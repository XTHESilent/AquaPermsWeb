Command usage is printed to the console/chat whenever invalid arguments are provided. **Simply typing /ap** will list all commands a user has permission to use.

If the only thing returned when you type a command is the plugin version, you do not have permission to use any of the commands. You need to use the server console to [give yourself access to AquaPerms commands first](Usage#granting-full-access-to-modify-permissions).

### Aliases
A list of aliases for each platform are listed below. Each command works in exactly the same manner, so you can use whichever you prefer.

| Bukkit / Sponge / Fabric / Forge / Nukkit | BungeeCord         | Velocity             |
|-------------------------------------------|--------------------|----------------------|
| `/ap`                                     | `/apb`             | `/apv`               |
| `/aquaperms`                              | `/aquapermsbungee` | `/aquapermsvelocity` |
| `/permissions` (*deprecated*)             |                    |                      |
| `/perms` (*deprecated*)                   |                    |                      |
| `/perm` (*deprecated*)                    |                    |                      |

**`Important:`** The command aliases are different on BungeeCord and Velocity. This is so you can choose where the command is executed. If the aliases were the same, you would never be able to control AquaPerms on a backend server as the command would always be handled by the proxy!

If you are using Bukkit/Spigot, by default, all users with OP have access to AquaPerms commands. You can change this in the config.

# Overview
#### Arguments Key:
* `<required>` - you *must* specify this argument when running the command
* `[optional]` - you do not need to specify this argument. a default will be used if not given.

If you want to include spaces in arguments, you must escape the argument with quotes. `"  "`

The alias used below (`/ap`) can be exchanged for any of the ones listed in the aliases section above.

### General commands
General commands used to operate AquaPerms functions.

*  [/ap](General-Commands#ap)
*  [/ap `sync`](General-Commands#ap-sync)
*  [/ap `info`](General-Commands#ap-info)
*  [/ap `editor`](General-Commands#ap-editor-type)
*  [/ap `verbose` \<on | record | off | upload\> [filter]](General-Commands#ap-verbose-onrecordoffupload-filter)
*  [/ap `tree` [scope] [player]](General-Commands#ap-tree-scope-player)
*  [/ap `search` [comparison] \<permission\>](General-Commands#ap-search-comparison-permission)
*  [/ap `networksync`](General-Commands#ap-networksync)
*  [/ap `import` \<file | code --upload\> [--replace]](General-Commands#ap-import-filecode---upload---replace)
*  [/ap `export` \<file\> [--upload]](General-Commands#ap-export-file--upload)
*  [/ap `reloadconfig`](General-Commands#ap-reloadconfig)
*  [/ap `bulkupdate`](General-Commands#ap-bulkupdate-data-type-action-action-field-action-value-constraints)
*  [/ap `translations`](General-Commands#ap-translations)
*  [/ap `creategroup` \<group\> [weight] [displayname]](General-Commands#ap-creategroup-name-weight-displayname)
*  [/ap `deletegroup` \<group\>](General-Commands#ap-deletegroup-name)
*  [/ap `listgroups`](General-Commands#ap-listgroups)
*  [/ap `createtrack` \<track\>](General-Commands#ap-createtrack-name)
*  [/ap `deletetrack` \<track\>](General-Commands#ap-deletetrack-name)
*  [/ap `listtracks`](General-Commands#ap-listtracks)

### User commands
Commands used to view or modify a specific user.

Formed of `/ap user <user> ...` - where `<user>` is the username or uuid of the user being queried / modified.
*  [/ap user \<user\> `info`](User-Commands#ap-user-user-info)
*  [/ap user \<user\> `permission`](Permission-Commands)
*  [/ap user \<user\> `parent`](Parent-Commands)
*  [/ap user \<user\> `meta`](Meta-Commands)
*  [/ap user \<user\> `editor`](User-Commands#ap-user-user-editor)
*  [/ap user \<user\> `promote` \<track\> [context...]](User-Commands#ap-user-user-promote-track-context)
*  [/ap user \<user\> `demote` \<track\> [context...]](User-Commands#ap-user-user-demote-track-context)
*  [/ap user \<user\> `showtracks`](User-Commands#ap-user-user-showtracks)
*  [/ap user \<user\> `clear` [context...]](User-Commands#ap-user-user-clear-context)
*  [/ap user \<user\> `clone` \<user\>](User-Commands#ap-user-user-clone-user)

### Group commands
Commands used to view or modify a specific group.

Formed of `/ap group <group> ...` - where `<group>` is the name of the group being queried / modified.
*  [/ap group \<group\> `info`](Group-Commands#ap-group-group-info)
*  [/ap group \<group\> `permission`](Permission-Commands)
*  [/ap group \<group\> `parent`](Parent-Commands)
*  [/ap group \<group\> `meta`](Meta-Commands)
*  [/ap group \<group\> `editor`](Group-Commands#ap-group-group-editor)
*  [/ap group \<group\> `listmembers` [page]](Group-Commands#ap-group-group-listmembers-page)
*  [/ap group \<group\> `setweight` \<weight\>](Group-Commands#ap-group-group-setweight-weight)
*  [/ap group \<group\> `setdisplayname` \<name\>](Group-Commands#ap-group-group-setdisplayname-name)
*  [/ap group \<group\> `showtracks`](Group-Commands#ap-group-group-showtracks)
*  [/ap group \<group\> `clear` [context...]](Group-Commands#ap-group-group-clear-context)
*  [/ap group \<group\> `rename` \<new name\>](Group-Commands#ap-group-group-rename-new-name)
*  [/ap group \<group\> `clone` \<name of clone\>](Group-Commands#ap-group-group-clone-new-name)

### Permission commands
Commands used to view or modify the permissions data of a specific user or group.

Formed of either `/ap user <user> permission ...` or `/ap group <group> permission ...`
*  [`info`](Permission-Commands#ap-usergroup-usergroup-permission-info)
*  [`set` \<node\> \<true/false\> [context...]](Permission-Commands#ap-usergroup-usergroup-permission-set-node-truefalse-context)
*  [`unset` \<node\> [context...]](Permission-Commands#ap-usergroup-usergroup-permission-unset-node-context)
*  [`settemp` \<node\> \<true/false\> \<duration\> [temporary modifier] [context...]](Permission-Commands#ap-usergroup-usergroup-permission-settemp-node-truefalse-duration-temporary-modifier-context)
*  [`unsettemp` \<node\> [duration] [context...]](Permission-Commands#ap-usergroup-usergroup-permission-unsettemp-node-duration-context)
*  [`check` \<node\>](Permission-Commands#ap-usergroup-usergroup-permission-check-node)
*  [`clear` [context...]](Permission-Commands#ap-usergroup-usergroup-permission-clear-context)

### Parent commands
Commands used to view or modify the inheritance properties (parents) of a specific user or group.

Formed of either `/ap user <user> parent ...` or `/ap group <group> parent ...`
*  [`info`](Parent-Commands#ap-usergroup-usergroup-parent-info)
*  [`set` \<group\> [context...]](Parent-Commands#ap-usergroup-usergroup-parent-set-group-context)
*  [`add` \<group\> [context...]](Parent-Commands#ap-usergroup-usergroup-parent-add-group-context)
*  [`remove` \<group\> [context...]](Parent-Commands#ap-usergroup-usergroup-parent-remove-group-context)
*  [`settrack` \<track\> \<group\> [context...]](Parent-Commands#ap-usergroup-usergroup-parent-settrack-track-group-context)
*  [`addtemp` \<group\> \<duration\> [temporary modifier] [context...]](Parent-Commands#ap-usergroup-usergroup-parent-addtemp-group-duration-temporary-modifier-context)
*  [`removetemp` \<group\> [duration] [context...]](Parent-Commands#ap-usergroup-usergroup-parent-removetemp-group-duration-context)
*  [`clear` [context...]](Parent-Commands#ap-usergroup-usergroup-parent-clear-context)
*  [`cleartrack` \<track\> [context...]](Parent-Commands#ap-usergroup-usergroup-parent-cleartrack-track-context)
*  [`switchprimarygroup` \<group\>](Parent-Commands#ap-user-user-parent-switchprimarygroup-group)

### Meta commands
Commands used to view or modify the metadata of a specific user or group.

Formed of either `/ap user <user> meta ...` or `/ap group <group> meta ...`
*  [`info`](Meta-Commands#ap-usergroup-usergroup-meta-info)
*  [`set` \<key\> \<value\> [context...]](Meta-Commands#ap-usergroup-usergroup-meta-set-key-value-context)
*  [`unset` \<key\> [context...]](Meta-Commands#ap-usergroup-usergroup-meta-unset-key-value-context)
*  [`settemp` \<key\> \<value\> \<duration\> [temporary modifier] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-settemp-key-value-duration-temporary-modifier-context)
*  [`unsettemp` \<key\> [context...]](Meta-Commands#ap-usergroup-usergroup-meta-unsettemp-key-context)
*  [`addprefix` \<priority\> \<prefix\> [context...]](Meta-Commands#ap-usergroup-usergroup-meta-addprefix-priority-prefix-context)
*  [`addsuffix` \<priority\> \<suffix\> [context...]](Meta-Commands#ap-usergroup-usergroup-meta-addsuffix-priority-suffix-context)
*  [`setprefix` [priority] \<prefix\> [context...]](Meta-Commands#ap-usergroup-usergroup-meta-setprefix-priority-prefix-context)
*  [`setsuffix` [priority] \<suffix\> [context...]](Meta-Commands#ap-usergroup-usergroup-meta-setsuffix-priority-suffix-context)
*  [`removeprefix` \<priority\> [prefix] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-removeprefix-priority-prefix-context)
*  [`removesuffix` \<priority\> [suffix] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-removesuffix-priority-suffix-context)
*  [`addtempprefix` \<priority\> \<prefix\> \<duration\> [temporary modifier] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-addtempprefix-priority-prefix-duration-temporary-modifier-context)
*  [`addtempsuffix` \<priority\> \<suffix\> \<duration\> [temporary modifier] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-addtempsuffix-priority-suffix-duration-temporary-modifier-context)
*  [`settempprefix` [priority] \<prefix\> \<duration\> [temporary modifier] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-settempprefix-priority-prefix-duration-temporary-modifier-context)
*  [`settempsuffix` [priority] \<suffix\> \<duration\> [temporary modifier] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-settempsuffix-priority-suffix-duration-temporary-modifier-context)
*  [`removetempprefix` \<priority\> [prefix] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-removetempprefix-priority-prefix-context)
*  [`removetempsuffix` \<priority\> [suffix] [context...]](Meta-Commands#ap-usergroup-usergroup-meta-removetempsuffix-priority-suffix-context)
*  [`clear` [context...]](Meta-Commands#ap-usergroup-usergroup-meta-clear-context)

### Track commands
Commands used to view or modify a specific track.

Formed of `/ap track <track> ...` - where `<track>` is the name of the track being queried / modified.
*  [/ap track \<track\> `info`](Track-Commands#ap-track-track-info)
*  [/ap track \<track\> `editor`](Track-Commands#ap-track-track-editor)
*  [/ap track \<track\> `append` \<group\>](Track-Commands#ap-track-track-append-group)
*  [/ap track \<track\> `insert` \<group\> \<position\>](Track-Commands#ap-track-track-insert-group-position)
*  [/ap track \<track\> `remove` \<group\>](Track-Commands#ap-track-track-remove-group)
*  [/ap track \<track\> `clear`](Track-Commands#ap-track-track-clear)
*  [/ap track \<track\> `rename` \<new name\>](Track-Commands#ap-track-track-rename-new-name)
*  [/ap track \<track\> `clone` \<name of clone\>](Track-Commands#ap-track-track-clone-new-name)

### Log commands
Commands used to view the action log.
*  [/ap log `recent` [user] [page]](Log-Commands#ap-log-recent-user-page)
*  [/ap log `search` \<query\> [page]](Log-Commands#ap-log-search-query-page)
*  [/ap log `notify` [on|off]](Log-Commands#ap-log-notify-onoff)
*  [/ap log `userhistory` \<user\> [page]](Log-Commands#ap-log-userhistory-user-page)
*  [/ap log `grouphistory` \<group\> [page]](Log-Commands#ap-log-grouphistory-group-page)
*  [/ap log `trackhistory` \<track\> [page]](Log-Commands#ap-log-trackhistory-track-page)
