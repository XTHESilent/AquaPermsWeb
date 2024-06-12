This is a sub-page of the main **Command Usage** page. [Click here to go back.](Command-Usage)

Key things to remember from the main page:

* You use `/apb` instead of `/ap` when running the plugin on BungeeCord
* You use `/apv` instead of `/ap` when running the plugin on Velocity
* Required arguments are marked with angle brackets - e.g. `<required>`
* Optional arguments are marked with square brackets - e.g. `[optional]`
* If you want to include spaces in arguments, you must escape the argument with quotes - e.g. `"  "`

___

### Index
*  [/ap](#ap)
*  [/ap `sync`](#ap-sync)
*  [/ap `info`](#ap-info)
*  [/ap `editor`](#ap-editor-type-filter)
*  [/ap `verbose` \<on | record | off | upload\> [filter]](#ap-verbose-onrecordoffupload-filter)
*  [/ap `verbose command` \<me | player\> \<command\>](#ap-verbose-command-meplayer-command)
*  [/ap `tree` [scope] [player]](#ap-tree-scope-player)
*  [/ap `search` [comparison] \<permission\>](#ap-search-comparison-permission)
*  [/ap `networksync`](#ap-networksync)
*  [/ap `import` \<file | code --upload\> [--replace]](#ap-import-filecode---upload---replace)
*  [/ap `export` \<file\> [--upload]](#ap-export-file--upload)
*  [/ap `reloadconfig`](#ap-reloadconfig)
*  [/ap `bulkupdate`](#ap-bulkupdate-data-type-action-action-field-action-value-constraints)
*  [/ap `translations`](#ap-translations)
*  [/ap `creategroup` \<group\> [weight] [displayname]](#ap-creategroup-name-weight-displayname)
*  [/ap `deletegroup` \<group\>](#ap-deletegroup-name)
*  [/ap `listgroups`](#ap-listgroups)
*  [/ap `createtrack` \<track\>](#ap-createtrack-name)
*  [/ap `deletetrack` \<track\>](#ap-deletetrack-name)
*  [/ap `listtracks`](#ap-listtracks)

___
#### `/ap`  
**Permission**: n/a  
Base AquaPerms command. Will print a list of the AquaPerms commands a user has permission to use, with brief information about what each command does, and what arguments it accepts.  

___
#### `/ap sync`  
**Permission**: aquaperms.sync  
Performs a refresh of all currently loaded data. If any changes have been made to the data in the storage, this command will update the copy on the server to include those changes. 

___
#### `/ap info`  
**Permission**: aquaperms.info  
Lists some information/data about AquaPerms, including debugging output, statistics, settings, and important values from the configuration. 

___
#### `/ap editor [type] [filter]`  
**Permission**: aquaperms.editor  
**Arguments**:  
* `[type]` - the types to include in the editor session. can be "all", "users", "online" or "groups"
* `[filter]` - if the session includes users (e.g. type = "all", "users" or "online"), it will exclude those whose nodes don't start with the provided filter. Groups are unaffected by this filter

Opens a web interface to edit permissions data. After changes are saved, a command will be given that you need to run for the changes to take effect.

___
#### `/ap verbose <on|record|off|upload> [filter]`  
**Permission**: aquaperms.verbose  
**Arguments**:  
* `<on|record|off|upload>` - whether to enable/disable logging, or to upload the logged output
* `[filter]` - the filter to sort the output

Controls the AquaPerms verbose logging system. This allows you to listen for all permission checks against players on the server. Whenever a permission is checked by a plugin, the check is passed onto the verbose handler.    

If your filters match the permission check, you will be notified.    

`on` will enable the system, and will send you an alert in chat when the filter is matched. `record` will do the same, however you will not be notified of checks in the chat. `off` will simply disable the checking, and `upload` will upload the first results to the web viewer, and provide you with a link.

Filters match the start of permissions or the user being checked. You can use `&` (and) and `|` (or) symbols, and `!` to negate a match. Parenthesis `( )` are also supported.   

**For example:**    
* `Luck & (essentials | worldedit)` - matches any checks made against my user starting with "essentials" or "worldedit"
* `!Luck & !anticheat` - matches any checks not against my user and not starting with "anticheat"
* `anticheat & !anticheat.check` - matches any checks starting with "anticheat" but not starting with "anticheat.check"    
  

More information can be found [**here**](Verbose)

___
#### `/ap verbose command <me|player> <command>`
**Permission**: aquaperms.vebose  
**Arguments**:
* `<me|player>` - the player to perform the verbose check on. Use `me` to select yourself
* `<command>` - the command to use for the verbose check

Controls the AquaPerms verbose logging system. This allows you to execute a command as a specific player and listen for all permission checks against the player on the server for this command.

___
#### `/ap tree [scope] [player]`  
**Permission**: aquaperms.tree  
**Arguments**:  
* `[scope]` - the root of the tree (specify `.` to include all permissions)
* `[player]` - the name of an online player to check against

Generates a tree view of permissions registered to the server. The tree is built using data exposed to the server by plugins, and expanded over time as plugins check for permissions.

All arguments are optional. The default selection is `.` (just a dot, which means all).

Scope allows you to only generate a part of the tree. For example, a scope of `aquaperms.user` will only return the branch of the tree starting with "aquaperms.user".

___
#### `/ap search [comparison] <permission>`  
**Permission**: aquaperms.search  
**Arguments**:  
* `[comparison]` - the relation between the search and the results

| Comparison | Meaning         | Function                                                                       |
|------------|-----------------|--------------------------------------------------------------------------------|
| `==`       | "Equal to"      | Default comparator - returns permissions equal to the `<permission>` searched. |
| `!=`       | "Not Equal to"  | Returns permissions not equal to the `<permission>` searched.                  |
| `~~`       | "Similar to"    | Returns permissions 'similar' to the `<permission>` searched. (SQL Style)      |
| `!~`       | "Not Similar to | Returns permissions 'not similar' to the `<permission>` searched. (SQL Style)  |

* `<permission>` - the permission to search for

Searches all users/groups for a specific permission, and returns a paginated list of all found entries. 

___
#### `/ap networksync`  
**Permission**: aquaperms.sync  
Refreshes all cached data with the storage provider, and then uses the plugins Messaging Service (if configured) to "ping" all other connected servers and request that they sync too.

___
#### `/ap import <file|code --upload> [--replace]`  
**Permission**: aquaperms.import  
**Arguments**:  
* `<file>` - the file to import from
* `<code> --upload` - the code to web-import from
* `[--replace]` - if included, will overwrite and replace the existing permissions with the import. If not, they will merge.


Imports data into AquaPerms from a file or from the web. If a file, it must be a JSON GZIP type file, exported from Luckperms v5. If from the web, the code must be generated when exporting with the `--upload` flag. The file is expected to be in the plugin directory. When importing a file, the extension `.json.gz` should be included in the name of the import file. When importing a file or web-export, the `--replace` flag may be added to the end of the command to overwrite and replace the existing permissions setup. If the `--replace` flag is not included, the existing permissions setup will be merged with the imported one.

___
#### `/ap export <file|--upload>`  
**Permission**: aquaperms.export  
**Arguments**:  
* `<file>` - the file to export to
* `<--upload>` - if added, will export to the web and provide a code for web-based imports.
* `[--without-users]` - if added, will export only all the group data. The export will not include any user data.
* `[--without-groups]` - if added, will export only all the user data. The export will not include any group data.

Exports data from AquaPerms into a file or into web-based datastorage. This file can either be used as a backup, or used to move data between AquaPerms installations. The web-based export will expire and should not be used as a backup. The file and the web-based export can be re-imported using the import command. The generated file will be in the plugin directory.

___
#### `/ap reloadconfig`  
**Permission**: aquaperms.reloadconfig  
Reloads some values from the configuration file. Not all entries are reloaded by this command, and some require a full server reboot to take effect. (storage settings, for example)

___
#### `/ap bulkupdate <data type> <action> [action field] [action value] [constraints...]`  
**Permission**: **Console Only**  
**Arguments**:  
* `<data type>` - the type of data being changed. (can be `all`, `users` or `groups`)
* `<action>` - the action to perform on the data. (can be `update` or `delete`)
* `[action field]` - the field to act upon. only required for update actions. (can be `permission`, `server` or `world`)
* `[action value]` - the value to replace with. only required for update actions
* `[constraints]` - the constraints required for the update

Allows you to perform a bulk modification to all permission data. A detailed guide on how to use this command can be found [here](Bulk-Editing).

___
#### `/ap translations`  
**Permission**: aquaperms.translations  
Shows information about loaded translations, and allows installation of community provided translation bundles.

___
#### `/ap creategroup <name> [weight] [displayname]`  
**Permission**: aquaperms.creategroup  
**Arguments**:  

* `<name>` - the name of the group
* `[weight]` - the weight of the group
* `[displayname]` - the displayname of the group

Creates a new group.

___
#### `/ap deletegroup <name>`  
**Permission**: aquaperms.deletegroup  
**Arguments**:  
* `<name>` - the name of the group

Permanently deletes a group.

___
#### `/ap listgroups`  
**Permission**: aquaperms.listgroups  
Displays a list of all current groups.

___
#### `/ap createtrack <name>`  
**Permission**: aquaperms.createtrack  
**Arguments**:  
* `<name>` - the name of the track

Creates a new track.

___
#### `/ap deletetrack <name>`  
**Permission**: aquaperms.deletetrack  
**Arguments**:  
* `<name>` - the name of the track

Permanently deletes a track.

___
#### `/ap listtracks`  
**Permission**: aquaperms.listtracks  
Displays a list of all current tracks.

___
