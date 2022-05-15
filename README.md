# zen-mod-polybar

Script to toggle brightness of a screen to 0 or 1 to be focused on work

## Dependencies
- xrandr

## Configuration

You can modify one variable in `focus.sh`

```sh
# Screen to be toggled
# Run `xrandr -q` to get output name
readonly SCREEN="DisplayPort-1"
```

## Usage

The script expects parameters :
 - `--toggle` : Toggle brightness of the screen to 0 or 1
 - `--get-current` : Get current brightness and display an icon
    - When brightness is > 0 : ![Screen on](./.assets/screen_on.png)
    - When brightness is set to 0 : ![Screen off](./.assets/screen_off.png)


Example module for polybar

```ini
[module/focus]
type = custom/script
interval = 1
exec = ~/.config/polybar/scripts/focus.sh --get-current
click-left = ~/.config/polybar/scripts/focus.sh --toggle
```