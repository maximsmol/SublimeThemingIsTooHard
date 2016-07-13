# group: container

Containers are elements, whose background can be stylized. They can't contain text.

Each container has a number of layers, which are drawn on top of each other in an order respecting their number (`layer0` is drawn first, `layer1` is drawn second etc.).

To draw a layer means to draw it's texture, after additionally applying the specified tint to it.

See also: `Textures` at [`basics.md`](basics.md)
See also: `Borders` at [`basics.md`](basics.md)
See also: `Animations` at [`basics.md`](basics.md)

## Layer customizations

Customization       | Type                                                                          | Specifies
------------------- | ----------------------------------------------------------------------------- | -----------
layerN.texture      | string; path relative to ST's config folder; or '' if texture should be plain | The layer's image
layerN.opacity      | floating point                                                                | The layer's opacity
layerN.tint         | array; color; RGBA                                                            | The tint of the texture
layerN.draw_center  | boolean                                                                       | If the texture's center region is drawn
layerN.inner_margin | array of integers; [left & right, bottom & top] or [left, top, right, bottom] | What part of the texture, starting from respective sides is *not* it's center
layerN.repeat       | boolean                                                                       | If the texture should be repeated rather than stretched

Customization       | Value if not defined
------------------- | --------------
layerN.texture      | `''` (empty string)
layerN.opacity      | `0.0` **invisible**
layerN.tint         | `[?, ?, ?, 255]` invisible
layerN.draw_center  | `true`
layerN.inner_margin | `[0, 0]` or `[0, 0, 0, 0]` which mean the same
layerN.repeat       | `false`

*P.S. ST's config folder is the one, which contains the `Packages` folder. The `Packages` folder can be accessed by selecting `Preferences -> Browse Packages...` in the menu bar*

## Other container options

Customization  | Type                                                                          | Specifies
-------------- | ----------------------------------------------------------------------------- | ---------
content_margin | array of integers; [left & right, bottom & top] or [left, top, right, bottom] | The (additional) distance from the edges of the container to it's children

See also: `Negative margins and paddings` at [`basics.md`](basics.md)

# group: text

Text elements are the ones that contain monotone text, and no other elements. Their background cannot be stylized, and they have no `layerN` properties, if such a property is used, ST will complain about it into the console.

Customization | Type                           | Specifies
------------- | ------------------------------ | -----------
color         | array of integers; color; RGBA | Color of the text
font.face     | string                         | Font used to render text
font.size     | integer                        | Text size
font.bold     | boolean                        | If text is bold
font.italic   | boolean                        | If text is italic

Customization | Value if not defined
------------- | -------------
color         | `[0, 0, 0]` or `[0, 0, 0, 255]` which mean the same
font.face     | **todo: add**
font.size     | depends on the element (seems to be 12 for most elements) **todo: add listing of elements**
font.bold     | `false`
font.italic   | `false`

# group: fgbg

Fg-bg group elements contain text styling of which depends on some parameter, and no other elements. Their background cannot be stylized, and they have no `layerN` properties, if such a property is used, ST will complain about it into the console.

The autocomplete panel, the quick panel and the mini quick panel style normal text, text in the currently selected entry and text which matches text in the search field differently.

Customization     | Type                           | Specifies
----------------- | ------------------------------ | -----------
fg                | array of integers; color; RGBA | color of normal text
selected_fg       | array of integers; color; RGBA | color of text in selected elements
bg                | array of integers; color; RGBA | **todo: add**
selected_bg       | array of integers; color; RGBA | **todo: add**
match_fg          | array of integers; color; RGBA | color of matching text
selected_match_fg | array of integers; color; RGBA | color of matching text in selected elements

Customization     | Value if not defined
----------------- | --------------
fg                | **todo: add**
selected_fg       | **todo: add**
bg                | **todo: add**
selected_bg       | **todo: add**
match_fg          | **todo: add**
selected_match_fg | **todo: add**

# Miscellaneous

