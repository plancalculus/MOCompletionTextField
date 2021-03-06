MOCompletionTextField
=====================


Introduction
------------

Subclass of `UITextField` that remembers previous entries and displays
a view with possible completions above the keyboard. The entries are
stored in a string trie (http://en.wikipedia.org/wiki/Trie) that can
be written to disc. The following images show an example application
that comes with the library.

![](https://github.com/plancalculus/MOCompletionTextField/raw/master/Screenshots/MOCompletionTextFieldExample1.png)
 
![](https://github.com/plancalculus/MOCompletionTextField/raw/master/Screenshots/MOCompletionTextFieldExample2.png)


Features
--------

A `MOCompletionTextField` can be used as a replacement for
`UITextField`. If multiple text fields are supposed to provide
identical completions, construct a string trie by invoking

    [[MOStringTrie alloc] init] 

and set the `completionStringTrie` property of all the text fields to
this trie. If you have written the trie to disc you can use

    [[MOStringTrie alloc] initWithContentsOfFile:filePath]

to initialise it. The library comes with an example project that
provides a table view with text fields that all share one trie. The
property `completionEnumerationStyle` of a text field can be used to
specify the order of the enumeration. Currently completions can be
ordered lexicographically as well as by frequency of their uses.


Usage
-----

Import the static library as a sub-project into your main project. As
the library uses a category you have to go to the Build Settings of
the target that is using the library and set the `Other Linker Flag`
to `-ObjC`.


Requirements
------------

You need iOS 4 or later as the library uses automatic reference
counting lite. Furthermore, as the library uses the new enum
declaration style you need XCode 4.5, which is currently only
available as developer preview.


License
-------

`MOCompletionTextField` is released under Modified BSD License.