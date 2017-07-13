# Wordpress-Civil-Footnotes-2
WordPress plugin for making footnotes, a simple improvement upon <a href="https://wordpress.org/plugins/civil-footnotes/">Civil Footnotes</a>'s plugin.

Parses and displays footnotes, based on <a href="https://wordpress.org/plugins/civil-footnotes/">Civil Footnotes</a>, which itself was based on <a href="https://elvery.net/drzax/wordpress-footnotes-plugin">WP-Foonotes</a> by <a href="http://elvery.net">Simon Elvery</a>, and the footnote syntax pioneered by <a href="http://daringfireball.net/2005/07/footnotes">John Gruber</a>. The improvement here is that the title information is placed in a data-title attribute, not in the anchor's title attribute. This allows a custom CSS to style the popup, instead of the ugly default browser way. Without this, adding custom CSS worked, but the default popup still showed at the same time. See <a href="https://stackoverflow.com/a/35141804/">here</a> and <a href="https://stackoverflow.com/a/2011199/">here</a>.

Here is a sample CSS:

<pre>
/* Note: See: https://stackoverflow.com/a/2011199/ */
/* selecting on `a.civil-footnote`, could also do: `a[rel="footnote"` */

a.civil-footnote {
  display: inline;
}
a.civil-footnote:hover {
  text-decoration-line: none;
}
a.civil-footnote:hover:after {
  content: attr(data-title);
  z-index: 99;
  font-size: 18px;
  border-radius: 10px;
  padding: 4px 10px;
  margin-left: 5px;
  color: #fff;
  background: rgba(55, 55, 55, 0.5);
}
</pre>