# Git End-of-Line Issues

End of line characters vary on different operating systems.
Linux/Cygwin/Mac use newline (`\n`) whereas Windows uses carriage return followed by newline (`\r\n`).
If not handled properly, developers working on the same repository but doing work on different operating systems
will introduce conflicting end of line characters, which will potentially result in every line of a file being different.

Git will, with default configuration, store end end of line as found in the file.
However, conventions have been established so that:

* The repository only stores newline character for end of line
* The working files use the end of line character appropriate for the system

Background and a recommended solution is listed here:

* [GitHub - Dealing with line endings](https://help.github.com/articles/dealing-with-line-endings/)

## Use .gitattributes File to Control Line Endings

It is possible to use Git user settings to control how line endings are handled.
However, this assumes that all developers consistently define their settings, which likely will not occur.
Instead, it is best to define how end of line is handled by using the per-repository `.gitattributes` file.
The `.gitattributes` file is committed to the repository and will therefore be used consistently for all users,
assuming that client software recognizes the attributes.
The following is the recommended setting in the `.gitattributes` file:

```
# Set the default behavior, in case people don't have core.autocrlf set.
* text=auto
```

The person that sets up a repository initially should include an appropriate `.gitattributes` file.

## Avoiding Issues by Using Consistent Developer Environment

One way to avoid issues is to encourage use of a consistent development environment for the development team.
For example, if the target installed environment is Windows, then everyone should use Windows for development.
If Linux is the target environment, then Linux/Cygwin/Mac can be used to ensure consistent end of line for files. 
