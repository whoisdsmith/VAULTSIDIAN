# Textutil

Documentation can be found at

- [https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/tcllib/files/modules/textutil/textutil.md](https://core.tcl-lang.org/tcllib/doc/trunk/embedded/md/tcllib/files/modules/textutil/textutil.md)
- [http://docs.activestate.com/activetcl/8.5/tcl/tcllib/textutil/textutil.html](http://docs.activestate.com/activetcl/8.5/tcl/tcllib/textutil/textutil.html)

Contains for example the core of the template and macro processor [expand](https://wiki.tcl-lang.org/page/expand). Released since Tcllib 1.2.

Module contains:

- **textutil::adjust** *string* ?*option value…*?
- **textutil::adjust::getPredefined** *filename*
- **textutil::adjust::listPredefined**
- **textutil::adjust::readPatterns** *filename*
- **textutil::indent** *string prefix* ?*skip*?
- **textutil::undent** *string*
    - See also [ycl dedent](https://wiki.tcl-lang.org/page/ycl), which considers tabs when determining how to remove indentation.
- **textutil::strRepeat** *string num*
- **textutil::blank** *num*
- **textutil::[splitn](https://wiki.tcl-lang.org/page/splitn)** *string* ?*len*?  
    *len* defaults to 1
- **textutil::[splitx](https://wiki.tcl-lang.org/page/splitx)** *string* ?*regexp*?  
    *regexp* defaults to \[\\t \\r\\n\]+
- **textutil::cap** *string*
- **textutil::chop** *string*
- **textutil::longestCommonPrefixList** *list*
- **textutil::longestCommonPrefix** ?*string*?
- **textutil::tail** *string*
- **textutil::uncap** *string*
- **textutil::tabify** *string* ?*num*?
- **textutil::tabify2** *string* ?*num*?
- **textutil::untabify** *string* ?*num*?
- **textutil::untabify2** *string* ?*num*?  
    *tab* above defaults to 8
- **textutil::trim** *string* ?*regexp*?
- **textutil::trimleft** *string* ?*regexp*?
- **textutil::trimright** *string* ?*regexp*?
- **textutil::trimPrefix** *string prefix*
- **textutil::trimEmptyHeading** *string*  
    *regexp* above defaults to \[\\t \\r\\n\]+
- textutil::expand  
    **Note:** This command comes in its own package
- textutil::expander  
    This package is used by [doctools](https://wiki.tcl-lang.org/page/doctools).

*[escargo](https://wiki.tcl-lang.org/page/escargo) 30 May 2007* - This seems to be documentation for a version prior to Tcl 8.2, textutil 0.7.1.

___
