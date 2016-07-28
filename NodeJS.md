### Installing
    sudo apt-get install -y nodejs
    
### add exec path to PATH
add to .bashrc:

    export NODE_PATH=/usr/lib/nodejs:/usr/lib/node_modules:/usr/share/javascript:~/share/npm-global/lib/node_modules
    export PATH=~/share/npm-global/bin:~/.local/bin:$PATH

### set the global install path
    npm config set prefix ~/share/npm-global/