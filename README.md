# voltha-netoconf-server
Netconf Server support for OpenCORD vOLTHA project using Netopeer2/Sysrepo

Assumption is that you have downloaded OpenCORD vOLTHA project from https://github.com/opencord/voltha and have followed and setup environment for bringing up vOLTHA.
Assuming you have installed the vOLTHA at ~/cord/incubator/voltha
Also assuming proto2yang location at ~/proto2yang

Follow below steps to generate yang files which will be placed in ~/proto2yang/yang directory from proto files

cd ~/cord/incubator/voltha
source env.sh
cd ~/proto2yang
mkdir yang
cd protos
python -m grpc.tools.protoc -I. --plugin=protoc-gen-custom=./proto2yang.py --custom_out=../yang voltha.proto
python -m grpc.tools.protoc -I. --plugin=protoc-gen-custom=./proto2yang.py --custom_out=../yang events.proto

