# JBML Formal Specification
My official formal specification for the JBML markup. Much like other markups, JBML also supports newline characters within an array, map or string. For the sake of brevity, this is not directly represented in the actual formal specification file.

## JBML features
JBML features a variety of different data types and operations. First, it has key to value pairs:

_key = value_

Much like TOML, a _value_ can be a string (e.g. ```intro = "Hello world"```), integer (e.g. ```age = 3```), decimal (e.g. ```pi = 3.14```), boolean (e.g. ```use_app = true```), a list/array (e.g. ```numbers = [1, 2, 3]```).

Additionally, JBML supports additional types in the _value_ including:
- mappings (e.g. ```letters = { "x" : 1, "y" : 3}```)
- concatenation (e.g. ```intro = "Hello " **&** "world"```)
- [properties](properties) (e.g. ```name = firstname```)

### Properties
Properties, also known as predefined values, work similarly to variables. Properties reference previously defined keys within the current group. See the code block below which demonstrates the concatenation of the ip and port properties to create an actual connect string.

```
[Network]
ip = "192.168.1.1"
port = 8080
connect_string = ip & ":" & port
```
