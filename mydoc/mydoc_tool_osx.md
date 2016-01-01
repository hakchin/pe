---
title: osx
keywords: osx, command, terminal
last_updated: December 26, 2015
tags: [getting_started]
summary: "I use this theme for sophisticated single_sourcing projects that I work on as a professional technical writer."
---

## Shortcut
* [Mac OS X Keyboard Shortcuts](http://pc.net/resources/shortcuts/mac_os_x)
* [별도의 소프트웨어 설치없이 OS X 시스템 한영 전환을 Shift + Space 단축키로 변경하는 방법](http://macnews.tistory.com/297)


## Full Keyboard Access

```
control+F1

  Toggle Full Keyboard Access on/off

control+F2 (or control+M)

  Focus keyboard control on menu bar

control+F3 (or control+D)

  Focus keyboard control on Dock

control+F4 (or control+W)

  Focus keyboard control on active Window or cycle to next window

control+F5 (or control+T)

  Focus keyboard control on toolbar

control+F6 (or control+U)

  Focus keyboard control on palette (utility window)

control+F7

  In windows and dialogs, switch focus to text boxes/lists/controls

arrow keys

  Navigate active item

return, enter, or spacebar

  Select highlighted item

return or enter

  Select default dialog control (OK, Yes, No, Save, Open, etc.)

escape

  Cancel action, menu, or dialog
```

## package manager

* brew
* gem


## Files

### Symbolic Link

* 생성
  * Example > ln -s /mnt/hgfs/J/fileserver /fileserver
* 삭제

### ditto
* OS X version of RoboCopy

```
  ditto -rsrcFork -V /path to/folder to copy /new destination
  ditto -V /path to/folder to copy /new destination
```


### cp & scp
* Directory copy

```
. 디렉트로와 디렉토리 안의 내용까지 다 복사
[root@oss2 testdir]# cp -r doc doc2

[root@oss2 testdir]# ls
doc/  doc2/  emptyfile.txt

[root@oss2 testdir]# ls doc2/
emptyfile.txt  kkk.txt

. 아래와 같이도 시도해 보자. (디렉토리 안의 모든 것을 목표 디렉토리에 복사한다.)
[root@oss2 testdir]# cp -r doc/* doc2
```

* scp command
  * [gpadmin@smdw htl]$ scp sdw15:/data1/bmt/sql/* ~/htl
  * scp -P 9061 basics.source postgres@hakchin.iptime.org:/var/lib/pgsql


## Network

## Linux Commands
  * which : file 의 위치를 찾아준다.
  * ifdown

```
ifdown eth0
```

## System


### 메모리 파악하기

*[리눅스 메모리 확인하기 (top, smaps)](http://blog.naver.com/PostView.nhn?blogId=hermet&logNo=203507029&parentCategoryNo=&categoryNo=29&viewDate=&isShowPopularPosts=true&from=search)


## Utility

* [Eight Terminal Utilities Every OS X Command Line User Should Know](http://lifehacker.com/eight-terminal-utilities-every-os-x-command-line-user-s-1593793109)
