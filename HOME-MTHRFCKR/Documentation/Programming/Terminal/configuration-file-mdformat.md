Toggle table of contents sidebar

Mdformat allows configuration in a [TOML](https://toml.io/) file named `.mdformat.toml`.

The configuration file will be resolved starting from the location of the file being formatted, and searching up the file tree until a config file is (or isn’t) found. When formatting standard input stream, resolution will be started from current working directory.

Command line interface arguments take precedence over the configuration file.

## Example configuration[¶](https://mdformat.readthedocs.io/en/stable/users/configuration_file.html#example-configuration "Permalink to this headline")

\# .mdformat.toml
#
\# This file shows the default values and is equivalent to having
\# no configuration file at all. Change the values for non-default
\# behavior.
#
wrap \= "keep" \# possible values: {"keep", "no", INTEGER}
number \= false \# possible values: {false, true}
end\_of\_line \= "lf" \# possible values: {"lf", "crlf"}