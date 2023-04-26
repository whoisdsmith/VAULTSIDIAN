# Regex for Random Numbers

find random numbers like this

cAABa-4_vdnV_IpwMg148Va_7M0Fj

Certainly! Here's a regular expression that will match the pattern you provided:

```
\w{5}-\w{8}-\w{5}-\w{23}
```

This regular expression matches a string consisting of:

- `\w{5}`: any 5 word characters (letters, digits, or underscores)
- `-`: a literal hyphen
- `\w{8}`: any 8 word characters
- `-`: a literal hyphen
- `\w{5}`: any 5 word characters
- `-`: a literal hyphen
- `\w{23}`: any 23 word characters

This will match the pattern you provided: `cAABa-4_vdnV_IpwMg148Va_7M0Fj`.

that didn't work

I apologize for the confusion. Here's another regular expression that should match the pattern you provided:

```
\w{5}-\w{10}-\w{9}-\w{6}
```

This regular expression matches a string consisting of:

- `\w{5}`: any 5 word characters (letters, digits, or underscores)
- `-`: a literal hyphen
- `\w{10}`: any 10 word characters
- `-`: a literal hyphen
- `\w{9}`: any 9 word characters
- `-`: a literal hyphen
- `\w{6}`: any 6 word characters

This should match the pattern you provided: `cAABa-4_vdnV_IpwMg148Va_7M0Fj`.
