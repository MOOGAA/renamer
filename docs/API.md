<a name="module_renamer"></a>

## renamer
Rename files in bulk.


* [renamer](#module_renamer)
    * [Renamer](#exp_module_renamer--Renamer) ⏏
        * [.rename(options)](#module_renamer--Renamer+rename)
        * ["replace-result"](#module_renamer--Renamer+event_replace-result)

<a name="exp_module_renamer--Renamer"></a>

### Renamer ⏏
**Kind**: Exported class  
<a name="module_renamer--Renamer+rename"></a>

#### renamer.rename(options)
A synchronous method to rename files in bulk.

**Kind**: instance method of [<code>Renamer</code>](#exp_module_renamer--Renamer)  
**Emits**: [<code>replace-result</code>](#module_renamer--Renamer+event_replace-result)  

| Param | Type | Description |
| --- | --- | --- |
| options | <code>object</code> | The renamer options |
| [options.files] | <code>Array.&lt;string&gt;</code> | One or more glob patterns or filenames to process. |
| [options.dryRun] | <code>boolean</code> | Set this to do everything but rename the file. You should always set this flag until certain the output looks correct. |
| [options.force] | <code>boolean</code> | If a target path exists, renamer will stop. With this flag set the target path will be overwritten. The main use-case for this flag is to enable changing the case of files on case-insensitive systems. Use with caution. |
| [options.plugin] | <code>Array.&lt;string&gt;</code> | One or more replacer plugins to use, set the `--plugin` option multiple times to build a chain. For each value, supply either: a) a path to a plugin file b) a path to a plugin package c) the name of a plugin package installed globally or in the current working directory (or above) or d) the name of a built-in plugin, either `default` or `index`. The default plugin chain is `default` then `index`, be sure to set `-p default -p index` before your plugin if you wish to extend default behaviour. |
| [options.find] | <code>sting</code> \| <code>RegExp</code> | Optional find string (e.g. `one`) or regular expression literal (e.g. `/one/i`). If omitted, the whole filename will be matched and replaced. |
| [options.replace] | <code>string</code> | The replace string. If omitted, defaults to a empty string. |
| [options.pathElement] | <code>string</code> | The path element to rename, valid values are `base` (the default), `name` and `ext`. For example, in the path `pics/image.jpg`, the base is `image.jpg`, the name is `image` and the ext is `.jpg`. |
| [options.indexFormat] | <code>string</code> | The format of the number to replace `{{index}}` with. Specify a standard printf format string, for example `%03d` would yield 001, 002, 003 etc. Defaults to `%d`. |
| [options.indexRoot] | <code>string</code> | The initial value for `{{index}}`. Defaults to 1. |

<a name="module_renamer--Renamer+event_replace-result"></a>

#### "replace-result"
Emitted just before each file is processed.

**Kind**: event emitted by [<code>Renamer</code>](#exp_module_renamer--Renamer)  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| from | <code>string</code> | The filename before rename. |
| to | <code>string</code> | The filename after rename. |
| renamed | <code>boolean</code> | True if the file was renamed. |

