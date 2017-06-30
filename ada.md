# ADA CODING CONVENTIONS
 * _Official Ada standard conventions_  
REFERENCE: ftp://ftp.estec.esa.nl/pub/wm/anonymous/wme/bssc/bssc983.pdf  
[Useful book/reference on language constructs](https://en.wikibooks.org/wiki/Ada_Programming)

# OUR CONVENTIONS

## File headers

We consider header all of what is above the `package [body] X.Y.Z is` line.

All imports are formatted as follows:

```
with Ada.Package_Name1; -- if any
with Ada.Package_Name2;
...

with Library.Package_Name1; -- if any
with Library.Package_Name2;
...

with Our_Main_Package1.Package_Name1; -- if any
with Our_Main_Package1.Package_Name2;
...

with Our_Main_Package2.Package_Name1; -- if any
with Our_Main_Package2.Package_Name2;
...
```

Where:

* `Ada.Package_Name` is an Ada package
* `Library.Package_Name` is a package present in one library (e.g., GNATCOLL's
  JSON)
* `Our_Main_Package.Package_Name` is a module present in one major package of
  our application
* The suffixes `1` and `2` are meant to represent an alphabetical ordering
* `with`'s with different initial prefix are separated by an additional newline
  (as in the format example above)


We don't know yet if our files will have a license at their beginning.
>>>>>>> add header conventions
