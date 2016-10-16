#ELIXIR PROJECT ORGANIZATION

## RULES
* Use `*.exs` extension only for scripts
* Create an Elixir project by using `mix new _project\_name_`
* Typical folders/files in a Elixir project:
  + *lib/*: place for source code
  + *mix.exs*: Compilation options
  + *config/config.exs*: Configuration file
  + *test/*: Folder for tests

## RECOMMANDATIONS
* Use a `lib/projectname/cli.ex` as an entry point for the execution
* Structure the project so that it is composed of modules by dividing the *lib*
  folder in subdirectories
