Placeholder text plugin for TinyMCE
===================================

This plugin brings HTML5 placeholder attribute functionality for the TinyMCE editor.

Usage
-----

* Add the plugin script to the page
* Add "placeholder" to tinymce config plugins array.
* Add a placeholder attribute to the textarea as usual or set placeholder property in editor settings.

Note: This plugin is not compatible with TinyMCE inline mode. It only works in classic mode.

Installation with bower
-------
To install plugin using bower use command <code>bower install tinymce-placeholder-attribute</code>

Dynamically load the plugin
-------
Most people nowaday will most probably load TinyMCE via CDN, e.g. like this in their index.htm head:

`<script src='//cdn.tinymce.com/4/tinymce.min.js'></script>`

If you now want to add this plugin, then you must add the plugin to the tinymce.configuration plugin list with a leading minus and then you can dynamically load the plugin from another location afterward:

    tinymce.init({
      selector: "#textareaid',
      plugins: [
        'advlist autolink lists link image -placeholder'   // see the minus before placeholder plugin name!
      ]
    })
    .then(function() {
      tinymce.PluginManager.load('placeholder', '/js/tinymce/plugins/tinymce-placeholder.plugin.js');
    });


Example
-------

Tinymce Plugins Array:
plugins: "fullscreen placeholder"

Textarea:
`<textarea class="tinymce" placeholder="Hello World!"></textarea>`

Styling the placeholder label
--------------------------------

By default, this plugin styles the placeholder with the following attributes:

```js
{
  style: {
    position: 'absolute',
    top:'5px',
    left:0,
    color: '#888',
    padding: '1%',
    width:'98%',
    overflow: 'hidden',
    'white-space': 'pre-wrap'
  }
}
```

You can replace this styling by providing a `placeholder_attrs` section in your TinyMCE config...

```js
tinyMCE.init({
  plugins: 'placeholder',
  placeholder_attrs: // (new value for the above object...)
});
```

Or alternatively, you can override specific properties of the default CSS by providing the `!important` directive along in your CSS property for the label...

```css
.mce-edit-area {
  label {
    color: #A9A9A9 !important; /* Override text color */
    left: 5px !important; /* Override left positioning */
  }
}
```
