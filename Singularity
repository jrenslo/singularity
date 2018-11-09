Bootstrap:docker
From:ubuntu:latest

%labels
Maintainer jrenslo

%environment

%runscript
exec /bin/bash $@  # runs whichever arguments given to the script

%post
apt-get update
apt-get -y install gcc wget clang python3 vim python-dev python-pip python-tk git
git clone http://github.com/jrenslo/singularity repo
cd repo
echo "Installing pip now"
#pip install --upgrade pip
pip install -r requirements.txt
python setup_script.py
python -m spacy download en_core_web_lg

#for tensorflow
#apt-get install pkg-config zip g++ zlibg-dev unzip
#wget https://github.com/bazelbuild/bazel/releases/download/0.18.1/bazel-0.18.1-installer-linux-x86_64.sh
#chmod +x bazel-0.18.1-installer-linux-x86_64.sh
#./bazel-0.18.1-installer-linux-x86_64.sh --user
#export PATH="$PATH:$HOME/bin"
#
#pip install -U --user pip six numpy wheel mock
#pip install -U --user keras_applications==1.0.5 --no-deps
#pip install -U --user keras_preprocessing==1.0.3 --no-deps
#git clone https://github.com/tensorflow/tensorflow.git
#cd tensorflow
#git checkout master  # r1.9, r1.10, etc.
## bazel test -c opt -- //tensorflow/... -//tensorflow/compiler/... -//tensorflow/contrib/lite/... # for <r1.12
#bazel test -c opt -- //tensorflow/... -//tensorflow/compiler/... -//tensorflow/lite/...
#./configure --config=monolithic
#bazel build --config=opt //tensorflow/tools/pip_package:build_pip_package
#./bazel-bin/tensorflow/tools/pip_package/build_pip_package /tmp/tensorflow_pkg
#pip install /tmp/tensorflow_pkg/tensorflow-version-tags.whl