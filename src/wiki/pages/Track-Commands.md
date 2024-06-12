This is a sub-page of the main **Command Usage** page. [Click here to go back.](Command-Usage)

Key things to remember from the main page:

* You use `/apb` instead of `/ap` when running the plugin on BungeeCord
* You use `/apv` instead of `/ap` when running the plugin on Velocity
* Required arguments are marked with angle brackets - e.g. `<required>`
* Optional arguments are marked with square brackets - e.g. `[optional]`
* If you want to include spaces in arguments, you must escape the argument with quotes - e.g. `"  "`

___

### Index
*  [/ap track \<track\> `info`](#ap-track-track-info)
*  [/ap track \<track\> `editor`](#ap-track-track-editor)
*  [/ap track \<track\> `append` \<group\>](#ap-track-track-append-group)
*  [/ap track \<track\> `insert` \<group\> \<position\>](#ap-track-track-insert-group-position)
*  [/ap track \<track\> `remove` \<group\>](#ap-track-track-remove-group)
*  [/ap track \<track\> `clear`](#ap-track-track-clear)
*  [/ap track \<track\> `rename` \<new name\>](#ap-track-track-rename-new-name)
*  [/ap track \<track\> `clone` \<name of clone\>](#ap-track-track-clone-new-name)

___
#### `/ap track <track> info`  
**Permission**: aquaperms.track.info  
Displays the groups in the track.

___
#### `/ap track <track> editor`  

**Permission**: aquaperms.track.editor  
Opens a web interface to edit permissions for the specified track. After changes are saved, a command will be given that you need to run for the changes to take effect.

___

#### `/ap track <track> append <group>`  

**Permission**: aquaperms.track.append  
**Arguments**:  
* `<group>` - the group to add

Adds a group onto the end of the track.

___
#### `/ap track <track> insert <group> <position>`  
**Permission**: aquaperms.track.insert  
**Arguments**:  
* `<group>` - the group to insert
* `<position>` - the position to insert the group at

Inserts a group into a specific position within this track. A position of 1 would place it at the start of the track.

___
#### `/ap track <track> remove <group>`  
**Permission**: aquaperms.track.remove  
**Arguments**:  
* `<group>` - the group to remove

Removes a group from the track.

___
#### `/ap track <track> clear`  
**Permission**: aquaperms.track.clear  
Removes all groups from the track.

___
#### `/ap track <track> rename <new name>`  
**Permission**: aquaperms.track.rename  
**Arguments**:  
* `<new name>` - the new name for the track

Changes a track's name.

___
#### `/ap track <track> clone <new name>`  
**Permission**: aquaperms.track.clone  
**Arguments**:  
* `<new name>` - the name of the clone

Makes an exact copy of the track under a different name.

___