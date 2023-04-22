# Zsh Cheatsheet

---

## Expressions

Expression

Example

Description

`!!`

`sudo !!`

Last command (`sudo !!`)

`!*`

`vim !*`

Last command’s parameters (`vim !*`)

`!^`

 

Last command’s first parameter

`!$`

 

Last command’s last parameter

`!?ls` `<tab>`

`sudo !?mv` `<tab>`

Command and params of last `ls` command

`!?ls?:*` `<tab>`

 

Params of last `ls` command

`*(m0)`

`rm *(m0)`

Last modified today

`*(m-4)`

 

Last modified <4 days ago

## Change Default Shell

```bash
chsh -s `which zsh`
```

## Process Substitution

Expression

Example

Description

`<(COMMAND)`

`grep "needle" <(curl "https://haystack.io")`

Replace argument with *named pipe/FIFO* (read-only) with command output

`=(COMMAND)`

`vim =(curl "https://haystack.io")`

Replace argument with *file* (writable) containing command output

## Also See

- [Bash cheatsheet](https://devhints.io/zsh./bash)

Zsh is mostly compatible with Bash, so most everything in Bash’s cheatsheet also applies.
