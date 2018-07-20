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
git clone http://gitlab.com/jrenslo/arnaout.git
cd arnaout/classifiers
make install
