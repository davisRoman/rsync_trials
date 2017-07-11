#!/bin/bash

#target=myHost
#here=$(pwd)

# 1. create a temp directory
#cd /tmp
#mkdir TMPfs
#cd TMPfs

fakeroot bash <<- EOF
    # 2. unpack tar archive into it
    #tar xf $here/archive.tar
    # 3. rysnc as needed (ssh options are *the* relevant thing)
     #rsync -av -e "ssh -i $HOME/.ssh/id_rsa -oUserKnownHostsFile=$HOME/.ssh/known_hosts" . root@$target:/
    # 4. if something changed locally repack int a new tar archive (not needed here)

    sudo rsync -v -azh --progress --delete --devices --compress-level=0 --inplace drop:/home/davis/my_rootfs/dev my_rootfs
    tar -cvzf my_rootfs.tar.gz my_rootfs
EOF

# 5. cleanup
#rm -rf *
#cd ..
#rmdir TMPfs
