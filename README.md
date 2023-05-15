# phpLiteAdmin

phpLiteAdmin on github codespaces based on [cs50](https://github.com/cs50/codespace/tree/main/opt/cs50/phpliteadmin)

## Install

```
# download code files
git clone https://github.com/eniompw/phpLiteAdmin
cd phpLiteAdmin
# move linked php and css files
mkdir -p /opt/cs50/phpliteadmin/
mv ./share/ /opt/cs50/phpliteadmin/
# make phpliteadmin executable
chmod +x phpliteadmin.py
# add to path, allows running by name only
sudo mv phpliteadmin.py /usr/local/bin
# install requirements
pip install termcolor
sudo apt update
sudo apt install phpliteadmin -y
# remove unneeded code
rm /workspaces/codespaces-blank/phpLiteAdmin -fr
```
## Run
```
touch test.db
phpliteadmin.py test.db
```
