---
layout: post
title: "Generating C# Classes from an XML File"
date: 2013-10-08
comments: true
---
<p>I frequently come to the conclusion that I'm working too hard. This is usually because I try to reinvent the wheel when someone out there has already done the job better than I could have. Recently, I had a need to create some strongly typed C# models to help with deserializing some XML. For simple XML it's easy enough to create these models/classes by hand. For more complex XML it's often easier to use the XML Schema Definition tool.</p>
<p>The XML Schema Definition tool is packaged into the Windows SDK. This means I've had this tool on my machine for practically forever and have been doing things the hard way for a long time.</p>
<p>Your path to xsd.exe will look something like this depending on which version of the Windows SDK you have installed.</p>
<pre>C:\Program Files (x86)\Microsoft SDKs\Windows\&lt;version&gt;\Bin\NETFX 4.0 Tools\xsd.exe</pre>
<p>It's a two step process to convert an XML file to a corresponding set of C# classes: create an XSD from your XML and then create your C# classes from that XSD...</p>
<h3>XML to XSD</h3>
<p>The follwing will&nbsp;output &lt;filename&gt;.xsd</p>
<pre>xsd.exe &lt;filename&gt;.xml </pre>
<h3>XSD to C# Classes</h3>
<p>The following will output your csharp classes to a single file &lt;filename&gt;.cs - Note the '/l:cs' switch can be changed to '/l:vb' to output VB instead of C#</p>
<pre>xsd.exe /c /l:cs file.xsd</pre>
<p>And that's it! You should now have an auto-generated C# model. By default this file will be placed into the same directory as the xsd executable. You can also specify the <strong>'-out:&lt;directoryName&gt;'&nbsp;</strong>in order to change the location that your files get saved.</p>