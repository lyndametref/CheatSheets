### Installing
    sudo apt-get install -y nodejs
    
### set the global install path
The global install put the files in `~/share/npm-global/`
    npm config set prefix ~/share/npm-global/
    
### add exec path to PATH
add to `.bashrc` to add `~/share/npm-global/`:

    export NODE_PATH=/usr/lib/nodejs:/usr/lib/node_modules:/usr/share/javascript:~/share/npm-global/lib/node_modules
    export PATH=~/share/npm-global/bin:~/.local/bin:$PATH

