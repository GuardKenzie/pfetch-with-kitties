<p align="center"><img src="https://raw.githubusercontent.com/andreasgrafen/pfetch-with-kitties/main/assets/preview.jpg" width="75%" alt="Terminal Window showing off the Kitty ASCII art">
</p>
<h1 align="center">Literally pfetch but with kitties</h1>
<p align="center">A pretty system information tool written in POSIX sh</p><br>

## Modifications
This fork adds the option to display your local ip address and the current weather. 

### Weather
The weather script just reads and outputs the content of the file specified in `PF_WEATHER`. You can create a script to update that file with your current weather.

[Here is my script](https://github.com/GuardKenzie/kastali/blob/master/.dotfiles/vedur.py) which I run as a chron job every 5 minutes.
The script takes 2 arguments:

1. Your location, the same as for [wttr.in](https://wttr.in/:help).
2. The weather file. 

## Configuration

`pfetch` is configured through environment variables.

```sh
# Which information to display.
# NOTE: If 'ascii' will be used, it must come first.
# Default: first example below
# Valid: space separated string
#
# OFF by default: shell editor wm de palette
PF_INFO="ascii title os host kernel uptime pkgs memory ip weather"

# Example: Only ASCII.
PF_INFO="ascii"

# Example: Only Information.
PF_INFO="title os host kernel uptime pkgs memory"

# A file to source before running pfetch.
# Default: unset
# Valid: A shell script
PF_SOURCE=""

# Separator between info name and info data.
# Default: unset
# Valid: string
PF_SEP=":"

# Enable/Disable colors in output:
# Default: 1
# Valid: 1 (enabled), 0 (disabled)
PF_COLOR=1

# Color of info names:
# Default: unset (auto)
# Valid: 0-9
PF_COL1=4

# Color of info data:
# Default: unset (auto)
# Valid: 0-9
PF_COL2=9

# Color of title data:
# Default: unset (auto)
# Valid: 0-9
PF_COL3=1

# Alignment padding.
# Default: unset (auto)
# Valid: int
PF_ALIGN=""

# Which ascii art to use.
# Default: unset (auto)
# Valid: string
PF_ASCII="Catppuccin"

# Where the current weather information is stored
# Default: unset
# Valid: string
PF_WEATHER="$HOME/.weather"

# The below environment variables control more
# than just 'pfetch' and can be passed using
# 'HOSTNAME=cool_pc pfetch' to restrict their
# usage solely to 'pfetch'.

# Which user to display.
USER=""

# Which hostname to display.
HOSTNAME=""

# Which editor to display.
EDITOR=""

# Which shell to display.
SHELL=""

# Which desktop environment to display.
XDG_CURRENT_DESKTOP=""
```

## Credit

- [ufetch](https://gitlab.com/jschx/ufetch): Lots of ASCII logos.
    - Contrary to the belief of a certain youtuber, `pfetch` shares **zero** code with `ufetch`. Only some of the ASCII logos were used.
