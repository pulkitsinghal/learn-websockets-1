```
# create the directories if they don't already exist
mkdir -p ~/workspace/sample1

# clean up any old content that the tutor may have left lyign around
rm -rf ~/workspace/sample1/*

# make sure that the sample1 directory exists under workspace
cd ~/workspace && ls -alrt

# make sure that the sample1 directory has nothing inside it anymore, so we may start fresh
cd ~/workspace && ls -alrt sample1

# work inside the sample1 directory
cd ~/workspace/sample1

# install 3 dependencies: express, jade, and socket.io
npm install express@ jade socket.io
```