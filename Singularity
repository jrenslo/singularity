Bootstrap:docker
From:ubuntu:latest

%labels
Maintainer jrenslo

%environment

%runscript
exec /bin/bash $@

%post
apt-get update
apt-get -y install gcc wget clang python3 vim python-dev python-pip python-tk git
git clone http://github.com/jrenslo/singularity repo
cd repo
echo "Installing pip now"
#pip install --upgrade pip
pip install -r requirements.txt
python setup_script.py
