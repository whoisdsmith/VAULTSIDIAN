# Useful Regex Expressions

## Lowercase letters

`[a-z]`

## Capital letters

`[A-Z]`

## Numbers

`[\d]`

## Lowercase and uppercase accented letters

`[àèìòùáéíóúâêîôûäëïöüãõ]`

### Accented lowercase and uppercase letters and cedilla

`[\p{Letter}]`

## Cedilla

`[ç]`

## Accents

`[`´^~¨]`

## Punctuation marks

`[.:,;\-_<>=+*!?)(}{|''""\][\\/]`

## Symbols

`[@#$%&]`

## Spaces

`[\s]`

## Line breaks

`[\n]`

## Characters non-unicode

`(?![ -~ç´¨àèìòùáéíóúâêîôûäëïöüãõ\n]).` 

## character non-unicode

`[^\p{Letter}\d`´^~¨.,;\-_<>=+*!?)(}{|'"\]`

`[\\/@#$%&\s\n]` 

`[a-zA-Z\dàèìòùáéíóúâêîôûäëïöüãõç`´^~¨.:,;\-_<>=+*!?)(}{|'"\][\\/@#$%&\s\n]`

`[\p{Letter}\d`´^~¨.:,;\-_<>=+*!?)(}{|'"\][\\/@#$%&\s\n]`
