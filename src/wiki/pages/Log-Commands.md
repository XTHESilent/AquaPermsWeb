This is a sub-page of the main **Command Usage** page. [Click here to go back.](Command-Usage)

Key things to remember from the main page:

* You use `/apb` instead of `/ap` when running the plugin on BungeeCord
* You use `/apv` instead of `/ap` when running the plugin on Velocity
* Required arguments are marked with angle brackets - e.g. `<required>`
* Optional arguments are marked with square brackets - e.g. `[optional]`
* If you want to include spaces in arguments, you must escape the argument with quotes - e.g. `"  "`

___

### Index
*  [/ap log `recent` [user] [page]](#ap-log-recent-user-page)
*  [/ap log `search` \<query\> [page]](#ap-log-search-query-page)
*  [/ap log `notify` [on|off]](#ap-log-notify-onoff)
*  [/ap log `userhistory` \<user\> [page]](#ap-log-userhistory-user-page)
*  [/ap log `grouphistory` \<group\> [page]](#ap-log-grouphistory-group-page)
*  [/ap log `trackhistory` \<track\> [page]](#ap-log-trackhistory-track-page)

___
#### `/ap log recent [user] [page]`  
**Permission**: aquaperms.log.recent  
**Arguments**:  
* `[user]` - the name/uuid of the user to filter by
* `[page]` - the page number to view

Shows a list of recent actions.

___
#### `/ap log search <query> [page]`  
**Permission**: aquaperms.log.search  
**Arguments**:  
* `<query>` - the query to search for
* `[page]` - the page number to view

Searches for log entries matching the given query.

___
#### `/ap log notify [on|off]`  
**Permission**: aquaperms.log.notify  
**Arguments**:  
* `[on|off]` - whether to enable or disable

Toggles log notifications for the sender executing the command.

___
#### `/ap log userhistory <user> [page]`  
**Permission**: aquaperms.log.userhistory  
**Arguments**:  
* `<user>` - the user to search for
* `[page]` - the page number to view

Searches for log entries acting upon the given user.

___
#### `/ap log grouphistory <group> [page]`  
**Permission**: aquaperms.log.grouphistory  
**Arguments**:  
* `<group>` - the group to search for
* `[page]` - the page number to view

Searches for log entries acting upon the given group.

___
#### `/ap log trackhistory <track> [page]`  
**Permission**: aquaperms.log.trackhistory  
**Arguments**:  
* `<track>` - the track to search for
* `[page]` - the page number to view

Searches for log entries acting upon the given track.

___