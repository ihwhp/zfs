# Commands used:
```
lsblk -f
zpool --help
zpool create otus1 mirror /dev/sd{b,c}   
zpool create otus2 mirror /dev/sd{d,e}
zpool create otus3 mirror /dev/sd{f,g}
zpool create otus4 mirror /dev/sd{h,i}
zpool list
zpool status
zfs get all
zfs set compression=lzjb otus1
zfs set compression=lz4 otus2
zfs set compression=gzip-9 otus3
zfs set compression=zle otus4
zfs get all | grep compression
for i in {1..4}; do  wget -P /otus$i https://gutenberg.org/cache/epub/2600/pg2600.converter.log; done
ls -l /otus*
zfs list
zfs get all |grep compressratio | grep -v ref
wget -O archive.tar.gz --no-check-certificate 'https://drive.google.com/u/0/uc?id=1KRBNW33QWqbvbVHa3hLJivOAt60yukkg&export=download'
tar -xzvf archive.tar.gz 
zpool import -d zpoolexport/
zpool import -d zpoolexport/ otus
zpool status
zpool get all otus
zfs get all otus
zfs get available otus
zfs get readonly otus
zfs get recordsize otus
zfs get compression otus
zfs get checksum otus
wget -O otus_task2.file --no-check-certificate 'https://drive.google.com/u/0/uc?id=1gH8gCL9y7Nd5Ti3IRmplZPF1XjzxeRAG&export=download'
zfs receive otus1/test@today < otus_task2.file 
ll /otus1/test/
find /otus1/test/ -name "secret_message"
cat /otus1/test/task1/file_mess/secret_message
```
\#
