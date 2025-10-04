# Regex en PHP

## Funciones principales
| Función                                  | Uso                               |
| ---------------------------------------- | --------------------------------- |
| ` preg_match($pat, $str, $matches) `     | Busca la **primera coincidencia** |
| ` preg_match_all($pat, $str, $matches) ` | Busca **todas las coincidencias** |
| ` preg_replace($pat, $repl, $str) `      | Sustituye                         |
| ` preg_split($pat, $str) `               | Divide un string por regex        |
## Delimitadores y modificadores
- Sintaxis:` /regex/modificadores `
- Modificadores más usados: 
	- -` i `→ case-insensitive 
	- -` m `→ multiline ( ^ y $ funcionan por línea ) 
	- -` u `→ UTF-8 -` x `→ regex legible con comentarios

--- 
## Metacaracteres
| Patrón    | Significado                               |
| --------- | ----------------------------------------- |
| `.`       | Cualquier carácter (menos salto de línea) |
| `^`       | Inicio de string                          |
| `$`       | Fin de string                             |
| `\d`      | Dígito` [0-9]`                            |
| `\w`      | Alfanumérico` [A-Za-z0-9_]`               |
| `\s`      | Espacio en blanco                         |
| `+`       | Uno o más                                 |
| `*`       | Cero o más                                |
| `?`       | Cero o uno                                |
| `{n,m}`   | Entre n y m repeticiones                  |
| `[abc]`   | Uno de a, b o c                           |
| `[^abc]`  | Cualquiera excepto a, b o c               |
| `( ... )` | Grupo con captura                         |
