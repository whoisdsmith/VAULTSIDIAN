---
tags:: apps
---
php occ integrity:check-core

php occ integrity:check-core --help
Description:
  Check integrity of core code using a signature.

Usage:
  integrity:check-core [options]

Options:
      --output[=OUTPUT]  Output format (plain, json or json_pretty, default is plain) [default: "plain"]

php occ integrity:check-core --output=plain

php occ integrity:check-core --output=json_pretty
[]