# AquaPermsWeb
[![Discord](https://img.shields.io/discord/241667244927483904.svg?logo=discord&label=)](https://discord.gg/xWNVTE7rp8)

[AquaPerms](https://github.com/XTHESilent/AquaPerms) is a permission plugin for Minecraft servers, written in Java.

AquaPermsWeb (this repository) contains the website for the project and a number of web apps which supplement the plugin, all written in HTML/JavaScript using the [Vue](https://vuejs.org/) framework.

### Branches

* Development takes place on the `master` branch.
* The production site at [aquasplashmc.ddns.net](https://aquasplashmc.ddns.net/aquaperms/) is automatically built from the `production` branch.
* An older (pre Vue rewrite) version of the site is on the `v1` branch.

### Development

Contributions are greatly appreciated! Just make a pull request with your changes. 

#### Cloning
Use the following command to clone (and include the wiki submodule):
```sh
git clone https://github.com/XTHESilent/AquaPermsWeb.git
```

#### Setup
Once it is cloned, move into the new directory and install the dependencies:
```sh
cd AquaPermsWeb
npm install
```

#### Compile and setup hot-reloads for development
When making changes to the app, you can run a local copy with the following command:
```sh
npm run serve
```

This will automatically open a new tab in your default browser with the app running on a local server. When you make changes to the files, the app will "hot-reload" with the new updates.

#### Compile for production
To build the project to a folder that can be accessed via a webserver, run this command (output is in the `/dist` directory):
```sh
npm run build
```

### Self hosting

Im still forking the Web Installer :D
