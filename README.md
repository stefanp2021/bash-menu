Here's an updated version of the README reflecting the improvements:

---

# Bash Menu

Bash Menu is a Bash script to easily add an interactive menu to your scripts. The menu allows navigation and selection of items using keyboard inputs.

![Bash Menu](https://raw.githubusercontent.com/barbw1re/bash-menu/bash-menu-meta/bash-menu.png)

## Features

- Clear screen display with interactive menu
- Up/Down arrow keys for navigation
- Esc key jumps to and selects the last menu item
- Case-insensitive first character selection

## Prerequisites

Ensure the script runs in a Bash shell:

```bash
# Ensure we are running under bash
if [ "$BASH_SOURCE" = "" ]; then
    /bin/bash "$0"
    exit 0
fi
```

The `bash-menu.sh` script requires `bash-draw.sh` to be in the same directory.

## Usage

### Step 1. Download the Bash Menu scripts

Download `bash-menu.sh` and `bash-draw.sh` and place them in the same directory.

### Step 2. Import Bash Menu into your script

Import `bash-menu.sh`:

```bash
source /path/to/bash-menu.sh
```

### Step 3. Create handlers for each menu item

Create handler functions for each menu item:

```bash
actionA() { echo "Action A"; return 1; }
actionB() { echo "Action B"; return 1; }
actionExit() { echo "Exiting..."; return 0; }
```

### Step 4. Setup menu items

Populate the `menuItems` and `menuActions` arrays:

```bash
menuItems=("1. Item 1" "2. Item 2" "Q. Exit ")
menuActions=(actionA actionB actionExit)
```

### Step 5. Override menu configuration as needed

Customize menu variables:

```bash
menuTop=2
menuLeft=15
menuWidth=42
menuMargin=4
menuColour=$DRAW_COL_WHITE
menuHighlight=$DRAW_COL_GREEN
menuTitle="Super Bash Menu System"
menuFooter="Enter=Select, Up/Down=Prev/Next Option"
```

### Step 6. Display the Menu

Initialize and display the menu:

```bash
menuInit
menuLoop
```

The `menuLoop` function will continue until a menu item returns `0`.

## Versioning

We use [SemVer](http://semver.org/) for versioning. See the [tags on this repository](https://github.com/barbw1re/bash-menu/tags).

## Authors

- **Kris Johnson** - [barbw1re](https://github.com/barbw1re)

See the list of [contributors](https://github.com/barbw1re/bash-menu/contributors).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

Thanks to [top-scripts blog post](http://top-scripts.blogspot.com/2011/01/blog-post.html) for inspiration.
