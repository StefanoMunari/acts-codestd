# ELIXIR CODING CONVENTIONS

## Resources

* [Naming conventions](http://elixir-lang.org/docs/master/elixir/naming-conventions.html)

* [Programming conventions](https://github.com/StefanoMunari/city-codestd/blob/elixir_p0/elixir/programming.md)

* [Project organization](https://github.com/StefanoMunari/city-codestd/blob/elixir_p0/elixir/project.md)

* [Documenting functions/types](http://elixir-lang.org/docs/master/elixir/typespecs.html)

* [Commenting code (commenting + doctest)](http://elixir-lang.org/docs/master/elixir/writing-documentation.html)

## Our conventions

* These rules have been distilled from the aforementioned resources and from our
hands-on experience with the programming language applied to the ACTS project

### PROJECT ORGANIZATION

* Use `*.exs` extension only for scripts

* Create an Elixir project by using `mix new _project\_name_`

* Typical folders/files in a Elixir project:
  + *lib/*: place for source code
  + *mix.exs*: Compilation options
  + *config/config.exs*: Configuration file
  + *test/*: Folder for tests

* Use a `lib/projectname/cli.ex` as an entry point for the execution

* Structure the project so that it is composed of modules by dividing the *lib*
  folder in subdirectories


### PROGRAMMING CONVENTIONS

* Indent with two spaces

* Source code can be coded in UTF-8, but keep in mind to use ASCII for
  identifiers

* Put an underscore (`_`) in front of unexported functions and define them by
  means of the macro `defp`

* Use `Enum` module on finite and non-big collections of data; otherwise, use
  `Stream` (ordered) or `Flow` (unordered but concurrent processing)

* No trailing whitespaces

* Use `false` in a boolean context rather than `nil`

* Use (namely) `and`, `or`, `not` rather than their sloppy versions `&&`, `||`,
  `!`

* Prefer `pattern matching` to `case` statements

* Prefer `case` statements to `if` statements

* Use pipeline (`|>`) when possible

* Use double quotes for strings (e.g. `"Hello World!"`); sequences of characters
  like the following one `'hi'` are stored as a sequence of numeric values

* Use links only for processes termination, otherwise use monitor

* When making services for the application, prefer using OTP library rather than
  make all from scratch

## Notes

We use the following tools:

* [Mix](http://elixir-lang.org/docs/stable/mix/Mix.Project.html) to generate the project and handle dependencies

* [ExUnit](http://elixir-lang.org/docs/stable/ex_unit/ExUnit.html) to write unit tests

* [Dialyzer](https://github.com/jeremyjh/dialyxir) to type-check the source code

* [ExDoc](https://github.com/elixir-lang/ex_doc) to generate the project documentation
