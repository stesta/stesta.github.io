---
layout: post
title: "Knockout Binding Handler for Google Maps"
date: 2014-01-04
comments: true
---
<p>Knockout Binding Handlers, FTW!</p>
<p>Very recently a client request came in for some new 'maps' features to their existing site. Their site is a C#/.NET 4.0 backend with a knockout.js frontend. They have a series of pages that represent their locations. To accompany the location information they wanted to display an interactive map. Google maps makes this easy enough, but with knockout it was even easier!</p>
<p>First the data. To position a map we're going to need latitude and longitude. Google makes this process super easy with their geocoding services. We start with a model to represent our location...</p>
<pre class="prettyprint linenums">[Serializable]<br />public class GeocoderLocation<br />{<br />&nbsp; &nbsp; &nbsp; &nbsp; public double Longitude { get; set; }<br />&nbsp; &nbsp; &nbsp; &nbsp; public double Latitude { get; set; }<br />&nbsp; &nbsp; &nbsp; &nbsp; public override string ToString()<br />&nbsp; &nbsp; &nbsp; &nbsp; {<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; return String.Format("{0}, {1}", Latitude, Longitude);<br />&nbsp; &nbsp; &nbsp; &nbsp; }<br /> }</pre>
<p>Then create a simple static method to use Google's geocoding service to populate that model based on a street address that we already have for the location.</p>
<pre class="prettyprint linenums">public static class Geocoder<br />{<br />&nbsp; &nbsp; &nbsp; &nbsp;public static GeocoderLocation GetLatitudeLongitude(string address)<br />&nbsp; &nbsp; &nbsp; &nbsp;{<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; WebRequest request = WebRequest<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; .Create("http://maps.googleapis.com/maps/api/geocode/xml?sensor=false&amp;address="<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; + HttpUtility.UrlEncode(address));<br /><br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; using (WebResponse response = request.GetResponse())<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; using (Stream stream = response.GetResponseStream())<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; {<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; XDocument document = XDocument.Load(new StreamReader(stream));<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; XElement longitudeElement = document.Descendants("lng").FirstOrDefault();<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; XElement latitudeElement = document.Descendants("lat").FirstOrDefault();<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; if (longitudeElement != null &amp;&amp; latitudeElement != null)<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; return new GeocoderLocation()<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; {<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Longitude = Double.Parse(longitudeElement.Value, CultureInfo.InvariantCulture),<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Latitude = Double.Parse(latitudeElement.Value, CultureInfo.InvariantCulture)<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; };<br /><br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; return null;<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; }<br />&nbsp; &nbsp; &nbsp; &nbsp;}<br />&nbsp;}</pre>
<p>What I actually ended up doing was using these two bits of code to update their database location records to include the returned latitude and longitude. I then updated the location c-sharp and corresponding javascript models to include these values when the data is returned. Having the latitude and longitude available on the frontend model made it easy to use the Google Maps Javascript API to create a map.</p>
<p>What I ended up doing was creating a Knockout binding handler to create the map.</p>
<pre class="prettyprint linenums">ko.bindingHandlers.googlemap = {
        init: function (element, valueAccessor) {
            var
                value = valueAccessor(),
                latLng = new google.maps.LatLng(value.latitude(), value.longitude()),
                mapOptions = {
                    zoom: 16,
                    center: latLng,
                    mapTypeId: google.maps.MapTypeId.ROADMAP
                },
                map = new google.maps.Map(element, mapOptions),
                marker = new google.maps.Marker({
                    position: latLng,
                    map: map
                });
        }
    };</pre>
<p>Below is a simple example of how to acutally use this binding handler...&nbsp;<br />(note you need to specify a height and width for your map)</p>
<pre class="prettyprint linenums">&lt;style&gt;<br />.map { height:300px; width:300px; }<br />&lt;/style&gt;<br /><br />&lt;div data-bind="foreach: locations"&gt;<br />&nbsp; &nbsp; &lt;div data-bind="text: name"&gt;&lt;/div&gt;<br />&nbsp; &nbsp; &lt;div class="map" data-bind="googlemap: { latitude: latitude, longitude: longitude }"&gt;&lt;/div&gt;<br />&lt;/div&gt;</pre>
<p>Easy enough! 15 minutes of work!</p>