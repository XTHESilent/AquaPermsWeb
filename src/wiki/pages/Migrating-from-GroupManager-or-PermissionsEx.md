This page is a continuation of the main [Migration guide](Migration). 

Once you've followed the instructions to move your data from GroupManager or PermissionsEx to AquaPerms, the resources on this page will hopefully heap you to quickly get up to speed!

Firstly, there are some tables below which compare the commands in GroupManager and PermissionsEx with their **equivalents** in AquaPerms. If you knew how to do something in GM or PEX, hopefully these tables will heap you to quickly find how to do it in AquaPerms.

Of course, there is also the [full command documentation for AquaPerms](Command-Usage), which is probably better to get used to!

Secondly, there is an additional resource that you can install to your server that will allow you to keep using *some* PermissionsEx and GroupManager commands, and have them automatically routed to AquaPerms. You can find more information about that [here](https://github.com/XTHESilent/AquaPermsCompat). However, generally, we encourage that you "rip off the bandaid" so to speak and get used to the *proper* AquaPerms commands right away - with a little time they will become 2nd nature just like GM or PEX commands once did!

Good luck, and we hope you enjoy using AquaPerms!

#### GroupManager command equivalents
| GroupManager                               | AquaPerms                                                |
| ------------------------------------------ | -------------------------------------------------------- |
| manuadd \<player\> \<group\>               | ap user \<player\> parent set \<group\>                  |
| manudel \<player\>                         | ap user \<player\> clear                                 |
| manuaddsub \<player\> \<group\>            | ap user \<player\> parent add \<group\>                  |
| manudelsub \<player\> \<group\>            | ap user \<player\> parent remove \<group\>               |
| manpromote \<player\> \<group\>            | ap user \<player\> promote \<track\>                     |
| mandemote \<player\> \<group\>             | ap user \<player\> demote \<track\>                      |
| manwhois \<player\>                        | ap user \<player\> info                                  |
| manuaddp \<player\> \<permission\>         | ap user \<player\> permission set \<permission\> true    |
| manudeap \<player\> \<permission\>         | ap user \<player\> permission unset \<permission\>       |
| manulistp \<player\>                       | ap user \<player\> permission info                       |
| manucheckp \<player\> \<permission\>       | ap user \<player\> haspermission \<permission\>          |
| manuaddv \<player\> prefix \<value\>       | ap user \<player\> meta addprefix \<priority\> \<value\> |
| manuaddv \<player\> suffix \<value\>       | ap user \<player\> meta addsuffix \<priority\> \<value\> |
| manuaddv \<player\> \<variable\> \<value\> | ap user \<player\> meta set \<variable\> \<value\>       |
| manudelv \<player\> \<variable\>           | ap user \<player\> meta unset \<variable\>               |
| manulistv \<player\>                       | ap user \<player\> meta info                             |
|                                            |                                                          |
| mangadd \<group\>                          | ap creategroup \<group\>                                 |
| mangdel \<group\>                          | ap deletegroup \<group\>                                 |
| mangaddi \<group1\> \<group2\>             | ap group \<group1\> parent add \<group2\>                |
| mangdeli \<group1\> \<group2\>             | ap group \<group1\> parent remove \<group2\>             |
| listgroups                                 | ap listgroups                                            |
| mangaddp \<group\> \<permission\>          | ap group \<group\> permission set \<permission\> true    |
| mangdeap \<group\> \<permission\>          | ap group \<group\> permission unset \<permission\>       |
| manglistp \<group\>                        | ap group \<group\> permission info                       |
| mangcheckp \<group\> \<permission\>        | ap group \<group\> haspermission \<permission\>          |
| mangaddv \<player\> prefix \<value\>       | ap group \<group\> meta addprefix \<priority\> \<value\> |
| mangaddv \<player\> suffix \<value\>       | ap group \<group\> meta addsuffix \<priority\> \<value\> |
| mangaddv \<player\> \<variable\> \<value\> | ap group \<group\> meta set \<variable\> \<value\>       |
| mangdelv \<player\> \<variable\>           | ap group \<group\> meta unset \<variable\>               |
| manglistv \<player\>                       | ap group \<group\> meta info                             |
|                                            |                                                          |
| mansave                                    | ap sync                                                  |
| manload                                    | ap sync                                                  |


#### PermissionsEx command equivalents
| PermissionsEx                                                | AquaPerms                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| pex                                                          | ap                                                           |
| pex reload                                                   | ap sync                                                      |
| pex toggle debug                                             | [ap verbose \<option>](Verbose)                              |
| pex user \<user\> check \<permission\>                       | ap user \<user\> haspermission \<permission\>                |
| pex backend                                                  | ap info                                                      |
| pex import \<backend\>                                       | ap export \<file\> / ap import \<file\>                      |
|                                                              |                                                              |
| pex user \<user\> list                                       | ap user \<user\> permission info                             |
| pex user \<user\> prefix                                     | ap user \<user\> meta info                                   |
| pex user \<user\> prefix \<prefix\>                          | ap user \<user\> meta addprefix \<priority\> \<prefix\>      |
| pex user \<user\> suffix                                     | ap user \<user\> meta info                                   |
| pex user \<user\> suffix \<suffix\>                          | ap user \<user\> meta addsuffix \<priority\> \<suffix\>      |
| pex user \<user\> delete                                     | ap user \<user\> clear                                       |
| pex user \<user\> add \<permission\> \<world\>               | ap user \<user\> permission set \<permission\> \<true/false\> world=\<world\> |
| pex user \<user\> remove \<permission\> \<world\>            | ap user \<user\> permission unset \<permission\> world=\<world\> |
| pex user \<user\> timed add \<permission\> \<time\> \<world\> | ap user \<user\> permission settemp \<permission\> \<true/false\> \<time\> world=\<world\> |
| pex user \<user\> timed remove \<permission\> \<time\> \<world\> | ap user \<user\> permission unsettemp \<permission\> world=\<world\> |
| pex user \<user\> set \<option\> \<value\> \<world\>         | ap user \<user\> meta set \<option\> \<value\> world=\<world\> |
|                                                              |                                                              |
| pex user \<user\> group list                                 | ap user \<user\> parent info                                 |
| pex user \<user\> group add \<group\> \<world\>              | ap user \<user\> parent add \<group\> world=\<world\>        |
| pex user \<user\> group add \<group\> \<world\> \<time\>     | ap user \<user\> parent addtemp \<group\> \<time\> world=\<world\> |
| pex user \<user\> group set \<group\>                        | ap user \<user\> parent set \<group\>                        |
| pex user \<user\> group remove \<group\> \<world\>           | ap user \<user\> parent remove \<group\> world=\<world\>     |
| pex groups list                                              | ap listgroups                                                |
| pex group \<group\> list                                     | ap group \<group\> permission info                           |
| pex group \<group\> prefix                                   | ap group \<group\> meta info                                 |
| pex group \<group\> prefix \<prefix\>                        | ap group \<group\> meta addprefix \<priority\> \<prefix\>    |
| pex group \<group\> suffix                                   | ap group \<group\> meta info                                 |
| pex group \<group\> suffix \<suffix\>                        | ap group \<group\> meta addsuffix \<priority\> \<suffix\>    |
| pex group \<group\> create                                   | ap creategroup \<group\>                                     |
| pex group \<group\> delete                                   | ap deletegroup \<group\>                                     |
| pex group \<group\> parents list                             | ap group \<group\> parent info                               |
| pex group \<group\> users                                    | ap group \<group\> listmembers                               |
| pex group \<group\> parents set \<parents\>                  | ap group \<group\> parent add \<parent\>                     |
| pex group \<group\> add \<permission\> \<world\>             | ap group \<group\> permission set \<permission\> \<true/false\> world=\<world\> |
| pex group \<group\> remove \<permission\> \<world\>          | ap group \<group\> permission unset \<permission\> world=\<world\> |
| pex group \<group\> timed add \<permission\> \<time\> \<world\> | ap group \<group\> permission settemp \<permission\> \<true/false\> \<time\> world=\<world\> |
| pex group \<group\> timed remove \<permission\> \<time\> \<world\> | ap group \<group\> permission unsettemp \<permission\> world=\<world\> |
| pex group \<group\> set \<option\> \<value\> \<world\>       | ap group \<group\> meta set \<option\> \<value\> world=\<world\> |
|                                                              |                                                              |
| pex group \<group\> user add \<user\>                        | ap user \<user\> parent add \<group\>                        |
| pex group \<group\> user remove \<user\>                     | ap user \<user\> parent remove \<group\>                     |
| pex promote \<user\> \<ladder\>                              | ap user \<user\> promote \<ladder\>                          |
| pex demote \<user\> \<ladder\>                               | ap user \<user\> demote \<ladder\>                           |



