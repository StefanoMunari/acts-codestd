# ADA CODING CONVENTIONS
 * _Official Ada standard conventions_  
REFERENCE: ftp://ftp.estec.esa.nl/pub/wm/anonymous/wme/bssc/bssc983.pdf  
[Useful book/reference on language constructs](https://en.wikibooks.org/wiki/Ada_Programming)

# OUR CONVENTIONS


## General rules

* Use spaces, not tabs

* Indent with 3 spaces

* Names are capitalized with _Pascal_Case_

* Do not exceed 80 columns, unless you have no other solutions
  * If parameters/arguments cause a line to exceed 80 cols, move the arguments
    to the following line and leave an open bracket in the first line:

  ```
     procedure Op (                             -- notice the open bracket here
        Very_Very_Very_Long_Arg1 : in out Type1);
  ```

* Leave a space before an open bracket: `A.Op (Arg)`

* Indent single-line comments so they are aligned with the beginning of the
  line they are referring
  * Corner case: if no indentation is applied to the line a comment is
    referring, do not apply any indentation to the comment itself

  ```
  -- Import Ada.Finalization
  with Ada.Finalization;       -- the comment above is OK

  -- Calling X of A
     A.X;                      -- the comment above is OK


     -- Calling X of A
     A.X;                      -- the comment above is NOT well-formatted
  ```

* Do not leave trailing whitespaces: if possible, use something like this
  [Sublime plugin](https://github.com/SublimeText/TrailingSpaces)

* If possible, align colons `:` of multiple contigous line of the same block
  (e.g., arguments, variable declarations, assignments, parameters, ...)

* If possible, align arrows `=>` of named arguments in function/procedure
  invocations


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

`limited with`'s should be avoided whenever possible.
**Rationale**: they cause hardly-debuggable errors at link time.

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


## Body files

The same rules for specification (`.ads`) files are valid for body (`.adb`)
files.

When invoking an operation, you should use named arguments if:

* There are 3/4 or more arguments
* Arguments may be inverted without making the compiler raise a warning/error
  because of their type

Use the `for Element of Elements` construct to iterate over a collection
`Elements`: it is a for-each loop, and at each iteration one of its elements
`Element` will be fetched from the collection without the need of declaring an
iteration variable.
_You'll not always be able to use the_ `for .. of` _construct, because it has
to be supported by the collection you are iterating over: for example,
GNATCOLL_JSON's arrays do not support this operation._
