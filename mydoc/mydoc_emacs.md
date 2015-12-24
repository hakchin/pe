---
title: Introduction
tags: [getting_started]
audience: field engineers, clients
type: first_page
homepage: true
---

## Reference Sites
* [emacs howto](https://hakchin.wordpress.com/2015/12/04/emacs-howto/)
* [Emacs를 쓰고 싶지만 허들이 높아 보이는 사람들을 위한 조언](http://zeph1e.tistory.com/79)
* [Absolute Beginner's Guide to Emacs](http://www.jesshamrick.com/2012/09/10/absolute-beginners-guide-to-emacs/)



## Installation
> brew install emacs --HEAD --use-git-head --with-cocoa --with-gnutls --with-rsvg --with-imagemagick



## Shortcuts
* block 잡기: control + space 대신에 control + shift + space를 사용할 수 있다.
* copy 하기
* paste 하기
* cut 하기



## emacs howto

* 인용:[ http://vovheas104.blog.me/220495382624](http://vovheas104.blog.me/220495382624)

<table>
  <tr>
    <td>1</td>
    <td>$ emacs -nw -q sample</td>
  </tr>
</table>


* -nw 옵션은 emacs 커맨드라인에서 반드시 첫 번째 옵션으로 나와야 하며, emacs 에게 X 인터페이스(GUI)를 사용하지 않게 지시한다.

* -q 옵션은 emacs 에게 ~/.emacs 시작 파일을 읽지 않게 지시하는 옵션이다.

* 시작 파일을 읽지 않으면 emacs가 표준 방식으로 동작한다는 것을 보장할 수 있다.

* 위 명령은 emacs를 시작하고 sample 이라는 파일을 버퍼로 읽어 들이며 그것의 내용을 화면이나 윈도우에 보여준다.

* 버퍼의 저장과 불러오기

    * emacs 는 세션 동안 버퍼에 대해서 어떤 변경을 했는가에 상관없이 사용자가 버퍼의 내용을 저장하기 전까지 관련 파일의 내용은 변하지 않는다.

    * 버퍼를 저장하지 않은 채 emacs를 끝내면 파일의 내용은 변경되지 않으며, emacs는 세션 동안 했던 작업을 모두 버린다.

* 저장방법 control-x , control-s

* emacs로 파일을 작업하던 중 다른 파일을 편집하고 싶다면 (emacs 에서는 파일 편집을 바파일 방문이라 말한다)

* control-x control-f

    * 명령으로 새 파일을 emacs의 새 버퍼로 복사할 수 있다.

    * emacs는 파일명을 물어보고 해당 파일을 새 버퍼로 읽어 들이며 현재 윈도우에 그 버퍼를 표시한다.




## PDF Download Option for Help Material

If you would like to download this help file as a PDF, you can do so here. The PDF is comprehensive of all the content in the online help.   

<a target="_blank" class="noCrossRef" href="files/{{site.pdf_file_name}}"><button type="button" class="btn btn-default" aria-label="Left Align"><span class="glyphicon glyphicon-download-alt" aria-hidden="true"></span> PDF Download</button></a>

The PDF contains a timestamp in the header indicating when it was last generated. 
