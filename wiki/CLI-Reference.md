# CLI Reference

This document provides detailed information about the ascii-cats command-line interface.

## Installation

To use ascii-cats as a command-line tool, install it globally:

```bash
npm install -g ascii-cats
```

## Basic Usage

Once installed, you can use the `asciiCats` command in your terminal:

```bash
# Display a random cat
asciiCats

# Display a specific cat
asciiCats nyan
```

## Command Syntax

```
asciiCats [cat-name] [options]
```

### Arguments

- `cat-name` (optional): The name of a specific cat to display. If omitted, a random cat will be shown.

### Options

- `-c, --cats`: Display a list of all available cat names
- `-h, --help`: Show help information

## Examples

### Display a Random Cat

```bash
asciiCats
```

Output (example):
```
  /\ ___ /\
 (  o   o  )
  \  >#<  /
  /       \
 /         \       ^
|           |     //
 \         /    //
  ///  ///   --
```

### Display a Specific Cat

```bash
asciiCats nyan
```

Output:
```
  ☆    ☆  ☆
┈┈┈┈ ╭━━━━━━╮  ☆
┈☆ ┈┈┃╳╳╳▕╲▂▂╱▏
┈┈☆ ┈┃╳╳╳▕▏▍▕▍▏
┈┈ ╰━┫╳╳╳▕▏╰┻╯▏
☆ ┈┈┈┃╳╳╳╳╲▂▂╱
   ☆ ╰┳┳━━┳┳╯   ☆
```

### List All Available Cats

```bash
asciiCats --cats
```

Output:
```
CAT OPTIONS: grumpy, approaching, tubby, confused, playful, thoughtful, delighted, nyan, resting, octocat, ready-to-attack, awake, sleepy, got-dat-cat, hector, leroy, longcat, lucky, sexy, fish-bowl, halloween
```

### Show Help Information

```bash
asciiCats --help
```

Output:
```
C A T   M E
print a cat to your console
                   ;,_            ,
                  _uP~"b          d"u,
                 dP'   "b       ,d"  "o
                d"    , `b     d"'    "b
               l] [    " `l,  d"       lb
               Ol ?     "  "b`"=uoqo,_  "l
             ,dBb "b        "b,    `"~~TObup,_
           ,d" (db.`"         ""     "tbc,_ `~"Yuu,_
         .d" l`T'  '=                      ~     `""Yu,
       ,dO` gP,                           `u,   b,_  "b7
      d?' ,d" l,                           `"b,_ `~b  "1
    ,8i' dl   `l                 ,ggQOV",dbgq,._"  `l  lb
   .df' (O,    "             ,ggQY"~  , @@@@@d"bd~  `b "1
  .df'   `"           -=@QgpOY""     (b  @@@@P db    `Lp"b,
 .d(                  _               "ko "=d_,Q`  ,_  "  "b,
 Ql         .         `"qo,._          "tQo,_`""bo ;tb,    `"b,
(qQ         |L           ~"QQQgggc,_.,dObc,opooO  `"~~";.   __,7,
`qp         t\io,_           `~"TOOggQV""""        _,dg,_ =PIQHib.
 `qp        `Q["tQQQo,_                          ,pl{QOP"'   7AFR`
   `         `tb  '""tQQQg,_             p" "b   `       .;-.`Vl'
              "Yb      `"tQOOo,__    _,edb    ` .__   /`/'|  |b;=;.__
                            `"tQQQOOOOP""        `"\QV;qQObob"`-._`\_~~-._
                                 """"    ._        /   | |oP"\_   ~\ ~\_  ~\
                                         `~"\ic,qggddOOP"|  |  ~\   `\  ~-._
                                           ,qP`"""|"   | `\ `;   `\   `\
                                _        _,p"     |    |   `\`;    |    |
                                 "boo,._dP"       `\_  `\    `\|   `\   ;
                                  `"7tY~'            `\  `\    `|_   |
                                                           `~\  |

Options:
  -c, --cats  get list of cat names
  -h, --help  Show help                                                [boolean]

Examples:
  asciiCats
  asciiCats nyan
```

## Integration with Other Tools

### Piping Output

You can pipe the output of ascii-cats to other commands:

```bash
# Save a cat to a file
asciiCats nyan > nyan-cat.txt

# Use a cat in a banner
asciiCats tubby | banner

# Send a cat via email (using mailx)
asciiCats | mailx -s "Have a cat!" recipient@example.com
```

### Using in Shell Scripts

You can use ascii-cats in shell scripts for fun error messages or welcome screens:

```bash
#!/bin/bash

# Display a welcome message with a cat
echo "Welcome to my script!"
asciiCats

# Do some work...
if [ $? -ne 0 ]; then
  echo "Something went wrong!"
  asciiCats grumpy
  exit 1
fi

# Success message
echo "All done successfully!"
asciiCats delighted
```

## Troubleshooting

### Command Not Found

If you get a "command not found" error, make sure:

1. You've installed ascii-cats globally (`npm install -g ascii-cats`)
2. Your npm global bin directory is in your PATH
3. You're using the correct command name (`asciiCats`)

### Display Issues

If cats don't display correctly:

1. Make sure your terminal supports Unicode characters
2. Check that your terminal font supports the characters used
3. Try a different cat that might use more basic ASCII characters

