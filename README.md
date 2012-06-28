wp-downloadmanager-extended
===========================

A fork of Lester Chan's (@gamerz) WP-DownloadManager plugin.

@gamerz's original version is at:
http://lesterchan.net/portfolio/programming/php/#wp-downloadmanager

Synopsis
--------

This fork will have the following enhancements over @gamerz's original
version (as of v1.60):

* Add %FILE\_SIZE\_DEC%, %TOTAL\_SIZE\_DEC%, and %CATEGORY\_SIZE\_DEC% template 
  variables for decimal file sizes (kB/MB/GB/TB), as opposed to the built-in
  template variables for binary file sizes (KiB/MiB/GiB/TiB);
* Add sorting options for embedded download lists;
* When rendering the post stream, make it possible to show only the top few
  items of an embedded download list, terminated with a "More…" link that
  points to the single post, wherein the complete embedded download list will
  be rendered;

A final, difficult challenge would be to either paginate embedded downloads or
request more results using AJAX.

Sorting Embedded Downloads
--------------------------

To control the sorting of embedded downloads, specify two new attributes in the
\[download\] shortcode:

* *sort_by* = the sorting criteria

  Valid values include:

    * file\_id (default)
    * file
    * file\_name
    * file\_size
    * file\_date
    * file\_hits

  Any invalid value will be ignored and the default *file_id* will be assumed.
* *sort_order* = ASCending or DESCending

  Valid values include:

    * asc (default)
    * desc

  Any invalid value will be ignored and the default *asc* will be assumed.

Limiting the Number of Embedded Downloads in the Post Stream
------------------------------------------------------------

To limit the number of embedded downloads displayed in the post stream, use the
new *stream_limit* attribute in the \[download\] shortcode.

Example:
  You have twenty files in category 2. Displaying them all in the post stream
  would take up too much vertical space, so you want to limit the number to
  five. This is the shortcode that you would use:

    [download category="2" stream_limit="5"]

  So, in the post stream, you will only see the top five items in category 2:

    report1.pdf
    report2.pdf
    report3.pdf
    report4.pdf
    report5.pdf

    More …

  The "More …" link points to the single post. So you can see the complete
  embedded download list in the single post.

Valid values for *stream_limit* are positive integers and zero (0), where zero
means no limit. Floating points, etc will be cast to an integer using the PHP
(int) casting, with zero (0) being the lowest value. Non-numeric values will be
ignored and zero (0) will be assumed.

License
-------

This plugin inherits the GPLv2 license under which the original
WP-DownloadManager plugin was released by Lester Chan. I have included the full
license text in wp-downloadmanager/gpl-2.0.txt.