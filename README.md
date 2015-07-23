<h1>Adobe XMP for WP</h1>

<table>
<tr><th align="right" valign="top" nowrap>Plugin Name</th><td>Adobe XMP for WP</td></tr>
<tr><th align="right" valign="top" nowrap>Summary</th><td>Access Adobe XMP / IPTC information from Media Library and NextGEN Gallery images using a Shortcode or PHP Class.</td></tr>
<tr><th align="right" valign="top" nowrap>Stable Version</th><td>1.2</td></tr>
<tr><th align="right" valign="top" nowrap>Requires At Least</th><td>WordPress 3.0</td></tr>
<tr><th align="right" valign="top" nowrap>Tested Up To</th><td>WordPress 4.2.3</td></tr>
<tr><th align="right" valign="top" nowrap>Contributors</th><td>jsmoriss</td></tr>
<tr><th align="right" valign="top" nowrap>License</th><td><a href="http://www.gnu.org/licenses/gpl.txt">GPLv3</a></td></tr>
<tr><th align="right" valign="top" nowrap>Tags / Keywords</th><td>adobe, xmp, xmpmeta, iptc, rdf, xml, lightroom, photoshop, media, library, nextgen, gallery, image, shortcode, function, method, meta data</td></tr>
</table>

<h2>Description</h2>

<p>Retrieve the following Adobe XMP / IPTC information from images in the WordPress Media Library and NextGEN Galleries:</p>

<ul>
<li>Creator Email</li>
<li>Owner Name</li>
<li>Creation Date</li>
<li>Modification Date</li>
<li>Label</li>
<li>Credit</li>
<li>Source</li>
<li>Headline</li>
<li>City</li>
<li>State</li>
<li>Country</li>
<li>Country Code</li>
<li>Location</li>
<li>Title</li>
<li>Description</li>
<li>Creator</li>
<li>Keywords</li>
<li>Hierarchical Keywords</li>
</ul>

<p>The <em>Adobe XMP for WP</em> plugin reads image files <em>progressively</em> (small chunks at a time) to extract the embeded XMP meta data, instead of reading the whole file into memory as other image management plugins do. The extracted XMP data is also <em>cached on disk</em> to improve performance and is refreshed only if/when the original image is modified. You can use the plugin in one of two ways; calling a method from the <code>$adobeXMP</code> global <strong>class object</strong> in your template(s), or using an <code>[xmp]</code> <strong>shortcode</strong> in your Posts or Pages.</p>

<!--more-->

<h4>Retrieve XMP data as an array</h4>

<pre><code>global $adobeXMP;

// $id can be media library image id, or nextgen gallery 
// image id in the form of 'ngg-#'.
$xmp = $adobeXMP-&gt;get_xmp( $id );

echo 'Taken by ', $xmp['Creator'], "\n";
</code></pre>

<p><a href="http://surniaulula.com/2013/04/09/read-adobe-xmp-xml-in-php/">You can read more about Adobe XMP for WP's class methods here</a>.</p>

<h4>Include a shortcode in your Post or Page</h4>

<pre><code>[xmp id="101,ngg-201"]
</code></pre>

<p>This shortcode prints all the XMP information for Media Library image ID "101" and NextGEN Gallery image ID "201". The XMP information is printed as a definition list <code>&lt;dl&gt;</code> with a class name of <code>xmp_shortcode</code> that you can style for your needs. Each <code>&lt;dt&gt;</code> and <code>&lt;dd&gt;</code> element also has a style corresponding to it's title - for example, the "Creator" list element has an <code>xmp_creator</code> class name. Here's an example of the definition list HTML:</p>

<pre><code>&lt;dl class="xmp_shortcode"&gt;
&lt;dt class="xmp_credit"&gt;Credit&lt;/dt&gt;
&lt;dd class="xmp_credit"&gt;Jean-Sebastien Morisset&lt;/dd&gt;
&lt;dt class="xmp_source"&gt;Source&lt;/dt&gt;
&lt;dd class="xmp_source"&gt;Underwater Focus&lt;/dd&gt;
&lt;dt class="xmp_hierarchical_keywords"&gt;Hierarchical Keywords&lt;/dt&gt;
&lt;dd class="xmp_hierarchical_keywords"&gt;What &amp;gt; Photography &amp;gt; 
    Field of View &amp;gt; Wide-Angle &amp;gt; Fish-Eye&lt;/dd&gt;
&lt;/dl&gt;
</code></pre>

<p>The shortcode can also take a few additional arguments:</p>

<ul>
<li><code>include</code> (defaults to "all")</li>
</ul>

<p>Define which XMP elements to include, for example <code>[xmp id="101" include="Creator,Creator Email"]</code>.</p>

<p>Please note that the <code>include</code> values are <strong>case sensitive</strong>.</p>

<ul>
<li><code>exclude</code> (defaults to none)</li>
</ul>

<p>Exclude some XMP elements, for example <code>[xmp id="101" exclude="Creator Email"]</code> to print all XMP elements, except for the "Creator Email".</p>

<ul>
<li><code>show_title</code> (defaults to "yes")</li>
</ul>

<p>Toggle printing of the XMP element title, for example <code>[xmp id="101" show_title="no"]</code> only prints the <code>&lt;dd&gt;</code> values, not the <code>&lt;dt&gt;</code> titles.</p>

<ul>
<li><code>not_keyword</code> (defaults to none)</li>
</ul>

<p>Exclude a list of (case incensitive) keywords, for example <code>[xmp id="101" not_keyword="who,what,where"]</code>.</p>

<p>To exclude a hierarchical keyword list, use hyphens between the keywords, for example <code>[xmp id="101" not_keyword="who,what,where,who-people-unknown"]</code>.</p>


<h2>Installation</h2>

<p><em>Using the WordPress Dashboard</em></p>

<ol>
<li>Login to your weblog</li>
<li>Go to Plugins</li>
<li>Select Add New</li>
<li>Search for <em>Adobe XMP for WP</em></li>
<li>Select Install</li>
<li>Select Install Now</li>
<li>Select Activate Plugin</li>
</ol>

<p><em>Manual</em></p>

<ol>
<li>Download and unzip the plugin</li>
<li>Upload the entire <code>adobe-xmp-for-wp/</code> folder to the <code>wp-content/plugins/</code> directory</li>
<li>Activate the plugin through the Plugins menu in WordPress</li>
</ol>


<h2>Frequently Asked Questions</h2>




<h2>Other Notes</h2>



