```
rsync_sending=/var/www/rsync/TSVE/202-0/rootfs-contents/
rsync_receiving=/tmp/rootfs_b

rsync -v -azh --progress         \
              --recursive        \
              --links            \
              --archive          \
              --checksum         \
              --delete           \
              --devices          \
              --compress         \
              --inplace          \
              --hard-links       \
              --perms            \
              --executability    \
              --xattrs           \
              --owner            \
              --group            \
              --times            \
              --one-file-system  \
              --force            \
              --stats            \
              --human-readable   \
              --itemize-changes  \
              --no-whole-file    \
              root@10.10.100.248:${rsync_sending} ${rsync_receiving}
```
