# prism-ie-crash
Prism/Change-Detection IE11 ES5 crash Miminal Working Example

Minimal working example to show the issue I'm having.

I'm importing ngx-prism, which at its turn imports angular-package/change-detection as a dependency.
The change detection decorator ts file has a default argument set to its function, which isn't supported by ES5.

When building the app using target:es2015 (and having IE11 in browserslist), running it in a standalone webserver, and then opening it in IE11, Everything is OK.

When setting the target to es5 and building it, running it in a standalone webserver, and opening it in IE11 there are errors.
It fails on the part where the default argument is.

There are examples of the build folders in the repository. You can find the offending lines in the vendor.js file in the es5-only dist folder.

I don't understand why building for es2015 generates a valid es5 file, and building for es5 directly doesnt.
Are there steps that I have to perform explicitly when building for es5 that are done hidden/automatically when building for es2015/es5?
