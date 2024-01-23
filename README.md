# Linux SYS_ADMIN Notes

This is My own Notes 

This Repo Structed by days 

### Day 1 : Basics info & installation ;

### Day 2 :

### 1. chvt <CHange foreground Virtual Terminal>

```bash
tty # Get TTY number I in 
chvt 5 # Change From TTY I in to TTY 5
```

#### Day 3 :

Command Line Basics :

`pwd`,`ls PATH`,`su - USERNAME` , `cal`,`date` , `eject`

* pwd show where you are
  
  ```bash
  pwd 
  /root/Downloads
  ```

* ls <Listing Directory> 
  
  * ls without PATH 
    
    ```bash
    ls
    bin   cdrom  dev  home  lib32  libx32  media  opt   root  sbin  srv
    tmp   var    boot etc   lib   lib64    mnt    proc  run   sys   usr ```
    ```
  
  * ls with PATH will list files who's in this PATH 
    
    ```bash
    ls root/
    backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  snap  spool  tmp  www
    ```

* su 
  
  * with out gaving user name 
    
    ```bash
    su - username
    su - == su - root 
    ```

* cal <Showing Calendar by Year or Month>
  
  * for showing yeah calendar use   `cal 2017` will gave you calendar of 2015 by Months
    
    ```bash
    cal 2017
          January               February               March          
    
      Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  
      1  2  3  4  5  6  7            1  2  3  4            1  2  3  4  
      8  9 10 11 12 13 14   5  6  7  8  9 10 11   5  6  7  8  9 10 11  
      15 16 17 18 19 20 21  12 13 14 15 16 17 18  12 13 14 15 16 17 18  
      22 23 24 25 26 27 28  19 20 21 22 23 24 25  19 20 21 22 23 24 25  
      29 30 31              26 27 28              26 27 28 29 30 31     
    
           April                  May                   June          
    
    Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  
                       1      1  2  3  4  5  6               1  2  3  
     2  3  4  5  6  7  8   7  8  9 10 11 12 13   4  5  6  7  8  9 10  
     9 10 11 12 13 14 15  14 15 16 17 18 19 20  11 12 13 14 15 16 17  
    16 17 18 19 20 21 22  21 22 23 24 25 26 27  18 19 20 21 22 23 24  
    23 24 25 26 27 28 29  28 29 30 31           25 26 27 28 29 30     
    30                                                                
    
            July                 August              September        
    
    Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  
                       1         1  2  3  4  5                  1  2  
     2  3  4  5  6  7  8   6  7  8  9 10 11 12   3  4  5  6  7  8  9  
     9 10 11 12 13 14 15  13 14 15 16 17 18 19  10 11 12 13 14 15 16  
    16 17 18 19 20 21 22  20 21 22 23 24 25 26  17 18 19 20 21 22 23  
    23 24 25 26 27 28 29  27 28 29 30 31        24 25 26 27 28 29 30  
    30 31                                                             
    
          October               November              December        
    
    Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  
     1  2  3  4  5  6  7            1  2  3  4                  1  2  
     8  9 10 11 12 13 14   5  6  7  8  9 10 11   3  4  5  6  7  8  9  
    15 16 17 18 19 20 21  12 13 14 15 16 17 18  10 11 12 13 14 15 16  
    22 23 24 25 26 27 28  19 20 21 22 23 24 25  17 18 19 20 21 22 23  
    29 30 31              26 27 28 29 30        24 25 26 27 28 29 30  
                                                31 
    ```

* date <showing Today Data >

* eject <Get CD-ROM door out> 
  
  ![CD-ROM](https://upload.wikimedia.org/wikipedia/commons/7/70/Sony_CRX310S-Internal-PC-DVD-Drive-Opened.jpg)
  
  * you can use eject with drive ex `eject /dev/sda` *Dont Use Eject With Partitions* `eject /dev/sda1`

* ```bash
  eject /dev/sda
  ```

## users :

* `normal users` there ID Starts From 1000 

* `root` takes 0-ID 

* 1-999 They're for services ex apache have user called web and so on with another services like FTP , SMTP and so on 

* > all users saved in  etc/passwd

* ```bash
  cat /etc/passwd
  ```

### Get Current userID

```bash
id
```

### Get Another userID

```bash
id username
```

## Linux File SYS Structure

![CD-ROM](https://1.bp.blogspot.com/-UQ7-sWd_J4w/WmhKIFx7_fI/AAAAAAAAHIE/tixi5SsyI5YzoJygq_JQKL50axe2cAcrQCLcBGAs/s1600/Untitled.png)

* `home`    : home Direcetory of any users will be created

* `root`    :  Directory for only ROOT user 

* `boot`    : Directory for boot files  

* `etc`      :  every Configration will be saved into it

* `bin`      : all binary files will be saved there 

* `sbin`    : system binarys or Administration Binarys  _normal users can access it_ . 

* `dev`      :  devices file 

* > EVERY THING IS FILE in Linux

* so `/dev/` all disk dirvers as file will be there and some spicall drivers like `/dev/zero` or`/dev/null` 

* `tmp`      : temp files 

* `usr`      : all Shared File between users  will be There

* `var`      : variable files for services Like Apache , FTP , SMTP , and so on  

* `media` , `mount` , `mnt` used for mounting files and accessing removable media ex CD-ROM and USB or any another Mircocontroller Like raspberry pi
  
  > you can remove it and mount disks any where but it comes as stander 
  
  ```bash
  mount /dev/sda1 /mnt/
  mount /dev/sdb1 /media/
  mount /dev/sdc1 /mount/
  or any another endpoint
  mount /dev/sda3 /usr/local_mount/
  ```

* `run` ,`sys`    :  running process used by kernel 

* `opt`      : optinal files you can remove it

* `srv`      : optinal files like opt .  

* `lib`      :  Library files like for <iostream> for c++ and so on with another lang 

* `proc`    : called Virtual Filesystem and saved running services info + Hardware info 
  
  like cpu information will be in `/proc/cpuinfo` 
  
  ```bash
  cat /proc/cpuinfo 
  ```
  
  > when shotdown proc dir will be deleted and if you booted from USB and mounted sys you will not able to see /proc and while troublshooting of system boot feliar you should mount bind for /proc and some drivers like
  > 
  > ```bash
  > mount --bind /dev/ /mnt/dev
  > mount --bind /sys/ /mnt/sys
  > mount --bind /proc/ /mnt/proc
  > ```

> proc READ ONLY not READ WRITE . 
> 
> kernel who's have access to write there 
> 
> and root but root by using force

---

### some Short-Cuts

1. cd 
   
       `cd -` cd to last dir i was there     

```bash
cd /root/Downloads
cd /home
cd - == cd /root/Downloads 
# and sometimes you forget whre you was so use
cd - 
```

`cd ~usernam`  ==  `cd /home/username`

2. `touch` for Creating empty `text` File  

```bash
touch file file1 file2 ...
```

> will Creat empty 3 files 

### short term or for loop with touch in bash scripting

```bash
root@G580:~/test# touch file{1..40}
root@G580:~/test# ls
file1   file13  file17  file20  file24  file28  file31  file35  file39  file6
file10  file14  file18  file21  file25  file29  file32  file36  file4   file7
file11  file15  file19  file22  file26  file3   file33  file37  file40  file8
file12  file16  file2   file23  file27  file30  file34  file38  file5   file9
```

#### Another Short Term

```bash
root@G580:~/test# mkdir file{1..40..5}
root@G580:~/test# ls
file1  file11  file16  file21  file26  file31  file36  file6
```

> this bash code it's adding old + new = filenumberX
> 
> ex file{15..300..15}
> 
> will be  
> 
> fiile(15+15)     => file30
> 
> file(30+15)      => file45
> 
> file(45+15)     => file60
> 
> and so on

### demo

```bash
root@G580:~/test# touch file{15..300..15}
root@G580:~/test# ls 
file105  file135  file150  file180  file210  file240  file270  file30   file45  file75
file120  file15   file165  file195  file225  file255  file285  file300  file60  file90
```

> When you touch new file based on the same name of old file  nothing will be happen but updating time scema "file info & data tiime & Creation time "



# Day 4

`Tree` It's command to show list directroy as tree 

```bash
root@G580:/var/log/mysql# tree
.
├── error.log
├── error.log.1.gz
├── nothing
│   ├── nothing1
│   ├── nothing2
│   ├── nothing3
│   ├── nothing4
│   └── nothing5
└── testing
    ├── file1
    ├── file2
    ├── file3
    ├── file4
    └── file5

2 directories, 12 files
```

`mkdir`  : Make Directory 

```bash
mkdir new_dir # make new dir called new_dir 
mkdir newfile{1..4} # make new 4-directorys called new_dir1,new_dir2_newdir_3,new_dir4
mkdir temp/dir # if temp not already directory exists will get error to fix this use -p 
mkdir -p temp/dir/testing/nothing/
```

`cp`  : copy 

```bash
cp source desctnation
cp /file/ /backup_file/
# when trying to use cp with directorys like make backup from /etc/
# use 
cp -R /etc/ /backup/
# if you wanna copy dir with special name 
cp -r /etc/ /backup/new_etc
```

`cat` : reading text files

```bash
root@G580:~# cat msg 
This is msg file and you can read me using cat msg :) .
```

`mv` it's `cp` but cp don't delete source

```bash
root@G580:~/labs# touch file{1..4}
root@G580:~/labs# mkdir back_up
root@G580:~/labs# tree
.
├── back_up
├── file1
├── file2
├── file3
└── file4
1 directory, 4 files
root@G580:~/labs# mv file* back_up/
root@G580:~/labs# tree
.
└── back_up
    ├── file1
    ├── file2
    ├── file3
    └── file4
1 directory, 4 files
```
