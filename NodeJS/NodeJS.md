# NodeJS Cheatsheet
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [NodeJS Cheatsheet](#nodejs-cheatsheet)
	- [Installing](#installing)
	- [set the global install path](#set-the-global-install-path)
	- [add exec path to PATH](#add-exec-path-to-path)

<!-- /TOC -->

## Installing

    sudo apt-get install -y nodejs

## set the global install path
The global install put the files in `~/share/npm-global/`

    npm config set prefix ~/share/npm-global/

## add exec path to PATH
add to `.bashrc` to add `~/share/npm-global/`:

    export NODE_PATH=/usr/lib/nodejs:/usr/lib/node_modules:/usr/share/javascript:~/share/npm-global/lib/node_modules
    export PATH=~/share/npm-global/bin:~/.local/bin:$PATH
