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

* 1-999 They're for services ex apache have user called web and so on with another services like FTP , SMTP ...

`all users saved in  etc/passwd`

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

* `media` , `mount` , `mnt`

* used for mounting files and accessing removable media ex CD-ROM and USB or any another Mircocontroller Like raspberry pi
  
  > you can remove it and mount disks any where but it comes as stander 
  
  ```bash
  mount /dev/sda1 /mnt/
  mount /dev/sdb1 /media/
  mount /dev/sdc1 /mount/
  or any another endpoint
  mount /dev/sda3 /usr/local_mount/
  ```

* `run`      :  running process

* `opt`      : optinal files you can remove it

* `srv`      : optinal files like opt .  

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
