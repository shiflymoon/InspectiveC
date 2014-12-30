InspectiveC
======

MobileSubstrate based objc_msgSend hook for debugging/inspection purposes.

Logs output to /tmp/InspectiveC/\<exe\>/\<pid\>_\<tid\>.

Based on [itrace by emeau](https://github.com/emeau/itrace), [AspectiveC by saurik](http://svn.saurik.com/repos/menes/trunk/aspectivec/AspectiveC.mm), and [Subjective-C by kennytm](http://networkpx.blogspot.com/2009/09/introducing-subjective-c.html).

This is **not compatible with arm64** at the moment, although I do hope to add support in the future.

**Features:**
* Watch specific objects
* Watch instances of a specific class
* Watch specific selectors
* Prints arguments

**Hopeful Features:**
* Hook obj_msgSend[st|fp]ret
* More advanced filtering
* arm64 support???

**Usage:**

Properly [install theos](http://iphonedevwiki.net/index.php/Theos/Setup) and grab yourself a copy
of the iOS SDK. You may have to modify the Makefile (i.e. ARCHS or TARGET) and/or InspectiveC.mm. I
compile this on my Mac with Clang - if you use anything different you may have some issues with the
assembly code.

Modify InspectiveC.plist to choose where to inject InspectiveC and just run "make package" to get
the dylib.
