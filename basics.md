### If you don't understand the meaning of a term, consult `glossary.md`

# Starting a new theme

`{packages}` is the location of your ST's `Packages` folder. It can be opened by choosing `Preferences -> Browse Packages...` in the menu bar.

`{themeName}` is the name of your theme

**todo: add the instructions for taking `Default.sublime-theme` out of ST**

1. Copy the contents of [`Default.sublime-theme`](default/Default.sublime-theme) into a new file at `{packages}/Theme - {themeName}/{themeName}.sublime-theme`.
1. Open ST's preferences (default shortcut is: `super+,` on *nix; and `ctrl+,` on Windows) and put the line `"theme": "{themeName}.sublime-theme"` there. This will change the current theme to your new theme file.

# Theming basics

* Themes are defined in `.sublime-theme` files.
* Theme files are in [JSON](http://www.json.org/), but they support comments: `//` and `/**/`; and allow for trailing commas in dictionaries and arrays.
* Every theme file has to represent an array of rules.

# Rules

The following keys are valid for any selector:

Key | Type | Role
--- | ---- | ----
class | string | Specifies the class
attributes | array of string | Specifies the attributes. An element matches iff it matches every specified attribute
settings | array of string | Specifies that a rule is applied iff every preference key in the array is set in the ST's preferences. This behavior can be inverted, if the preference key is prefixed by a `!`. **todo: when is a key set?**
parents | array of rules not specifying customizations **todo: what if they contain customizations?** | Specifies that a rule is applied iff the target element is a child (**todo: can be an indirect child?**) of the target element of the rule in the array **todo: what if multiple rules are in the array?**

Rule `A` overrides rule `B`, defined in the same file iff `B` is defined prior to `A` in a given `.sublime-theme` file.
Rule `A` overrides rule `B`, in another file iff `A`'s file is prior to `B`'s in the file priority order.

File priority order **todo: is it so?**:

1. {packages}/Theme - {themeName}/{themeName}.sublime-theme
1. {packages}/User/{themeName}.sublime-theme

{themeName} is the theme chosen in the ST's preferences

*P.S. iff <=> if and only if*

# Example

```js
[ // Root array

	{ // Begining of a rule

		"class": "sidebar_label", // Target element's class is `sidebar_label`
		// This rule's selector is `sidebar_label`

		"color": [255, 255, 255] // Specifying the `color` customization to the value of `[255, 255, 255]`
	}, // End of a rule

	{
		"class": "sidebar_label",
		"settings": ["sidebar_label_red_enable"], // Apply the rule only when `sidebar_label_red_enable` property is set
		"parents": // Start of the array specifying the element's parents
		[
			{
				"class": "tree_row", // This parent's class is `tree_row`
				"attributes": ["expandable", "!hover"] // This parent's attributes are `expanded` *and* not `!hover`
				// This parent's selector is `tree_row(expanded, !hover)`
			}
		],
		// This rule's selector is `sidebar_label <- tree_row(expanded, !hover)`

		"color": [255, 0, 0]
	},

	/*
	This theme specifies:
	a `sidebar_label` has `color` equal to `[255, 255, 255]`;
	a `sidebar_label` in a not `hover`ed over, `expandable` `tree_row` has `color` equal to `[255, 0, 0]` iff `sidebar_label_red_enable` property is set;
	the second rule will *override* the first one, based on the order of the definition
	*/
]
```

# Widgets

If `{packages}/Theme - {themeName}/Widget - {themeName}.sublime_settings` file exists, then preferences defined in it override preferences defined in the usual locations, but *only* for elements, that are not the main editor view.

This behavior can be used to define a separate color scheme for regex-enabled find dialog's text fields.

A common practice is to create such a color scheme in `{packages}/Theme - {themeName}/Widget - {themeName}.tmTheme`

# File sidebar icons

File sidebar icons depend on the type of the file (on the color scheme `scope` of the file) and are looked for in the `{packages}/Theme - {themeName}/icons/` folder. Based on the `Icon ({iconName}).tmPreferences` files. The default versions of these `icon` specifications are located in the `/fileIcons/` folder of this repository.

Each [XML plist](http://www.apple.com/DTDs/PropertyList-1.0.dtd) `Icon ({iconName}).tmPreferences` file contains a dictionary with the following keys:

Key | Type | Description
--- | ---- | ---------
`scope` | string, comma-separated list | Specifies targeted files by scope (the same scopes are used in color schemes)
`settings` | dictionary | Contains only the setting: `icon`
`settings`/`icons` | string | Contains the icon name, which specifies the icon file as in: `{packages}/Theme - {themeName}/icons/{iconName}.png`

Icon file path is filled in as `layer0.texture` in `icon_file_type` class
