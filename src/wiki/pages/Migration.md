AquaPerms is able to automatically import permissions data from other plugins - we call this system "migration".

### Intro
It should be noted that these scripts are not perfect. They will do a pretty decent job at converting all of your existing data, and work perfectly in *most cases*. However, not all data is the same, and there are sometimes things I haven't accounted for.

AquaPerms has some similarities with other permission plugins, however, some parts are fundamentally different, and therefore sometimes automatic migration is tricky.

Additionally, letting the plugin migrate all of your data for you means you will not have a chance to learn any of the AquaPerms commands. This may become an issue later on. 😉 If you're migrating from PermissionsEx or GroupManager, you might [find this page useful](Migrating-from-GroupManager-or-PermissionsEx).

If you have an old permissions setup, or a setup you're not completely happy with, now might be a great time to have a restructure and cleanup, and a chance to learn AquaPerms commands in the process!


#### Supported plugins
Migration is supported for:

* GroupManager
* PermissionsEx (Bukkit/Spigot only)
* zPermissions
* bPermissions
* PermissionsBukkit
* PowerRanks
* UltraPermissions
* BungeePerms (migration can only be performed on the proxy)

## The process
The migration process is fairly simple, however it varies slightly for each platform.

#### Step 1: Install AquaPerms

Firstly, you need to [install AquaPerms](Installation). Don't remove your old permissions plugin yet.

Ensure that your old permissions plugin is still enabling properly. The migration process won't work if your old setup is broken.

If you intend to change your data [storage type](Storage-types), for instance, to mysql, it is easiest to do this now. If you decide to change storage types after the migration, follow the instructions in [Switching Storage Types](Switching-storage-types).

#### Step 2: Install the correct migration plugin

Download the jar that corresponds to your existing permission plugin from the table below. Add it to your plugins folder too.

| Plugin            | Migration Jar                                                | Migration Command            |
| ----------------- | ------------------------------------------------------------ | ---------------------------- |
| GroupManager      | [aquaperms-migration-groupmanager.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/groupmanager/build/libs/aquaperms-migration-groupmanager.jar) | `/migrate-groupmanager`      |
| PermissionsEx     | [aquaperms-migration-permissionsex.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/permissionsex/build/libs/aquaperms-migration-permissionsex.jar) | `/migrate-permissionsex`     |
| zPermissions      | [aquaperms-migration-zpermissions.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/zpermissions/build/libs/aquaperms-migration-zpermissions.jar) | `/migrate-zpermissions`      |
| bPermissions      | [aquaperms-migration-bpermissions.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/bpermissions/build/libs/aquaperms-migration-bpermissions.jar) | `/migrate-bpermissions`      |
| PermissionsBukkit | [aquaperms-migration-permissionsbukkit.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/permissionsbukkit/build/libs/aquaperms-migration-permissionsbukkit.jar) | `/migrate-permissionsbukkit` |
| PowerRanks        | [aquaperms-migration-powerranks.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/powerranks/build/libs/aquaperms-migration-powerranks.jar) | `/migrate-powerranks`        |
| UltraPermissions  | [aquaperms-migration-ultrapermissions.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/ultrapermissions/build/libs/aquaperms-migration-ultrapermissions.jar) | `/migrate-ultrapermissions` |
| BungeePerms       | [aquaperms-migration-bungeeperms.jar](https://ci.lucko.me/job/aquaperms-migration/lastSuccessfulBuild/artifact/bungeeperms/build/libs/aquaperms-migration-bungeeperms.jar) | `/migrate-bungeeperms`       |

#### Step 3: Restart your server, then run the migration command.

Restart the server to allow your existing plugin, AquaPerms, and the migration plugin to load correctly.

Then, go to your server console and run the migration command listed in the table above.

Sit back, relax, and let AquaPerms handle the rest! You will be notified of the migration progress, and then notified again once it has finished.

When the process has finished, stop the server, remove the your old permissions plugin and the migration jar, then start your server again.

If you're migrating from GroupManager or PermissionsEx, there are some additional resources [here](Migrating-from-GroupManager-or-PermissionsEx) which may be useful!