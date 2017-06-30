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


## Specification files

Specification files should be formatted as follows:

```
package X.Y.Z is

   package A renames B; -- if any
   ...

   type T is [add type definition here]; -- if any
   ...

   [not] overriding -- only if operation is defined on instances of this package
   [ procedure | function ] Op ([add arguments here: see rules below]);
   ...

private

   type T is [add type definition here]; -- if any
   ...

   [not] overriding -- only if operation is defined on instances of this package
   [ procedure | function ] Op ([add arguments here: see rules below]);
   ...
```

The argument list should be formatted as follows:

* If there are only `in` (or only `out`) arguments, do not add any offset
  before their type

* In case of `in` **and** `out` arguments, they have to be aligned as follows:

```
   procedure Op (Arg1      : in out Type1;  -- no offset needed here
                 Such_Arg2 : in     Type2;  -- notice the offset of Type2
                 The_Arg3  :    out Type3;  -- notice the offset of Type3
                 Arg4      : access Type4); -- no offset needed here
```

* If the first line exceeds 80 columns, format the arguments as follows

```
   procedure Op (
      Very_Very_Very_Long_Arg1 : in out Type1;  -- would have exceeded 80 cols
      Such_Arg2                : in     Type2;  -- aligned with arg1
      The_Arg3                 :    out Type3;  -- aligned with arg1
      Arg4                     : access Type4); -- aligned with arg1
```
