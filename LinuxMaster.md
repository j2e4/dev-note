# 리눅스 마스터 준비

1802회 A형

```console
# ls -l lin.txt
-rwxrwxrwx. ihdman ihd 513 Dec 22 21:05 lin.txt
# chmod a=r lin.txt
```
Q. 해당 명령어의 결과  
A. -r--r--r--

**ls -l lin.txt 명령어 확인 결과**  
`-rwxrwxrwx. ihdman ihd 513 Dec 22 21:05 lin.txt`  

[접근 권한] 모든 사용자(소유자, 소유 그룹, 그 외 사용자) read write execute 가능  
    - (접근 권한이 'd'로 시작할 경우 directory를 의미)  
[소유자] ihdman  
[소유 그룹] ihd  
[파일 크기] 513  
[파일 수정 일자] 12/22 21:05  
[파일 이름] lin.txt  

**chmod 명령어 문자열 모드**  
`chmod a=r lin.txt`  
chmod [옵션] [레퍼런스][연산자][권한] [파일|디렉토리]  

* 레퍼런스  
u 소유자  
g 그룹  
o 그 외 사용자  
a 모든 사용자  

* 연산자  
\+ 기존 권한에 추가  
\- 기존 권한에서 제거  
= 해당 권한으로 변경  

* 권한  
r readable  
w writeable  
x executable  