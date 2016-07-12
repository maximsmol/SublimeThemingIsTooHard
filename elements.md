Element | Where to look for an example
------- | ----------------------------
Autocomplete | Enable `auto_complete` in ST's preferences; type `hello hell`; on new line: `hel`; press `ctrl-space` (issue `auto_complete` command)
Button | Open `Find dialog` element; look at the `Find` button at the bottom-right
Drop down button | Open `Text field` element; look at the right side of the `Text field` element
Find dialog | Select `Find -> Find...` (*nix `super-F`, Windows `ctrl-F`) in the menu bar; look at the panel at the bottom
Find in files dialog | Select `Find -> Find in Files...` (*nix `super-shift-F`, Windows `ctrl-shift-F`) in the menu bar; look at the panel at the bottom
Fold buttons | Enable `gutter` in ST's preference; create a file `tmp.js` (with a source code syntax); type `{`; on new line: `a`; on new line `b`; on new line `}`; look at the arrow in the gutter, to the left of `{`. *Appearance depends on the state of the arrow (changed by clicking it)*
Icon button | Open `Find dialog` element; look at the buttons on the left of `Find dialog` element
Layout border | Select `View -> Layout -> Grid: 4` (*nix `alt-super-5`, Windows `alt-ctrl-5`) in the menu bar; look at the border separating the 4 editing areas
Mini quick panel | Select `Tools -> Command Palette...` (*nix `super-shift-P`, Windows `ctrl-shift-P`) in the menu bar; look at the panel at the top
Minimap | Select `View -> Show Minimap` in the menu bar; look at the transparent overlay on the right
Quick panel | Select `Goto -> Goto anything...` (*nix `super-P`, Windows `ctrl-P`) in the menu bar; look at the the panel at the top
Replace dialog | Select `Find -> Replace...` (*nix `super-alt-F`, Windows `ctrl-alt-F`) in the menu bar; look at the panel at the bottom
Scroll bar | Create a file bigger in height and width than the ST window; look at the right, bottom and bottom-right while scrolling. *Appearance depends on the `overlay_scroll_bars` property*
Sidebar | Select `View -> Side Bar -> Show Side Bar` in the menu bar; look at the the panel on the left
Status bar | Select `View -> Show Status Bar` in the menu bar; look at the panel on the bottom
Tabs | Select `View -> Show Tabs` in the menu bar; look at the tab listing at the top
Text field | Open `Find dialog` element; look at the text field at the bottom
Tooltip | Open `Find dialog` element; for a couple of seconds mouse over any of the buttons with icons on the left of `Find dialog` element

Some groups of elements are affected by a lot of different properties

Element groups | Contents
-------------- | --------
Group: panels | `Find dialog`, `Find in files dialog`, `Replace dialog`, `Quick panel`, `Mini quick panel`, and the console (select `View -> Show Console` (*nix `ctrl-backtick`, Windows `ctrl-backtick`) in the menu bar; look at the the panel at the bottom)

*P.S. All given instructions assume the default configuration of ST*
