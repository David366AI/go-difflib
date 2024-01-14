go-difflib
==========

Forked from https://github.com/pmezard/go-difflib

Go-difflib is a partial port of python 3 difflib package. Its main goal
was to make unified and context diff available in pure Go, mostly for
testing purposes.

The following class and functions (and related tests) have be ported:

* `SequenceMatcher`
* `unified_diff()`
* `context_diff()`
* `Differ`  (NEW!!!)

## Installation

```bash
$ go get github.com/David366AI/go-difflib/difflib
```

### Quick Start

Diffs are configured with Unified (or ContextDiff) structures, and can
be output to an io.Writer or returned as a string.

```Go
text1Words := []string{"In", "the", "last", "weekend"}
text2Words := []string{"In", "the", "Last", "Weekend"}
differ := difflib.NewDiffer(nil, difflib.IsCharacterJunk)
result := differ.Compare(text1Words, text2Words)
for _, item := range result {
    fmt.Println(item)
}
```

would output:

```
  In
  the
- last
+ Last
- weekend
+ Weekend
```

