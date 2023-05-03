
# LOTJ

`LOTJ` table holds general utility functions.

## 

## date

`LOTJ.date()` returns the current in-game date.

### Example

```lua
return LOTJ.date()
```

> `dataprog` Output:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: Fri Apr 28 01:26:29 2023
```

##

## time

`LOTJ.time()` returns the current in-game time.

##

## stripColor

`LOTJ.stripColor(string)` removes all color codes from a string.

### Parameters

| Parameter | Required | Description                                                                                                                  |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `string`  | Yes      | The string to remove color codes from.                                                                                       |

### Example

```lua
local str = "&zThis is a &Rcolored&W string.&D"

return LOTJ.stripColor(str)
```

> `dataprog` Output:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: This is a colored string.
```

## keywordCheck

`LOTJ.keywordCheck(args, keywords)` checks if a string matches any of the keywords.

### Parameters

| Parameter  | Required | Description                                                                                                                  |
| ---------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `args`     | Yes      | The string to check.                                                                                                        |
| `keywords` | Yes      | A table of keywords to check against.                                                                                       |

### Example

```lua
local keywords = {"foo", "bar", "baz"}

return LOTJ.keywordCheck(args, keywords) -- args is passed by dataprog
```

> `dataprog` Output, using `dataprog run 1 foo`:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: true
```

> `dataprog` Output, using `dataprog run 1 qux`:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: false
```


