Documentation can be found at

-   [https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/tcllib/files/modules/textutil/textutil.md](https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/tcllib/files/modules/textutil/textutil.md)
-   [http://docs.activestate.com/activetcl/8.5/tcl/tcllib/textutil/textutil.html](http://docs.activestate.com/activetcl/8.5/tcl/tcllib/textutil/textutil.html)

Contains for example the core of the template and macro processor [expand](https://wiki.tcl-lang.org/page/expand). Released since Tcllib 1.2.

Module contains:

-   **textutil::adjust** _string_ ?_option value..._?
-   **textutil::adjust::getPredefined** _filename_
-   **textutil::adjust::listPredefined**
-   **textutil::adjust::readPatterns** _filename_
-   **textutil::indent** _string prefix_ ?_skip_?
-   **textutil::undent** _string_
    -   See also [ycl dedent](https://wiki.tcl-lang.org/page/ycl), which considers tabs when determining how to remove indentation.
-   **textutil::strRepeat** _string num_
-   **textutil::blank** _num_
-   **textutil::[splitn](https://wiki.tcl-lang.org/page/splitn)** _string_ ?_len_?  
    _len_ defaults to 1
-   **textutil::[splitx](https://wiki.tcl-lang.org/page/splitx)** _string_ ?_regexp_?  
    _regexp_ defaults to \[\\t \\r\\n\]+
-   **textutil::cap** _string_
-   **textutil::chop** _string_
-   **textutil::longestCommonPrefixList** _list_
-   **textutil::longestCommonPrefix** ?_string_?
-   **textutil::tail** _string_
-   **textutil::uncap** _string_
-   **textutil::tabify** _string_ ?_num_?
-   **textutil::tabify2** _string_ ?_num_?
-   **textutil::untabify** _string_ ?_num_?
-   **textutil::untabify2** _string_ ?_num_?  
    _tab_ above defaults to 8
-   **textutil::trim** _string_ ?_regexp_?
-   **textutil::trimleft** _string_ ?_regexp_?
-   **textutil::trimright** _string_ ?_regexp_?
-   **textutil::trimPrefix** _string prefix_
-   **textutil::trimEmptyHeading** _string_  
    _regexp_ above defaults to \[\\t \\r\\n\]+
-   textutil::expand  
    **Note:** This command comes in its own package
-   textutil::expander  
    This package is used by [doctools](https://wiki.tcl-lang.org/page/doctools).

_[escargo](https://wiki.tcl-lang.org/page/escargo) 30 May 2007_ - This seems to be documentation for a version prior to Tcl 8.2, textutil 0.7.1.

___