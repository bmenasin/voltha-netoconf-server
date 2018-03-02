# voltha-netoconf-server
Netconf Server support for OpenCORD vOLTHA project using Netopeer2/Sysrepo

Assumption is that you have downloaded OpenCORD vOLTHA project from https://github.com/opencord/voltha and have followed and setup environment for bringing up vOLTHA. <br />
Assuming you have installed the vOLTHA at ~/cord/incubator/voltha<br />
Also assuming proto2yang location at ~/voltha-netoconf-server/proto2yang<br />

Follow below steps to generate yang files which will be placed in ~/proto2yang/yang directory from proto files<br />

cd ~/cord/incubator/voltha<br />
source env.sh<br />
cd ~/voltha-netoconf-server/proto2yang<br />
mkdir yang<br />
cd protos<br />
chmod +x proto2yang.py<br />
python -m grpc.tools.protoc -I. --plugin=protoc-gen-custom=./proto2yang.py --custom_out=../yang voltha.proto<br />
python -m grpc.tools.protoc -I. --plugin=protoc-gen-custom=./proto2yang.py --custom_out=../yang events.proto<br />

