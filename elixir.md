# Elixir Coding Conventions

## Resources

* [Naming conventions](http://elixir-lang.org/docs/master/elixir/naming-conventions.html)

* [Programming conventions](https://github.com/StefanoMunari/city-codestd/blob/elixir_p0/elixir/programming.md)

* [Project organization](https://github.com/StefanoMunari/city-codestd/blob/elixir_p0/elixir/project.md)

* [Documenting functions/types](http://elixir-lang.org/docs/master/elixir/typespecs.html)

* [Commenting code (commenting + doctest)](http://elixir-lang.org/docs/master/elixir/writing-documentation.html)

## Our conventions

* These rules have been distilled from the aforementioned resources and from our
hands-on experience with the programming language applied to the ACTS project

### Project Organization

* Use `*.exs` extension only for scripts

* Create an Elixir project by using `mix new _project\_name_`

* Typical folders/files structure of an Elixir project:

	+ *lib/*: place for source code
	+ *mix.exs*: Compilation options
	+ *config/config.exs*: Configuration file
	+ *test/*: Folder for tests

  If the application has been structured to be deployed under different deployment environments ([Martin Fowler - CI](https://martinfowler.com/articles/continuousIntegration.html), [Wiki - deployment environment](https://en.wikipedia.org/wiki/Deployment_environment)), the configuration files will typically be placed in:

  	+ *config/dev.exs*: Configuration file for **development** mode
  	+ *config/prod.exs*: Configuration file for **production** mode
  	+ *config/test.exs*: Configuration file for **test** mode

* Structure the project as a composition of modules by dividing the *lib*
  folder in subdirectories


### Programming Conventions

* Indent with two spaces

* Source code can be coded in UTF-8, but keep in mind to use ASCII for
  identifiers in order to have better code readability

* Put an underscore (`_`) in front of unexported (private) functions and define
  them by means of the macro `defp`

* Use `Enum` module on finite and non-big collections of data; otherwise, use
  `Stream` (ordered) or `Flow` (unordered but concurrent processing)

* No trailing whitespaces

* Use `false` in a boolean context rather than `nil`

* Use (namely) `and`, `or`, `not` rather than their sloppy versions `&&`, `||`,
  `!`

* Prefer `pattern matching` to `case` statements

* Prefer `case` statements to `if` statements

* Use pipelining (`|>`) when possible

* Use double quotes for strings (e.g. `"Hello World!"`); sequences of characters
  like the following one `'hi'` are stored as a sequence of numeric values

* Use links only for processes termination, otherwise use monitor

* Use tasks for one-shot monitored services

* When making services for the application, prefer using OTP library rather than
  make all from scratch

## Notes

The following tools are widespread used in the Elixir community:

* [Mix](http://elixir-lang.org/docs/stable/mix/Mix.Project.html) to generate the project and handle dependencies

* [ExUnit](http://elixir-lang.org/docs/stable/ex_unit/ExUnit.html) to write unit tests

* [Dialyzer](https://github.com/jeremyjh/dialyxir) to inspect the source code and find possible bugs

* [ExDoc](https://github.com/elixir-lang/ex_doc) to generate the project documentation
