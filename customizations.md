# group: container

Container elements' background can be stylized. They can't contain text.

Each container has a number of layers, which are drawn on top of each other in an order respecting their number (`layer0` is drawn first, `layer1` is drawn second etc.).

To draw a layer means to draw it's texture, after additionally applying the specified tint to it.

See also:
* `Textures`   at [`basics.md`](basics.md)
* `Borders`    at [`basics.md`](basics.md)
* `Animations` at [`basics.md`](basics.md)

## Layer customizations

Customization       | Type                                                                          | Specifies                                                                     | Value if not defined
------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | --------------------
layerN.texture      | string; path relative to ST's data folder; or '' if texture should be plain   | The layer's image                                                             | `''` (empty string)
layerN.opacity      | floating point                                                                | The layer's opacity                                                           | `0.0` **invisible**
layerN.tint         | array; color; RGBA                                                            | The tint of the texture                                                       | `[?, ?, ?, 255]` invisible
layerN.draw_center  | boolean                                                                       | If the texture's center region is drawn                                       | `true`
layerN.inner_margin | array of integers; [left & right, bottom & top] or [left, top, right, bottom] | What part of the texture, starting from respective sides is *not* it's center | `[0, 0]` or `[0, 0, 0, 0]` which mean the same
layerN.repeat       | boolean                                                                       | If the texture should be repeated rather than stretched                       | `false`

*P.S. ST's data folder is the one, which contains the `Packages` folder. The `Packages` folder can be accessed by selecting `Preferences -> Browse Packages...` in the menu bar*

## Other container options

Customization  | Type                                                                          | Specifies
-------------- | ----------------------------------------------------------------------------- | ---------
content_margin | array of integers; [left & right, bottom & top] or [left, top, right, bottom] | The (additional) distance from the edges of the container to it's children

See also: `Negative margins and paddings` at [`basics.md`](basics.md)

# group: text

Text elements are the ones that contain monotone text, and no other elements. Their background cannot be stylized, and they have no `layerN` properties, if such a property is used, ST will complain about it into the console.

Customization | Type                           | Specifies                | Value if not defined
------------- | ------------------------------ | ------------------------ | --------------------
color         | array of integers; color; RGBA | Color of the text        | `[0, 0, 0]` or `[0, 0, 0, 255]` which mean the same
font.face     | string                         | Font used to render text | **todo: add**
font.size     | floating point                 | Text size                | depends on the element (seems to be 12 for most elements) **todo: add listing of elements**
font.bold     | boolean                        | If text is bold          | `false`
font.italic   | boolean                        | If text is italic        | `false`

# group: fgbg

Fg-bg elements contain text styling of which depends on some parameter, and no other elements.
Their background cannot be stylized, and they have no `layerN` properties, if such a property is used, ST will complain about it into the console.
Fg-bg elements inherit font from ST's preferences.

The autocomplete panel, the quick panel and the mini quick panel style normal text, text in the currently selected entry and text which matches text in the search field differently.

Customization     | Type                           | Specifies                                   | Value if not defined
----------------- | ------------------------------ | ------------------------------------------- | --------------------
fg                | array of integers; color; RGBA | color of normal text                        | **todo: add**
selected_fg       | array of integers; color; RGBA | color of text in selected elements          | **todo: add**
bg                | array of integers; color; RGBA | **todo: add**                               | **todo: add**
selected_bg       | array of integers; color; RGBA | **todo: add**                               | **todo: add**
match_fg          | array of integers; color; RGBA | color of matching text                      | **todo: add**
selected_match_fg | array of integers; color; RGBA | color of matching text in selected elements | **todo: add**

# Miscellaneous

