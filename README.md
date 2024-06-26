# phpLiteAdmin

Install phpLiteAdmin on GitHub Codespaces based on [cs50](https://github.com/cs50/codespace/tree/main/opt/cs50/phpliteadmin)

## Install
One line installer:
```
curl -s https://raw.githubusercontent.com/eniompw/phpLiteAdmin/main/install.sh | bash
```
**OR**  

All the explicit steps installer:
```
# download code files
git clone https://github.com/eniompw/phpLiteAdmin
cd phpLiteAdmin
# move linked php and css files
sudo mkdir -p /opt/cs50/phpliteadmin/
sudo mv ./share/ /opt/cs50/phpliteadmin/
# make phpliteadmin executable
chmod +x phpliteadmin.py
# add to path, allows running by name only
sudo mv phpliteadmin.py /usr/local/bin
# add pla symlink to phpliteadmin.py
sudo ln -s /usr/local/bin/phpliteadmin.py /usr/local/bin/pla
# remove unneeded code
rm ../phpLiteAdmin -fr
cd ..
# install requirements
pip install termcolor
sudo apt update
sudo apt install phpliteadmin -y
sudo apt install python-is-python3 -y
```

## Run
```
pla filename.db  
OR  
phpliteadmin.py filename.db

usage: phpliteadmin [-h] path
phpliteadmin: error: the following arguments are required: path
```

## Investigation
On cs50.dev
```
$ whereis phpliteadmin 
phpliteadmin: /opt/cs50/bin/phpliteadmin
$ ls /opt/cs50/bin/phpliteadmin 
/opt/cs50/bin/phpliteadmin@
$ readlink /opt/cs50/bin/phpliteadmin 
/opt/cs50/phpliteadmin/bin/phpliteadmin
```
Python file points to:  
``` 
PHP_FILE = f'/opt/cs50/phpliteadmin/share/index.php'
PHP_THEME = f'/opt/cs50/phpliteadmin/share/phpliteadmin.css'
