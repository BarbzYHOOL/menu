[![Slack Room][slack-badge]][slack-link]

# Menu

Create interactive prompt menus.

## Install

With [fisherman]

```
fisher menu
```

## Usage

```
menu 1 2 3
> 1  
  2
  3
```

## Options

### `menu_cursor_glyph`

Set cursor character.

Default: `>`.

### `menu_hover_item_style`

Set hover item style.

Default: None.

### `menu_multiple_choice`

Enable multiple choice mode.

Default: `false`.


### `menu_selected_item_style`

Set selected item style.

Default: None.

### `menu_checked_glyph`

Checked item glyph.

Default: `[x]`

### `menu_unchecked_glyph`

Unchecked item glyph.

Default: `[ ]`

### `menu_selected_index`

Use `menu_selected_index` to retrieve the selected item index from `$argv`.

### Example

```fish
## Menu list
set -l items "Batman" "Flash" "Superman" "Aquaman"

## Menu options
set -l menu_hover_item_style -o black -b yellow
set -l menu_cursor_glyph ▶
set -l menu_cursor_glyph_style -o

## Question before menu with 2 seconds timer
set -l choice_timer 2
echo "Choose a hero in $choice_timer seconds:"

for second in (seq $choice_timer)[-1..1]
    printf "$second\n"
    sleep 1
end

## Menu
menu $items

## Result
echo "This is your choice: $items[$menu_selected_index]"

if test $items[$menu_selected_index] = "Flash"
  echo "Good choice"
else
  echo "Bad choice"
end
```

[slack-link]: https://fisherman-wharf.herokuapp.com
[slack-badge]: https://fisherman-wharf.herokuapp.com/badge.svg
[fisherman]: https://github.com/fisherman/fisherman
