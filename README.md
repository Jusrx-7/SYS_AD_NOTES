# Linux SYS_ADMIN Notes

#### This is My own Notes

#### This Repo Structed by days

---

## Day 1 : was Basics info & installation ;

## Day 2 : Basics Commands ;



```bash

```

## Day 3 : More Basics Commands ;

### Command Line Basics :

1. __`pwd`__
   
   ```bash
   $: pwd
   /home/xy
   ```

2. __`ls`__
   
   ```bash
   ls
   DBFiles  file1
   ```

3. **`su`**
   
   ```bash
   # Switch from user to nother user
   $: whoami # command tell you who are you .
   root 
   $: su - xy  # i will be xy user  
   ```

4. **`cal`**
   
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

5. **`date`**
   
   ```bash
   date
   Wed Jan 24 12:09:14 PM EET 2024
   ```

6. **`eject`** __disconnect with removable media__
   
   ```bash
   eject # eject only opens CD-ROM 
   eject /dev/sda # disconnect with sda drive 
   ```

<img title="" src="https://upload.wikimedia.org/wikipedia/commons/7/70/Sony_CRX310S-Internal-PC-DVD-Drive-Opened.jpg" alt="CD-ROM" width="537" data-align="center">

7. `TTY`'s and `chvt`
   
   ```bash
   tty # Get TTY number I in 
   chvt 5 # Change From TTY I in to TTY 5
   ```



### Linux File SYS Structure

