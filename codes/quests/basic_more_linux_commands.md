# 연습문제 1: 기본 파일 시스템 탐색
## 1-1. 현재 위치 확인 및 이동
### 1) 현재 작업 디렉터pw리의 절대 경로를 출력하시오.
### 2) 홈 디렉터리로 이동하시오.
### 3) 루트 디렉터리(/)로 이동하시오.
### 4) 다시 홈 디렉터리로 돌아가시오.
```
[mincheolkim@localhost ~]$ pwd
/home/mincheolkim
[mincheolkim@localhost ~]$ cd /
[mincheolkim@localhost /]$ pwd
/
[mincheolkim@localhost /]$ cd /home
[mincheolkim@localhost home]$ pwd
/home
[mincheolkim@localhost home]$ 
```
## 1-2. 디렉터리 내용 확인
### 1) 현재 디렉터리의 파일과 폴더 목록을 출력하시오.
### 2) 숨김 파일을 포함한 모든 파일의 상세 정보를 출력하시오.
### 3) /etc 디렉터리의 내용을 확인하시오.

```
[mincheolkim@localhost home]$ ls
mincheolkim
[mincheolkim@localhost home]$ ls -la
total 4
drwxr-xr-x.  3 root        root          25 Jul 16 10:54 .
dr-xr-xr-x. 18 root        root         235 Jul 16 10:12 ..
drwx------. 14 mincheolkim mincheolkim 4096 Jul 16 10:54 mincheolkim
[mincheolkim@localhost home]$ cd /etc
[mincheolkim@localhost etc]$ ls
accountsservice          firewalld       makedumpfile.conf.sample  samba
adjtime                  flatpak         man_db.conf               sane.d
aliases                  fonts           mcelog                    sasl2
alsa                     foomatic        microcode_ctl             security
alternatives             fprintd.conf    mime.types                selinux
anacrontab               fstab           mke2fs.conf               services
appstream.conf           fuse.conf       modprobe.d                sestatus.conf
asound.conf              fwupd           modules-load.d            setroubleshoot
at.deny                  gcrypt          motd                      sgml
audit                    gdm             motd.d                    shadow
authselect               geoclue         mtab                      shadow-
avahi                    glvnd           multipath                 shells
bash_completion.d        gnupg           nanorc                    skel
bashrc                   GREP_COLORS     netconfig                 smartmontools
bindresvport.blacklist   groff           NetworkManager            sos
binfmt.d                 group           networks                  speech-dispatcher
bluetooth                group-          nftables                  ssh
brlapi.key               grub2.cfg       nsswitch.conf             ssl
brltty                   grub.d          nsswitch.conf.bak         sssd
brltty.conf              gshadow         nvme                      statetab.d
chromium                 gshadow-        openldap                  subgid
chrony.conf              gss             opt                       subgid-
chrony.keys              host.conf       os-release                subuid
cifs-utils               hostname        ostree                    subuid-
cockpit                  hosts           PackageKit                sudo.conf
containers               hp              pam.d                     sudoers
cron.d                   inittab         papersize                 sudoers.d
cron.daily               inputrc         passwd                    sudo-ldap.conf
cron.deny                iscsi           passwd-                   sysconfig
cron.hourly              issue           pbm2ppa.conf              sysctl.conf
cron.monthly             issue.d         pinforc                   sysctl.d
crontab                  issue.net       pkcs11                    systemd
cron.weekly              kdump           pkgconfig                 system-release
crypto-policies          kdump.conf      pki                       system-release-cpe
crypttab                 kernel          plymouth                  terminfo
csh.cshrc                keys            pm                        tmpfiles.d
csh.login                keyutils        pnm2ppa.conf              tpm2-tss
cups                     krb5.conf       polkit-1                  trusted-key.key
cupshelpers              krb5.conf.d     popt.d                    tuned
dbus-1                   ld.so.cache     printcap                  udev
dconf                    ld.so.conf      profile                   udisks2
debuginfod               ld.so.conf.d    profile.d                 updatedb.conf
default                  libaudit.conf   protocols                 UPower
depmod.d                 libblockdev     pulse                     usb_modeswitch.conf
dhcp                     libibverbs.d    qemu-ga                   vconsole.conf
DIR_COLORS               libnl           ras                       vimrc
DIR_COLORS.lightbgcolor  libpaper.d      rc.d                      virc
dnf                      libreport       rc.local                  vmware-tools
dnsmasq.conf             libssh          redhat-release            vulkan
dnsmasq.d                libuser.conf    request-key.conf          wgetrc
dracut.conf              locale.conf     request-key.d             wireplumber
dracut.conf.d            localtime       resolv.conf               wpa_supplicant
egl                      login.defs      rocky-release             X11
enscript.cfg             logrotate.conf  rocky-release-upstream    xattr.conf
environment              logrotate.d     rpc                       xdg
ethertypes               lsm             rpm                       xml
exports                  lvm             rsyncd.conf               yum
favicon.png              machine-id      rsyslog.conf              yum.conf
filesystems              magic           rsyslog.d                 yum.repos.d
firefox                  mailcap         rwtab.d
```
# 연습문제 2: 디렉터리 및 파일 생성
## 2-1. 디렉터리 구조 생성
### 다음과 같은 디렉터리 구조를 생성하시오:
```
practice/

├── documents/
│   ├── reports/ls
│   └── notes/
├── images/
└── backup/
```
```
[mincheolkim@localhost ~]$ pwd
/home/mincheolkim
[mincheolkim@localhost ~]$ mkdir documents
[mincheolkim@localhost ~]$ mkdir images
[mincheolkim@localhost ~]$ mkdir backup
[mincheolkim@localhost ~]$ cd documents
[mincheolkim@localhost documents]$ mkdir reports
[mincheolkim@localhost documents]$ mkdir notes
[mincheolkim@localhost documents]$ cd reports
[mincheolkim@localhost reports]$ mkdir ls
[mincheolkim@localhost reports]$ cd ..
[mincheolkim@localhost documents]$ cd ..
[mincheolkim@localhost ~]$ tree
.
├── backup
├── Desktop
├── documents
│   ├── notes
│   └── reports
│       └── ls
├── Documents
├── Downloads
├── images
├── Music
├── Pictures
├── Public
├── Templates
└── Videos
[mincheolkim@localhost ~]$ mkdir practice
[mincheolkim@localhost ~]$ mv documents practice
[mincheolkim@localhost ~]$ ls
backup   Documents  images  Pictures  Public     Videos
Desktop  Downloads  Music   practice  Templates
[mincheolkim@localhost ~]$ tree
.
├── backup
├── Desktop
├── Documents
├── Downloads
├── images
├── Music
├── Pictures
├── practice
│   └── documents
│       ├── notes
│       └── reports
│           └── ls
├── Public
├── Templates
└── Videos

15 directories, 0 files

```
## 2-2. 파일 생성 및 내용 작성
### 1) practice/documents/ 디렉터리에 readme.txt 파일을 생성하고 "Hello Linux!"라는 내용을 작성하시오.
### 2) practice/notes/ 디렉터리에 memo.txt 파일을 생성하고 "Linux 명령어 연습 중"이라는 내용을 작성하시오.
```
[mincheolkim@localhost documents]$ "Hello Linux!" > readme.txt
bash: Hello Linux!: command not found...
[mincheolkim@localhost documents]$ ls
notes  readme.txt  reports
[mincheolkim@localhost documents]$ ls -l
total 0
drwxr-xr-x. 2 mincheolkim mincheolkim  6 Jul 16 11:03 notes
-rw-r--r--. 1 mincheolkim mincheolkim  0 Jul 16 11:13 readme.txt
drwxr-xr-x. 3 mincheolkim mincheolkim 16 Jul 16 11:03 reports
[mincheolkim@localhost documents]$ cat readme.txt
[mincheolkim@localhost documents]$ cd ..
[mincheolkim@localhost practice]$ ls
documents
[mincheolkim@localhost practice]$ cd documents
[mincheolkim@localhost documents]$ ls
notes  readme.txt  reports
[mincheolkim@localhost documents]$ cd notes
[mincheolkim@localhost notes]$ ls
[mincheolkim@localhost notes]$ touch memo.txt
[mincheolkim@localhost notes]$ ls
memo.txt
[mincheolkim@localhost notes]$ 

```
# 연습문제 3: 파일 내용 확인 및 조작
## 3-1. 파일 내용 출력
### 1) 앞서 생성한 readme.txt 파일의 내용을 출력하시오.
### 2) memo.txt 파일의 내용을 출력하시오.
```
[mincheolkim@localhost documents]$ pwd
/home/mincheolkim/practice/documents
[mincheolkim@localhost documents]$ cat readme.txt
[mincheolkim@localhost documents]$ ls
notes  readme.txt  reports
[mincheolkim@localhost documents]$ cd notes
[mincheolkim@localhost notes]$ ls
memo.txt
[mincheolkim@localhost notes]$ cat memo.txt
```
## 3-2. 파일 복사
### 1) readme.txt 파일을 backup/ 디렉터리에 복사하시오.
### 2) documents/ 디렉터리 전체를 backup/ 디렉터리에 복사하시오.
```
[mincheolkim@localhost practice]$ ls
backups  documents
[mincheolkim@localhost practice]$ cp -r documents /home/mincheolkim/practice/backups
[mincheolkim@localhost practice]$ ls
backups  documents
[mincheolkim@localhost practice]$ cd backups
[mincheolkim@localhost backups]$ ls
documents
[mincheolkim@localhost backups]$ tree
.
└── documents
    ├── notes
    │   └── memo.txt
    ├── readme.txt
    └── reports
        └── ls

4 directories, 2 files
[mincheolkim@localhost backups]$ 
```
# 연습문제 4: 파일 이동 및 이름 변경
## 4-1. 파일 이동
### 1) memo.txt 파일을 documents/ 디렉터리로 이동하시오.
### 2) images/ 디렉터리를 practice/media/로 이름을 변경하시오.
```
[mincheolkim@localhost notes]$ ls
memo.txt
[mincheolkim@localhost notes]$ mv memo.txt /home/mincheolkim/practice/documents
[mincheolkim@localhost notes]$ ls
[mincheolkim@localhost notes]$ cd ..
[mincheolkim@localhost documents]$ ls
memo.txt  notes  readme.txt  reports
[mincheolkim@localhost documents]$ cd ..
[mincheolkim@localhost practice]$ ls
backups  documents
[mincheolkim@localhost practice]$ tree
.
├── backups
│   └── documents
│       ├── notes
│       │   └── memo.txt
│       ├── readme.txt
│       └── reports
│           └── ls
└── documents
    ├── memo.txt
    ├── notes
    ├── readme.txt
    └── reports
        └── ls

9 directories, 4 files
[mincheolkim@localhost practice]$ mkdir images
[mincheolkim@localhost practice]$ ls
backups  documents  images
[mincheolkim@localhost practice]$ ls
backups  documents  images
[mincheolkim@localhost practice]$ cd /home/mincheolkim/practice/documents
[mincheolkim@localhost documents]$ cd /home/mincheolkim/practice/documents/notes
[mincheolkim@localhost notes]$ mv memo.txt /home/mincheolkim/practice/documents
mv: cannot stat 'memo.txt': No such file or directory
[mincheolkim@localhost notes]$ ls
[mincheolkim@localhost notes]$ pwd
/home/mincheolkim/practice/documents/notes
[mincheolkim@localhost notes]$ tree
.

0 directories, 0 files
[mincheolkim@localhost notes]$ cd ..
[mincheolkim@localhost documents]$ tree
.
├── memo.txt
├── notes
├── readme.txt
└── reports
    └── ls

3 directories, 2 files
[mincheolkim@localhost documents]$ cd ..
[mincheolkim@localhost practice]$ ls
backups  documents  images
[mincheolkim@localhost practice]$ mv images practice/media
mv: cannot move 'images' to 'practice/media': No such file or directory
[mincheolkim@localhost practice]$ ls
backups  documents  images
[mincheolkim@localhost practice]$ mv images media
[mincheolkim@localhost practice]$ ls
backups  documents  media
[mincheolkim@localhost practice]$ 
```
## 4-2. 파일 이름 변경
### 1) readme.txt를 introduction.txt로 이름을 변경하시오.
### 2) memo.txt를 study_notes.txt로 이름을 변경하시오.
```
[mincheolkim@localhost documents]$ ls
memo.txt  notes  readme.txt  reports
[mincheolkim@localhost documents]$ mv readme.txt introduction.txt
[mincheolkim@localhost documents]$ mv memo.txt study_notes.txt
[mincheolkim@localhost documents]$ ls
introduction.txt  notes  reports  study_notes.txt
```
# 연습문제 5: 종합 실습
## 5-1. 프로젝트 디렉터리 생성
### 1) 다음 요구사항에 따라 프로젝트 디렉터리를 생성하시오:
### 2) my_project/라는 최상위 디렉터리 생성
### 3) 하위에 src/, docs/, tests/, config/ 디렉터리 생성
### 4) src/ 디렉터리에 main.py 파일 생성 (내용: "# Main Python File")
### 5) docs/ 디렉터리에 README.md 파일 생성 (내용: "# My Project Documentation")
### 6) config/ 디렉터리에 settings.conf 파일 생성 (내용: "# Configuration File")
```
[mincheolkim@localhost ~]$ mkdir my_project
[mincheolkim@localhost ~]$ cd my_project
[mincheolkim@localhost my_project]$ ls
[mincheolkim@localhost my_project]$ mkdir src
[mincheolkim@localhost my_project]$ mkdir docs tests config
[mincheolkim@localhost my_project]$ ls
config  docs  src  tests
[mincheolkim@localhost my_project]$ cd src
[mincheolkim@localhost src]$ cat main.py
cat: main.py: No such file or directory
[mincheolkim@localhost src]$ ls
[mincheolkim@localhost src]$ touch main.py
[mincheolkim@localhost src]$ ls
main.py
[mincheolkim@localhost src]$ cd ..
[mincheolkim@localhost my_project]$ cd docs
[mincheolkim@localhost docs]$ touch README.md
[mincheolkim@localhost docs]$ cd ..
[mincheolkim@localhost my_project]$ cd config
[mincheolkim@localhost config]$ touch settings.conf
[mincheolkim@localhost config]$ ls
settings.conf
```
## 5-2. 백업 및 정리
### 1) 전체 my_project/ 디렉터리를 my_project_backup/으로 복사하시오.
### 2) my_project/src/main.py 파일을 my_project/src/app.py로 이름을 변경하시오.
### 3) my_project/docs/README.md 파일을 my_project/ 디렉터리로 이동하시오.
```
[mincheolkim@localhost config]$ cd ..
[mincheolkim@localhost my_project]$ cd ..
[mincheolkim@localhost ~]$ cp my_project my_project_backup
cp: -r not specified; omitting directory 'my_project'
[mincheolkim@localhost ~]$ cp -r my_project my_project_backup
[mincheolkim@localhost ~]$ ls
backup   Documents  images  my_project         Pictures  Public     Videos
Desktop  Downloads  Music   my_project_backup  practice  Templates
[mincheolkim@localhost ~]$ mv myproject/src/main.py my_project/src/app.py
mv: cannot stat 'myproject/src/main.py': No such file or directory
[mincheolkim@localhost ~]$ mv my_project/src/main.py my_project/src/app.py
[mincheolkim@localhost ~]$ tree
.
├── backup
├── Desktop
├── Documents
├── Downloads
├── images
├── Music
├── my_project
│   ├── config
│   │   └── settings.conf
│   ├── docs
│   │   └── README.md
│   ├── src
│   │   └── app.py
│   └── tests
├── my_project_backup
│   ├── config
│   │   └── settings.conf
│   ├── docs
│   │   └── README.md
│   ├── src
│   │   └── main.py
│   └── tests
├── Pictures
├── practice
│   ├── backups
│   │   └── documents
│   │       ├── notes
│   │       │   └── memo.txt
│   │       ├── readme.txt
│   │       └── reports
│   │           └── ls
│   ├── documents
│   │   ├── introduction.txt
│   │   ├── notes
│   │   ├── reports
│   │   │   └── ls
│   │   └── study_notes.txt
│   └── media
├── Public
├── Templates
└── Videos

31 directories, 10 files
[mincheolkim@localhost ~]$ mv my_project/docs/README.md my_project
[mincheolkim@localhost ~]$ tree
.
├── backup
├── Desktop
├── Documents
├── Downloads
├── images
├── Music
├── my_project
│   ├── config
│   │   └── settings.conf
│   ├── docs
│   ├── README.md
│   ├── src
│   │   └── app.py
│   └── tests
├── my_project_backup
│   ├── config
│   │   └── settings.conf
│   ├── docs
│   │   └── README.md
│   ├── src
│   │   └── main.py
│   └── tests
├── Pictures
├── practice
│   ├── backups
│   │   └── documents
│   │       ├── notes
│   │       │   └── memo.txt
│   │       ├── readme.txt
│   │       └── reports
│   │           └── ls
│   ├── documents
│   │   ├── introduction.txt
│   │   ├── notes
│   │   ├── reports
│   │   │   └── ls
│   │   └── study_notes.txt
│   └── media
├── Public
├── Templates
└── Videos

31 directories, 10 files
```
