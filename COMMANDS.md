mkdir -p $THETA_HOME
git clone --branch release https://github.com/thetatoken/theta-protocol-ledger.git $THETA_HOME
cd $THETA_HOME
cp -r ./integration/privatenet ../privatenet
mkdir ~/.thetacli
cp -r ./integration/privatenet/thetacli/* ~/.thetacli/
chmod 700 ~/.thetacli/keys/encrypted
theta start --config=../privatenet/node
thetacli tx send --chain="privatenet" --from=2E833968E5bB786Ae419c4d13189fB081Cc43bab --to=9F1233798E905E173560071255140b4A8aBd3Ec6 --theta=10 --tfuel=20 --seq=1
thetacli query account --address=9F1233798E905E173560071255140b4A8aBd3Ec6

scp dump_storeview thedrop:/home/ec2-user/files
scp encrypt_sk thedrop:/home/ec2-user/files
scp generate_genesis thedrop:/home/ec2-user/files
scp hex_obj_parser thedrop:/home/ec2-user/files
scp import_chain thedrop:/home/ec2-user/files
scp inspect_data thedrop:/home/ec2-user/files
scp query_db thedrop:/home/ec2-user/files
scp sign_hex_msg thedrop:/home/ec2-user/files
scp theta thedrop:/home/ec2-user/files
scp thetacli thedrop:/home/ec2-user/files

mkdir -p $GOPATH/bin
cd $GOPATH/bin

curl -LO http://thedrop.partner-eng.com/files/dump_storeview
curl -LO http://thedrop.partner-eng.com/files/encrypt_sk
curl -LO http://thedrop.partner-eng.com/files/generate_genesis
curl -LO http://thedrop.partner-eng.com/files/hex_obj_parser
curl -LO http://thedrop.partner-eng.com/files/import_chain
curl -LO http://thedrop.partner-eng.com/files/inspect_data
curl -LO http://thedrop.partner-eng.com/files/query_db
curl -LO http://thedrop.partner-eng.com/files/sign_hex_msg
curl -LO http://thedrop.partner-eng.com/files/theta
curl -LO http://thedrop.partner-eng.com/files/thetacli

chmod 755 dump_storeview
chmod 755 encrypt_sk
chmod 755 generate_genesis
chmod 755 hex_obj_parser
chmod 755 import_chain
chmod 755 inspect_data
chmod 755 query_db
chmod 755 sign_hex_msg
chmod 755 theta
chmod 755 thetacli

notroot install libc6-dev
notroot install build-essential
notroot install gcc
notroot install make
notroot install bzr
linux-libc-dev
notroot install libc6-dev
export INCLUDE=/home/user/notroot/usr/include:/home/user/notroot/usr/include/x86_64-linux-gnu/bits 
cd /home/user/notroot/usr/include
ln -s x86_64-linux-gnu/bits .
ln -s x86_64-linux-gnu/sys .
ln -s x86_64-linux-gnu/gnu .
ln -s x86_64-linux-gnu/asm .
LD_LIBRARY_PATH=/home/user/notroot/usr/=

LD_LIBRARY_PATH=/home/user/notroot/deb/usr/lib:/home/user/notroot/deb/lib:/home/user/notroot/deb/usr/lib/x86_64-linux-gnu:/home/user/notroot/deb/lib/x86_64-linux-gnu:/home/user/notroot/usr/lib:/home/user/notroot/lib:/home/user/notroot/usr/lib/x86_64-linux-gnu:/home/user/notroot/lib/x86_64-linux-gnu:
LD_LIBRARY_PATH=/home/user/notroot/usr/lib/x86_64-linux-gnu:/home/user/notroot/deb/usr/lib:/home/user/notroot/deb/lib:/home/user/notroot/deb/usr/lib/x86_64-linux-gnu:/home/user/notroot/deb/lib/x86_64-linux-gnu:/home/user/notroot/usr/lib:/home/user/notroot/lib:/home/user/notroot/usr/lib/x86_64-linux-gnu


