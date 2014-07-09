---
layout: post
title: "Natural String Sorting "
date: 2012-08-08
comments: true
---
<p>Here's the quick run down of the problem. Let's suppose you have a list of string that contain numeric values. When you sort that list in .Net they probably don't get returned in the manner you'd expect. They get returned based upon their ASCII string values giving you a list that looks something like the image below. This problem has already been <a href="http://www.codinghorror.com/blog/2007/12/sorting-for-humans-natural-sort-order.html">covered</a> <a href="http://www.interact-sw.co.uk/iangblog/2007/12/13/natural-sorting">quite</a> <a href="http://nedbatchelder.com/blog/200712.html#e20071211T054956">extensively</a> so I'm going to quickly run through the solution I ended up using.</p>
<p><img src="http://testasoftware.com/assets/images/blog/NaturalStringComparer/badorder.png" alt="" height="256" width="240" /></p>
<p>In order to sort this list into a format we expect we need a natural (logical, humanized or whatever you prefer to call it) type of sorting. After doing the quick "research" that brought you the above links, I noticed that explorer displayed my list of directories I have been trying to sort in the manner I desired.</p>
<p><img src="http://testasoftware.com/assets/images/blog/NaturalStringComparer/files.png" alt="" height="398" width="501" /></p>
<p>This led me to find a <a href="http://stackoverflow.com/questions/248603/natural-sort-order-in-c-sharp">post</a> on stackoverflow.com describing how to use a native Windows method - <strong>StrCmpLogicalW(string psz1, string psz2)</strong> - to do the type of comparison I desired. Native methods can be imported and easily wrapped up in some nice usable .NET!&nbsp; I have provided a link to this code for ease of use.</p>
<p><a href="https://github.com/stesta/NaturalStringComparer">https://github.com/stesta/NaturalStringComparer</a></p>
<p>and the codez to use it...</p>
<pre>var mylist = new List&lt;string&gt;();
mylist.Sort(new NaturalStringComparer());
</pre>