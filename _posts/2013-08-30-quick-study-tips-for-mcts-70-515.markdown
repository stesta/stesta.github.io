---
layout: post
title: "Quick Study Tips for MCTS 70-515"
date: 2013-08-30
comments: true
---
<p><img src="/assets/images/blog/exam-passed.jpg" alt="" width="700" height="250" /></p>
<p>Well today I successfully passed my MCTS 70-515 exam! (Web Applications Development in .Net 4.0) -&nbsp;<strong>950/1000!</strong></p>
<div class="row">
<div class="span3"><img src="/assets/images/cert-logos/MCP(rgb).gif" alt="" width="160" height="80" /></div>
<div class="span5"><img src="/assets/images/cert-logos/MCTS(rgb)_1370.gif" alt="" width="331" height="80" /></div>
</div>
<p>I just wanted to gloat a little bit and share my quick study notes for some of the items I was less familiar with...</p>
<h3>MCTS 70-515 Quick Notes</h3>
<p>Page.ClientScript.*</p>
<ul>
<li>RegisterClientScriptBlock: adds client-side script to the top of the page</li>
<li>RegisterStartupScript: adds client-side script that executes before the page's OnLoad event is raised</li>
<li>RegisterClientScriptInclude: adds a reference to a client-side script</li>
<li>RegisterOnSubmitStatement: adds client-side script that executes when the page's OnSubmut event is raised&nbsp;</li>
</ul>
<p>Master/Content Life Cycle</p>
<ol>
<li>Master page controls PreInit event.&nbsp;</li>
<li>Content controls PreInit event.&nbsp;</li>
<li>Master page Init event.&nbsp;</li>
<li>Content page Init event.&nbsp;</li>
<li>Content page Load event.</li>
<li>Master page Load event.&nbsp;</li>
<li>Content controls Load event.</li>
<li>Content page PreRender event.&nbsp;</li>
<li>Master page PreRender event.&nbsp;</li>
<li>Master page controls PreRender event.&nbsp;</li>
<li>Content controls PreRender event.&nbsp;</li>
</ol>
<p>Page Life Cycle</p>
<ol>
<li>PreInit: before page initialization - check IsPostBack or IsCrossPostBack - create and add dynamic controls - set MasterPageFile or Theme - access profile properties&nbsp;</li>
<li>Init: after controls have been initialized and all skins and personalization settings have been applied - access control properties before view state is applied&nbsp;</li>
<li>PreLoad: after the view state is applied to the page and all controls, and after all postback data has been processed&nbsp;</li>
<li>Load: after PreLoad event has completed, but before control events have been raised - set control properties (after view state) - establish linkage to data sources</li>
<li>PreRender: after all control events have completed - final chance to modify content before client output is generated - view state has not been saved&nbsp;</li>
<li>PreRenderComplete: after data binding has been completed on all data-bound controls - check the contents of data-bound controls&nbsp;</li>
<li>SaveStateComplete: after view state has been saved for the page and all controls - access final view state before rendering</li>
<li>Unload: after the response has been generated for the client - perform cleanup of code, such as releasing resources</li>
</ol>
<p>Microsoft Ajax</p>
<ul>
<li>Sys.require: accepts a named reference to a registered script in Sys.scripts&nbsp;</li>
<li>Sys.loadScripts: used to dynamically load custom javascript files</li>
<li>Sys.loader.registerScript: requires a named referece to a registered script in Sys.scripts</li>
<li>Sys.loader.defineScript: provides a method to define a named reference to a script</li>
</ul>
<p>IIS 6.0 - httpHandlers &amp; httpModules<br /> IIS 7.0 - handler &amp; modules</p>
<p>aspnet_merge switches</p>
<ul>
<li>-o merge both UI elements and top-level assemblies&nbsp;</li>
<li>-w leave top-level assemblies unmerged&nbsp;</li>
</ul>
<p>Web Services</p>
<ul>
<li>.asmx - &lt;scripts&gt;&lt;asp:ScriptReference /&gt;&lt;/scripts&gt; - [ScriptService]&nbsp;</li>
<li>wcf - &lt;services&gt;&lt;asp:ServiceReference /&gt;&lt;/sservices&gt; - [AspNetCompatibilityRequirements] - enableWebScript behavior</li>
</ul>