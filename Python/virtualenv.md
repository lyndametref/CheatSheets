
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

		- [Install virtualenv](#install-virtualenv)
		- [Create new virtualenv specifying which version of Pyhton using](#create-new-virtualenv-specifying-which-version-of-pyhton-using)
		- [activate the virtualenv](#activate-the-virtualenv)
		- [deatctivate virtualenv](#deatctivate-virtualenv)
		- [Save package list installed in venv](#save-package-list-installed-in-venv)
	- [Reference](#reference)

<!-- /TOC -->

### Install virtualenv
3.3+ built-in. In Ubuntu:

    sudo apt-get install python3-venv

### Create new virtualenv specifying which version of Pyhton using
    python3 -m venv my_venv_path

### activate the virtualenv
    source my_venv_path/bin/activate

### deatctivate virtualenv
    deactivate

### Save package list installed in venv

   pip freeze > requirements.txt

## Reference
https://packaging.python.org/installing/#creating-virtual-environments
