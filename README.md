# Wakanda Plugins Essential

> A walkthrough on elements composing a wakanda plugin and how it should be written.


## Package.json
 **Mandatory** file, it contains metadata that describes the plugin, it should be placed at the root of the plugin directory.

Key | Mandatory | Type | Description
---- |:--------:| ---- | -------
`name` | Yes | `string` | The name of the plugin.
`main` | No | `string` | Entry point to the plugin, if not found wakanda will look for an index.js or main.js.
`description` | Yes | `string` | Description of what your plugin does.
`version` | Yes | `string` | The plugin version .
`author` |No | `string`| The author of plugin.
`license` |No | `string` | Check [npm's documentation](https://docs.npmjs.com/files/package.json#license) for details.
`location` |No | `string` |Where the plugin will be available, two option are available: `codeEditorToolbar` and `solutionTreeView`.
`icon` |No | `string` | Path to the used icon.
`label` |No | `string` | Title of the plugin to be displayed.
`hint` |No | `string` | 	Additional information to display when the cursor moves over the button.
`repository` |No | `string` | URL of a git repository.
`keywords` |No | `array` | Array of **keywords**  to find the plugin easily.
`compatibleVersions` |Yes | `object` |Wakanda studio compatible version with the plugin.
`triggers` |No | `array of objects` | A plugin is not loaded immediately, this array defines when the plugin has to be activated. Wakanda supports  the following triggers  : [studioEvent](http://doc.wakanda.org/), [command](http://doc.wakanda.org/) and [language](http://doc.wakanda.org/)  .
`menus` |No | `array of objects` | Use this property if you want to define a menu. Wakanda supports multiple types of menus : [menu-bar](http://doc.wakanda.org/),[editor-menu](http://doc.wakanda.org/),[context-menu](http://doc.wakanda.org/). The menu can also be stored as a json file in the root of your plugin as [menu.json](http://doc.wakanda.org/)
`keybindings` |No | `array of objects` | Define shortcuts for the plugin command.The keymaps can also be stored as a json file in the root of your plugin [keybinding.json](http://doc.wakanda.org/)
`snippets` |No | `array of objects` |Add snippets of code by defining the **path** to a snippets.json file and a **target** (js,html,...) check [wakanda snippets](http://doc.wakanda.org/) for details and examples
`dependencies` |No | `object` | Dependencies your extensions needs. Check [npm's  dependencies](https://docs.npmjs.com/files/package.json#dependencies) for details.
`devDependencies` |No | `object` | The same as [npm's devDependencies](https://docs.npmjs.com/files/package.json#devdependencies).

[here](https://github.com/intissarMez/wakanda-plugin/blob/master/package.json) is an example of package.json

##  main.js
 Entry point of a wakanda plugin. In this file, `wakanda-studio-api` is imported and an entry function `init()` will handle all the commands, check [wakanda main](http://doc.wakanda.org/) for details.

You can check a full example of wakanda plugin [here](https://github.com/intissarMez/wakanda-plugin)
