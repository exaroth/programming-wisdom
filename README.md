## :sheep: Programming Wisdom
I3/Sway plugin containing programming wisdom to meditate over during long coding sessions.

<img align="left" width="500" src="demo.gif"><br/><br/>


## Overview

`Programming Wisdom` is a simple snippet for various tiling wm bar plugins which displays excerpts, proverbs, quotes and other wisdoms from across programming spectrum, based on 600+ assorted texts. Currently supported plugins:

- polybar
- waybar
- i3blocks

## Installation

Download `programming_wisdom` script

``` bash
curl -o programming_wisdom https://raw.githubusercontent.com/exaroth/programming-wisdom/main/programming_wisdom
```
Make it executable:

``` bash
chmod +x programming_wisdom
```

And put it in the location of your choice

## Usage

### polybar
```
    [module/programming-wisdom]
    type = custom/script
    exec = /path/to/programming_wisdom
    tail = true
```

### waybar
``` json
    "custom/programming-wisdom": {
        "escape": "true",
        "exec": "/path/to/programming_wisdom",
        "max-length": 60,
        "min-length": 60
    }
```

### i3blocks

```
    [PROGRAMMING_WISDOM]
    command=SNIPPET_OUTPUT_PANGO=1 /path/to/programming_wisdom
    color=#959692
    interval=persist
    markup=pango
```

## Configuration

Snippet can be configured by passing various env vars to the script, most straightforward way to do it is to pass them as a prefix when calling the executable, eg.

``` bash
ENV_VAR=val /path/to/programming_wisdom
```
Available settings:

- `SNIPPET_INTERVAL` - Defines how often to swap quotes (in seconds) (default: `10 minutes`)
- `SNIPPET_DELAY` - Refresh interval when outputting text (default `6`)
- `SNIPPET_WIDTH` - Width of the snippet (default `60`)
- `SNIPPET_ALIGN` - Set text alignment when outputting text, available values: `left`, `right`, `center` (default `left`)
- `SNIPPET_SHOW_AUTHOR` - Set whether to print author as part of the snippet output, available values: `0`/`1`
- `SNIPPET_OUTPUT_PANGO` - Output text in `pango` format (with monospace font set), `0`/`1`

### License
See `LICENSE` file for details
