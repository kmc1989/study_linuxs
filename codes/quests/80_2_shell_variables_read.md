# 문제 예시
인자와 read를 함께 사용하여 변수 조합 출력

~$ shell_read.sh agument_first
 read input : read_first

input values : agument_first read_first

# 명령어
```shell
[mincheolkim@localhost Downloads]$ nano shell_read.sh
# shell_read.sh 파일 내용 출력 EOF
[mincheolkim@localhost Downloads]$ cat shell_read.sh
# first value = $1
# second value = V_READ_INPUT

read -p "read input : " V_READ_INPUT

echo "input values : $1 $V_READ_INPUT"
# EOF
[mincheolkim@localhost Downloads]$ source shell_read.sh argument_first
read input : read_first
input values : argument_first read_first

```
