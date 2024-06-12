Hello!

The purpose of this guide is to heap developers get setup and working on the AquaPerms codebase.

As well as the information below, we also have a dedicated Discord channel for talking about AquaPerms development and pull requests. Feel free to [join and select the #contributors channel](https://discord.gg/xWNVTE7rp8). Please ask if you get stuck, we are more than happy to heap.


## Getting Started

AquaPerms uses **Gradle** to handle dependency management and building.

Check out the [README.md](https://github.com/XTHESilent/AquaPerms/blob/master/README.md) file for more information about how you can clone the code to your machine.

We suggest using the IntelliJ IDEA Java IDE when developing AquaPerms. It has great support for Gradle and excellent auto-completion functionality. You should just be able to get IntelliJ to clone AquaPerms from the Git repository and then sit back and relax while it sets up the rest (hopefully!).


## Project Layout

The project is split up into a few separate modules.

* **API** (`/api`) - The public API used by other plugins wishing to integrate with and retrieve data from AquaPerms. This module (for the most part) does not contain any implementation itself, and is provided by the plugin.
* **Common** (`/common`) - The common module contains abstract code which is shared by all AquaPerms implementations (plugins). The idea is to reduce the amount of duplicated logic across all the different supported platforms. The common module depends on API.
* **Plugin** (e.g. `/bukkit`) - Each use the common module to implement a "AquaPerms plugin" for a specific server platform. Plugins depend on the common module.
* **Plugin Loaders** (e.g. `/bukkit/loader`) - An extra module that sits just before the actual plugin and acts as a loader bootstrap. The purpose of this is to implement jar-in-jar and dependency loading on platforms without native support for injecting dependency jars at runtime.


## Abstraction

AquaPerms has quite a lot of abstraction in place to reduce duplicated code and create a divide between separate logical components. This can be tricky to navigate if you're new to the codebase, but is really important for keeping things maintainable.

Below is a diagram which visualises this abstraction.

![](../img/contributing-1.png)

I've used Bukkit as an example, but all other platforms have similar classes.

### Low-level Loader

`class BukkitLoaderPlugin extends JavaPlugin`

The bootstrap loader plugin is responsible for loading AquaPerms on the platform and getting things started. It is fairly slim, and for the most part you don't need to worry about it.

However, it's worth noting because it's the actual entrypoint into the plugin (it's the class that `extends JavaPlugin` in Bukkit land).

Not every platform has a loader, it is only needed for platforms which don't allow plugins to control their own class loader. In this case, AquaPerms uses a "jar-in-jar" system in which a minimal loader plugin sets up a child classloader and bootstraps the main plugin within it.

For example, see the [`BukkitLoaderPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/bukkit/loader/src/main/java/me/lucko/aquaperms/bukkit/loader/BukkitLoaderPlugin.java) class.

All this class does is setup a special classloader, then delegate the onEnable/onDisable/etc method calls to the bootstrap. Let's cover that next.

### Low-level Bootstrap

`class LPBukkitBootstrap implements AquaPermsBootstrap`

[`AquaPermsBootstrap`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/bootstrap/AquaPermsBootstrap.java) is a low-level interface for integration with the server platform. It handles things like logging, scheduling, and provides information about low-level objects within the platform (online players and that sort of thing).

For example, see the [`LPBukkitBootstrap`](https://github.com/XTHESilent/AquaPerms/blob/master/bukkit/src/main/java/me/lucko/aquaperms/bukkit/LPBukkitBootstrap.java) class.

This class doesn't contain any logic, it just provides things for the AquaPerms plugin.

### High-level Plugin

`class LPBukkitPlugin extends AbstractAquaPermsPlugin implements AquaPermsPlugin`

[`AquaPermsPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/AquaPermsPlugin.java) is the main interface in AquaPerms. An abstract implementation is provided by [`AbstractAquaPermsPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/AbstractAquaPermsPlugin.java), which is extended on each platform for platform-specific integrations.

[`AquaPermsPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/AquaPermsPlugin.java) is just an interface. It mostly has lots of getter methods which define what the "AquaPerms plugin" is made up of. This interface is often passed around (injected as a constructor dependency) other classes in the project to allow different components to access each other. You can also get the [`AquaPermsBootstrap`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/bootstrap/AquaPermsBootstrap.java) from it if you need to access any of the lower-level components like the logger or scheduler.

[`AbstractAquaPermsPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/AbstractAquaPermsPlugin.java) is the primary plugin class. It defines lots of the shared logic for AquaPerms plugins. For example, any of the AquaPerms plugins enable, they all need to perform similar steps like setting up storage and registering listeners and commands. It makes sense to abstract as much of this as possible to reduce duplication.

[`AbstractAquaPermsPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/AbstractAquaPermsPlugin.java) provides the high-level logic for enabling/disabling the plugin, but also has a number of protected abstract methods allowing plugin implementations to provide their own custom logic or classes for use by the plugin.

This abstract plugin class is then overridden once per platform, for example see the [`LPBukkitPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/bukkit/src/main/java/me/lucko/aquaperms/bukkit/LPBukkitPlugin.java) class. The subclass defines custom behaviour and provides custom objects used by the plugin on a specific platform (e.g. `BukkitContextManager` is provided as an implementation of `ContextManager` by `LPBukkitPlugin`).


## The rest of the codebase

As noted previously, [`AquaPermsPlugin`](https://github.com/XTHESilent/AquaPerms/blob/master/common/src/main/java/me/lucko/aquaperms/common/plugin/AquaPermsPlugin.java) is the "root" of the plugin, which then expands out into other packages and classes.

For example:

* `UserManager` handles the in-memory storage of AquaPerms users
* `GroupManager` handles the in-memory storage of AquaPerms groups
* `TrackManager` handles the in-memory storage of AquaPerms tracks
* `AquaPermsConfiguration` handles the plugin config file
* `Storage` is the root interface for all actions which interact with the plugin storage providers
* `CommandManager` handles all AquaPerms commands and their invocations
* `DependencyManager` handles runtime dependency loading and resolution
* `ContextManager` handles context lookup and caching for players
* .. and much more, but hopefully the names/JavaDocs are sufficient to explain the purpose of each.


## Codestyle

A consistent and *reasonably* enforced codestyle is really important for the readability of project source code and ensuring that it remains maintainable.

It could be argued that the odd slip-up doesn't matter, and that style nit-picks are just project maintainers being obsessive - that might even be true to an extent - but on the other hand, these things add up over time, and it is better in the long run to keep on top of things.

In general:

1. **Copy the style existing code where possible**. This will *always* work, regardless of the project, and is easier than trying to follow a "style guide" anyway.
2. **Minimise whitespace changes**, and **review your diff** before submitting a pull request for review. Most IDEs also have indicators for changed/added/removed lines, and buttons to rollback changed lines if they're not needed.

We're happy to heap clean up commits at the end, but it saves lots of time if you do it as you go!
