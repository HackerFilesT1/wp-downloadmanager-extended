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
  items of an embedded download list with a "More…" link that points to the
  single post, wherein the complete embedded download list will be rendered;