![CD-ROM](https://1.bp.blogspot.com/-UQ7-sWd_J4w/WmhKIFx7_fI/AAAAAAAAHIE/tixi5SsyI5YzoJygq_JQKL50axe2cAcrQCLcBGAs/s1600/Untitled.png)

* `home`    : home Direcetory of any user will be created

* `root`    :  root's Direcetory only for him 

* `boot`    :  boot files There

* `etc`      :  every Configration will be saved into it

* `bin`      : all bin files there 

* `sbin`    : system binarys For root only

* `dev`      :  devices file + Special Files ex __`/dev/null`__,__`/dev/zero`__ and more
  
  >           __`EVERY THING IS FILE in Linux`__

* `tmp`      : temp files 

* `usr`      : Shared File between users 

* `var`      : variable files for services Like Apache , FTP , SMTP , and so on  

* `media` , `mount` , `mnt`  : Mounting Points 
  
  ```bash
  mount /dev/sda1 /mnt/
  mount /dev/sdb1 /media/
  mount /dev/sdc1 /mount/
  or any another endpoint
  mount /dev/sda3 /usr/local_mount/
  ```

* `run` ,`sys` , `proc`   :  Kernel handle then + services info there and Hardware info There  

* `opt`,`srv`      : optinal files __you can remove it___

* `lib`      :  Library files like for __`iostream`__ for c++ and so on with another lang 

---

### some Short-Cuts

```bash
SHORT-CUTs
cd - # return you into last directory you was there
cd ~username == cd /home/username 
touch file1 # Creating New file called file1 
touch file{1..4} # Create 4 Files starts from 1 to 4 called fileX
mkdir dir{1..50..2}#  for i=1 ; i>50 ; i+2
Demo :
$: touch file{15..300..15}
$: ls 
file105  file135  file150  file180  file210  file240  file270  file30   file45  file75
file120  file15   file165  file195  file225  file255  file285  file300  file60  file90
```

---

## Day 4 : More Commands

`Tree` show directroy as tree 

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
# if perant dir not even exist create him and same with chiled who's perant to who's under him 
# like temp is perant to dir and dir is child for temp but perant for testing and so on  
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

---

## Day 5 : Basics Administration

#### info :

> **Normal users** There ID-Range : Starts From 1000
> 
> **root** His ID only 0
> 
> **Services** There ID-Range : From 1 To 999

- > all users saved in etc/passwd

- ```bash
  cat /etc/passwd
  xy:x:1000:1000:xy,,,:/home/xy:/bin/bash
  mysql:x:132:139:MySQL Server,,,:/nonexistent:/bin/false
  geoclue:x:133:140::/var/lib/geoclue:/usr/sbin/nologin
  ```

### Basics Commands with users

#### `useradd` :

> users info saved into `/etc/passwd`

```bash
# Basics user addition
useradd web_adm_usr
# after adding group and want to add new user in this group 
useradd -g WebAD web_adm_usr # web_adm_usr will be in WebAD group
# WebAD group will be The Primary Group for web_adm_usr
userdel web_adm_usr # will remove user but leave his dir
userdel web_adm_usr -r # remove everything for this user 
```

#### `groupadd` :

> groups info saved into `/etc/group`

```bash
groupadd DCAdmins
groupadd NetwrokAdmins
groupadd DBadmins
groupadd WebAD
```

#### `usermod` & `groupmod` to edit user & groups

```bash
# u have been added web_adm_usr
# so to add him to more then one group "Secondary Groups"
# use -G to add only one secondary group 
$: useradd web_adm_usr
$: id web_adm_ur
# userID                Primary Group ID(name)  Seconday Groups
uid=1001(web_adm_usr)   gid=1005(web_adm_usr)   groups=1005(web_adm_usr)
# when you use only -G he add update old seconday Group by new group and add both
$: usermod -G DCADM web_adm_usr
$: id web_adm_usr
uid=1001(web_adm_usr) gid=1005(web_adm_usr) groups=1005(web_adm_usr),1002(DCADM)
$: usermod -G NETAD web_adm_usr
$: id web_adm_usr
uid=1001(web_adm_usr) gid=1005(web_adm_usr) groups=1005(web_adm_usr),1003(NETAD)
#if you looked at secondary Group you will see it's replaced old one by new one
# to Fix this use -a with -G 
$: usermod -aG DCADM web_adm_usr
$: id web_adm_usr
# added more then one in secondary group
uid=1001(web_adm_usr) gid=1005(web_adm_usr) groups=1005(web_adm_usr),1002(DCADM),1003(NETAD)
# to replace old primary group use -g in usermod
$: usermod -g DCADM web_adm_usr
$: id web_adm_usr
uid=1001(web_adm_usr) gid=1002(DCADM) groups=1002(DCADM),1003(NETAD)
# so -g for Primary -G for Seconday *u can use -a with -g* you only have a one primary group


# renameing groups
groupmod -n "WEB_DEV" web_developers
```

#### reading `etc/passwd`

```bash
$: cat /etc/passwd
web_adm_usr:x:1001:1002::/home/web_adm_usr:/bin/sh
web_adm_usr : # user name
x: # is password but to more secure added x 
# and hash of passwords will be in /etc/shadow
#like my xy user password is $y$j9T$7r1EbrB9cAiFRIMAgkoI3.$DzvR9nLYCJGRK9oZa0iUWHAEhnhFeSqMApeUF51ExVC:19714:0:99999:7:::
# it's 123 :) and hash algorithms is SHA
1001 : # it's usrID 
1002 : # it's Primary group ID 
# between 1001 , 1002 it's a desription for user called GECOS Field  
# to add description use useradd -c or usermod -c 
usermod -c "this a web admin user" web_adm_usr 
$: tail  -n 1 /etc/passwd
web_adm_usr:x:1001:1003:this a web admin user:/home/web_adm_usr:/bin/sh
/home/web_adm_usr : # it's a home directory for this user
/bin/sh : # it's user shell path 
```

> users passwords will be in /etc/shadow
> 
> and groups passwords in /etc/gshadow 

### Permissions

```bash
We Have 3 permissions on any File 
1. User OWNER => RWX
2. Group OWNER => RWX
3. Other => RWX
and 1st 3 bits For user & 2nd 3 bits For Group & 3rd 3 Bits For Other & First bit For File Type
---------------------------------------------------------
-rw-r--r--
R = Read
W = Write 
X = Execute
- = File Type (- = normal File , d = Directory , b = Block Device , c = Char Device , l = Link File )
# char device like keyboard 
$: ll /dev/tty1 
crw--w---- 1 root tty 4, 1 Jan 24 08:19 /dev/tty1
# blok device like HardDisk or USB or floppy Disk
$: ll /dev/sda
brw-rw---- 1 root disk 8, 0 Jan 24 08:19 /dev/sda
Reading Permissions :
-rw-r--r--
    - File Type = normal File 
    rw- = user  can Read & Write on this File 
    r-- = Group can Read Only This File
    r-- = Other have same Group Permission 

Reading Permissions 
$: ls -la # some Linux Distro adding ll and do the same job of ls -la 
# to add ll Manual use alial 
$: alias ll="ls -la"
$: ll
total 8
drwxr-xr-x 2 root root 4096 Jan 23 16:31 .
drwxr-xr-x 3 root root 4096 Jan 23 16:31 ..
-rw-r--r-- 1 root root    0 Jan 23 16:31 file1
-rw-r--r-- 1 root root    0 Jan 23 16:31 file2
-rw-r--r-- 1 root root    0 Jan 23 16:31 file3
-rw-r--r-- 1 root root    0 Jan 23 16:31 file4

# Explaining
-rw-r--r-- 1 root root    0 Jan 23 16:31 file4
0. drwxr #File Type 
1.-rw-r--r-- # Permissions Read Write Execute
2. 1 # Link Counter
3. root # USER  OWNER
4. root # Group OWNER
5. 0 # file Size
6. Jan 23 16:31 # Last Access not Modifition Time
7. File4 # file name
```

#### Edit Permissions

```bash
$: ll file1 
-rw-r--r-- 1 root root 0 Jan 23 16:31 file1
$: chmod o+wx file1 
$: ll file1 
-rw-r--rwx 1 root root 0 Jan 23 16:31 file1*
$: chmod {a or }{+,-}{w,r,x} file1 # will remove x permission from all of them 
chmod a-x file1 # file1 will be file without exec permission
chmod ugo+wr,o-wrx # owner & group will get wr permissions and o will be null
# to apply permissions in all things in speical dir use -R 
$: chmod go-rwx
$: ll
drwx------ 2 root root 4096 Jan 24 10:42 DBFiles/
$: ll DBFiles/
-rw-r--r-- 1 root root    0 Jan 24 10:42 file1.db
-rw-r--r-- 1 root root    0 Jan 24 10:42 file2.db
-rw-r--r-- 1 root root    0 Jan 24 10:42 file3.db
-rw-r--r-- 1 root root    0 Jan 24 10:42 file4.db
# Directory got removed GO permissions but File who's inside This Dir not got the same permissions 
# to make all dir and the file inside this dir use -R
$: chmod -R go-wrx,u+rwx DBFiles/
$: ll
total 12
drwxr-xr-x 3 root root 4096 Jan 24 10:42 ./
drwxr-xr-x 3 root root 4096 Jan 23 16:31 ../
drwx------ 2 root root 4096 Jan 24 10:42 DBFiles/
$: ll DBFiles/
total 8
drwx------ 2 root root 4096 Jan 24 10:42 ./
drwxr-xr-x 3 root root 4096 Jan 24 10:42 ../
-rwx------ 1 root root    0 Jan 24 10:42 file1.db*
-rwx------ 1 root root    0 Jan 24 10:42 file2.db*
-rwx------ 1 root root    0 Jan 24 10:42 file3.db*
-rwx------ 1 root root    0 Jan 24 10:42 file4.db* 
```

#### file Permissions

| Symbol | means                                          |
|:------:|:----------------------------------------------:|
| read   | View                                           |
| write  | edit , del , overload , any kind under editing |
| exec   | run file                                       |

#### Direcotry Permissions

| Symbol | means                                        |
|:------:|:--------------------------------------------:|
| read   | ls this dir                                  |
| write  | add , Remove , Delete Directory              |
| exec   | cd dir , ls -l dir _-l :Long Listing Format_ |

#### `chown` : Change Ownership on files or Dir

```bash
chown username:group {filename,dir}
$: ll
drwx------ 2 root root 4096 Jan 24 10:42 DBFiles/
$: chown web_adm_usr:WEBAD DBFiles/
$: ll
drwx------ 2 web_adm_usr WEBAD 4096 Jan 24 10:42 DBFiles/
# changeing group only
chown :WEBAD DBFiles/
```

### Permission $Kind$

1. Symbolic Method 

2. Numeric method 

#### Symbol :

user owner =  $u$

group owner =  $g$

other = $o$ 

#### Numeric :

| Syntax | number |
|:------:|:------:|
| r      | 4      |
| w      | 2      |
| x      | 1      |

> U,G,O Every one of them have this 3 Numbers 4,2,1 

```bash
chmod 775 file1
# means user=rwx
# means Group=rwx
# means Other=rx
$: touch file1 
$: chmod 775 file1 
$: ll
total 12
-rwxrwxr-x 1 root root    0 Jan 24 11:48 file1*
```

## Day 6 : Redirection
