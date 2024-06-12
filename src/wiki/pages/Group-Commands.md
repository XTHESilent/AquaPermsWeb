This is a sub-page of the main **Command Usage** page. [Click here to go back.](Command-Usage)

Key things to remember from the main page:

* You use `/apb` instead of `/ap` when running the plugin on BungeeCord
* You use `/apv` instead of `/ap` when running the plugin on Velocity
* Required arguments are marked with angle brackets - e.g. `<required>`
* Optional arguments are marked with square brackets - e.g. `[optional]`
* If you want to include spaces in arguments, you must escape the argument with quotes - e.g. `"  "`

___

### Index
*  [/ap group \<group\> `info`](#ap-group-group-info)
*  [/ap group \<group\> `permission`](Permission-Commands)
*  [/ap group \<group\> `parent`](Parent-Commands)
*  [/ap group \<group\> `meta`](Meta-Commands)
*  [/ap group \<group\> `editor`](#ap-group-group-editor)
*  [/ap group \<group\> `listmembers` [page]](#ap-group-group-listmembers-page)
*  [/ap group \<group\> `setweight` \<weight\>](#ap-group-group-setweight-weight)
*  [/ap group \<group\> `setdisplayname` \<name\> [context...]](#ap-group-group-setdisplayname-name)
*  [/ap group \<group\> `showtracks`](#ap-group-group-showtracks)
*  [/ap group \<group\> `clear` [context...]](#ap-group-group-clear-context)
*  [/ap group \<group\> `rename` \<new name\>](#ap-group-group-rename-new-name)
*  [/ap group \<group\> `clone` \<name of clone\>](#ap-group-group-clone-new-name)

___
#### `/ap group <group> info`  
**Permission**: aquaperms.group.info  
Displays information about a group.

___
#### `/ap group <group> editor`  
**Permission**: aquaperms.group.editor  
Opens a web interface to edit permissions for the specified group. After changes are saved, a command will be given that you need to run for the changes to take effect.

___
#### `/ap group <group> listmembers [page]`  
**Permission**: aquaperms.group.listmembers  
**Arguments**:  
* `[page]` - the page to view

Gets a list of the other users/groups which inherit directly from this group.

___
#### `/ap group <group> setweight <weight>`  
**Permission**: aquaperms.group.setweight  
**Arguments**:  
* `<weight>` - the weight to set

Sets the groups weight value, which determines the order in which groups will be considered when accumulating a users permissions. Higher value = higher weight.

___
#### `/ap group <group> setdisplayname <name>`  
**Permission**: aquaperms.group.setdisplayname  
**Arguments**:  
* `<name>` - the name to set
* `[context...]` - the [contexts](Context) to set the display name in

Sets the groups display name. This can effectively be used as an "alias" for the group.

___
#### `/ap group <group> showtracks`  
**Permission**: aquaperms.group.showtracks  
Displays a list of all of the tracks a group is currently on.

___
#### `/ap group <group> clear [context]`  
**Permission**: aquaperms.group.clear  
**Arguments**:  
* `[context...]` - the [contexts](Context) to filter by

Clears the group's permissions, parent groups and meta.

___
#### `/ap group <group> rename <new name>`  
**Permission**: aquaperms.group.rename  
**Arguments**:  
* `<new name>` - the new name for the group

Changes a group's name. Note that any members of this group will not know about the change, and will still point to the old group name. If you wish to update this, you'll need to use the bulk change feature to update the existing entries.

___
#### `/ap group <group> clone <new name>`  
**Permission**: aquaperms.group.clone  
**Arguments**:  
* `<new name>` - the name of the clone

Makes an exact copy of the group under a different name.

___
