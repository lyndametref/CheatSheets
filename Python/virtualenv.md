### Install virtualenv
https://packaging.python.org/installing/#creating-virtual-environments

3.3+ built-in. In Ubuntu:

    sudo apt-get install python3-venv
    
can be added to 2.6+/3.1+ : 

    pip install virtualenv

### Create new virtualenv specifying which version of Pyhton using
3.3+:
    python3 -m venv my_venv_path

### activate the virtualenv
    source my_venv_path/bin/activate

### deatctivate virtualenv
    deactivate