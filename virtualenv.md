### Install virtualenv (python3)
built-in with 3.3, or can be added to 2.6+/3.1+ : https://packaging.python.org/installing/#creating-virtual-environments

    pip install virtualenv

### Create new virtualenv specifying which version of Pyhton using
    virtualenv -p /usr/bin/python3 virtualenv

easier if ~/.local/bin is in PATH, so adding to `~/.bashrc` the following:
    export PATH=~/.local/bin:$PATH
    
### activate the virtualenv
    source virtualenv/bin/activate

### deatctivate virtualenv
    deactivate