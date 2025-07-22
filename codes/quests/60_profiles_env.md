각 실습 후 su - 사용자명, ls -R ~/Downloads, cat 등을 통해 적용 여부를 확인하십시오.

🧪 환경 변수 및 초기화 스크립트 실습 문제
🔹 문제 1. 로그인 시마다 "Welcome, USERNAME" 메시지를 출력하시오.
조건:
현재 로그인한 사용자명을 포함할 것 ($USER)


로그인할 때마다 자동으로 출력되도록 설정할 것
```shell
[mincheolkim@localhost ~]$ cat .bash_profile
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
	. ~/.bashrc
fi

# User specific environment and startup programs
echo "Welcome, $USER"

[mincheolkim@localhost ~]$ su - mincheolkim
Password: 
Welcome, mincheolkim
```
🔹 문제 2. 로그인 시 사용자의 Downloads/ 폴더 내 일반 파일을 삭제하시오.
조건:
경로: ~/Downloads/

일반 파일만 삭제 (서브디렉토리, 숨김파일은 삭제하지 않음)


로그인 시 자동 실행
```shell
[mincheolkim@localhost ~]$ nano .bash_profile
[mincheolkim@localhost ~]$ cat .bash_profile
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
	. ~/.bashrc
fi

# User specific environment and startup programs
echo "Welcome, $USER"
rm ~/Downloads/*

[mincheolkim@localhost ~]$ su - mincheolkim
Password: 
Welcome, mincheolkim
rm: cannot remove '/home/mincheolkim/Downloads/practice': Is a directory
[mincheolkim@localhost ~]$ ls ./Downloads/
practice
```

🔹 문제 3. 로그인할 때마다 ~/Downloads/ 경로에 다음 구조로 디렉토리 및 파일을 자동 생성하도록 설정하시오.
생성 구조:
~/Downloads/
 └── auto_created/
      ├── info.txt
      └── logs/
           └── log.txt

조건:
파일에는 임의의 간단한 문자열이 들어갈 것


매 로그인마다 자동 생성
```shell
[mincheolkim@localhost ~]$ nano .bash_profile
[mincheolkim@localhost ~]$ cat .bash_profile
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
	. ~/.bashrc
fi

# User specific environment and startup programs
echo "Welcome, $USER"
rm ~/Downloads/*
mkdir -p ~/Downloads/auto_created/logs/
echo "information" > ~/Downloads/auto_created/info.txt
echo "log test" > ~/Downloads/auto_created/logs/log.txt

[mincheolkim@localhost ~]$ cd Downloads/
[mincheolkim@localhost Downloads]$ ls
auto_created  practice
[mincheolkim@localhost Downloads]$ tree
.
├── auto_created
│   ├── info.txt
│   └── logs
│       └── log.txt
└── practice
    └── permissions
        ├── deep_dir1
        │   └── deep_dir2
        │       └── secret.txt
        ├── file1.txt
        ├── file2.txt
        ├── private_dir
        │   └── confidential.txt
        └── public_dir
            └── info.txt

8 directories, 7 files
[mincheolkim@localhost Downloads]$ cat ./auto_created/info.txt
information
[mincheolkim@localhost Downloads]$ cat ./auto_created/logs/log.txt
log test
```
🔹 문제 4. /etc/profile을 수정하여, 로그인 시 모든 사용자에게 공지 메시지 /etc/login_notice.txt를 출력하도록 설정하시오.
조건:
출력 방식은 cat, echo 등 자유


시스템 전체 사용자에게 적용


/etc/login_notice.txt는 임의의 내용을 사전에 작성해 둘 것


sudo 권한 필요

```shell
[mincheolkim@localhost ~]$ su -
Password: 
This is login_notice test!
[root@localhost ~]# ls
anaconda-ks.cfg  permission_practice
[root@localhost ~]# pwd
/root
[root@localhost ~]# cd ../etc/
# nano profile 내용 추가
if [ -f /etc/login_notice.txt ]; then
    cat /etc/login_notice.txt
fi

[mincheolkim@localhost ~]$ su - mincheolkim
Password: 
This is login_notice test!
Welcome, mincheolkim
```
