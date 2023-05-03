---
---
# LOTJ Datapad API

## Introduction

:::caution First time coding?
This API is intended for advanced players who either have some programming experience or a strong willingness to learn. Please note that as this system continues to develop, certain aspects of the API may change.
:::

Welcome to the in-game Lua API for your datapad! This powerful tool allows you to customize your epic gaming experience by writing and running Lua code directly on your datapad. Whether you're a seasoned programmer or a curious player, this API opens up new possibilities for in-game interactions and automation.

With this API, you can perform basic text and number manipulations, as well as access datapad-related functions such as adding or deleting messages. I've designed this guide to be accessible to both programmers and non-programmers, so feel free to explore at your own pace.

## Getting Started

```lua
local now = LOTJ.date()

return now
```

> When a program like above is run using `dataprog`, your character will see something like this:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: Fri Apr 28 01:26:29 2023
```

To get started, all you need is:

* a datapad
* [Lua basics](#basics-of-lua)

To write a datapad program, simply use your datapad like usual to write a new note:

`datamem write new`

Once you wrote and saved your code, you can run it with:

`dataprog run <note number> (<arguments>)`

### dataprog Command Parameters

| Parameter     | Required | Description                                                                                                                  |
| ------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `note number` | Yes      | The datapad note number containing your code.                                                                                |
| `arguments`   |          | If you want, you can pass your own arguments into your program - it will be available as the `args` variable for you to use. |

:::tip About `arguments`
If you intend to use multiple arguments, the resulting <code>args</code> variable is a string so you will need to do your own parsing to split them. 
:::

This command does a few things:

1. Run your code
2. Report an error, if there are any
3. Show you the result you potentially `return`ed from your code

## Next steps

[The rest of this page](./docs/LOTJ) outlines all the various functions and variables you can use in your datapad code. Besides LotJ specific functions, you can use the following common Lua functions and libraries:

* [pairs](https://www.lua.org/manual/5.1/manual.html#pdf-pairs)
* [ipairs](https://www.lua.org/manual/5.1/manual.html#pdf-ipairs)
* [next](https://www.lua.org/manual/5.1/manual.html#pdf-next)
* [select](https://www.lua.org/manual/5.1/manual.html#pdf-select)
* [tonumber](https://www.lua.org/manual/5.1/manual.html#pdf-tonumber)
* [tostring](https://www.lua.org/manual/5.1/manual.html#pdf-tostring)
* [type](https://www.lua.org/manual/5.1/manual.html#pdf-type)
* [unpack](https://www.lua.org/manual/5.1/manual.html#pdf-unpack)
* [string](https://www.lua.org/manual/5.1/manual.html#5.4)
* [table](https://www.lua.org/manual/5.1/manual.html#5.5)
* [math](https://www.lua.org/manual/5.1/manual.html#5.6)


## Basics of Lua

Lua is a lightweight, easy-to-learn scripting language that's perfect for embedding in applications, like LotJ has been doing for all sorts of fun things. If you're new to Lua, have a look at these resources to familiarize yourself with the language:

* [Lua 5.1 Reference Manual](https://www.lua.org/manual/5.1/)
* [Programming in Lua](https://www.lua.org/pil/)
