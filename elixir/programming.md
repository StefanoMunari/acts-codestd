#ELIXIR PROGRAMMING CONVENTIONS

## RULES
* Indent with two spaces
* Source code can be coded in UTF-8, but keep in mind to use ASCII for
  identifiers
* Put an underscore (`_`) in front of unexported functions and define them by
  means of the macro `defp`
* Use `Enum` module on finite and non-big collections of data; otherwise, use
  `Stream` (ordered) or `Flow` (unordered but concurrent processing)
* No trailing whitespaces

## RECOMMANDATIONS
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
