This is a sub-page of the main **Command Usage** page. [Click here to go back.](Command-Usage)

Key things to remember from the main page:

* You use `/apb` instead of `/ap` when running the plugin on BungeeCord
* You use `/apv` instead of `/ap` when running the plugin on Velocity
* Required arguments are marked with angle brackets - e.g. `<required>`
* Optional arguments are marked with square brackets - e.g. `[optional]`
* If you want to include spaces in arguments, you must escape the argument with quotes - e.g. `"  "`

___

### Index
*  [/ap user \<user\> `info`](#ap-user-user-info)
*  [/ap user \<user\> `permission`](Permission-Commands)
*  [/ap user \<user\> `parent`](Parent-Commands)
*  [/ap user \<user\> `meta`](Meta-Commands)
*  [/ap user \<user\> `editor`](#ap-user-user-editor)
*  [/ap user \<user\> `promote` \<track\> [context...]](#ap-user-user-promote-track-context-flags)
*  [/ap user \<user\> `demote` \<track\> [context...]](#ap-user-user-demote-track-context-flags)
*  [/ap user \<user\> `showtracks`](#ap-user-user-showtracks)
*  [/ap user \<user\> `clear` [context...]](#ap-user-user-clear-context)
*  [/ap user \<user\> `clone` \<user\>](#ap-user-user-clone-user)

___
#### `/ap user <user> info`  
**Permission**: aquaperms.user.info  
Displays information about a user, including their username, primary group, parents, and current contexts.

___
#### `/ap user <user> editor`  
**Permission**: aquaperms.user.editor  
Opens a web interface to edit permissions for the specified group. After changes are saved, a command will be given that you need to run for the changes to take effect.

___
#### `/ap user <user> promote <track> [context...] [flags...]`  
**Permission**: aquaperms.user.promote  
**Arguments**:  
* `<track>` - the track to promote along
* `[context...]` - the [contexts](Context) to promote in
**Flags**:
* `[--dont-add-to-first]` - the command will fail to run if the user doesn't have parent groups on said track
* `[-s]` - silent, don't print the user progress on the track

This command will promote a user along a track. Firstly, the command will check to see if the user is on the track specified in the given contexts. If the user is not on the track, they will be added to the first group on the track unless a flag is used. If they are on the track in more than one place, the command will fail. In all other cases, the user will be promoted up the track, and will be removed from the existing group. If the track action affects their primary group, that will be updated too.

___
#### `/ap user <user> demote <track> [context...] [flags...]`  
**Permission**: aquaperms.user.demote  
**Arguments**:  
* `<track>` - the track to demote along
* `[context...]` - the [contexts](Context) to demote in
**Flags**:
* `[--dont-remove-from-first]` - the command will fail to run if the user is on the first position on the track
* `[-s]` - silent, don't print the user progress on the track

This command will demote a user along a track. Firstly, the command will check to see if the user is on the track specified in the given contexts. If the user is not on the track, or on the track in more than one place, the command will fail. If not, the user will be demoted down the track, and will be removed from the existing group. If the track action affects their primary group, that will be updated too.

___
#### `/ap user <user> showtracks`  
**Permission**: aquaperms.user.showtracks  
Displays a list of all of the tracks a user is currently on.

___
#### `/ap user <user> clear [context...]`  
**Permission**: aquaperms.user.clear  
**Arguments**:  
* `[context...]` - the [contexts](Context) to filter by

Clears the user's permissions, parent groups and meta.

___
#### `/ap user <user> clone <user>`  
**Permission**: aquaperms.user.clone  
**Arguments**:  
* `<user>` - the name of the other user

Clones the users data onto another user.

___
