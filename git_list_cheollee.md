##Git 
### Pull : 다른사람이 저장소에 올려둔 파일을 내 로컬로 당겨올 때 이용한다.
### Push : 내파일을 저장소에 업로드한다.

1. 폴더에 접속하고
2. Git clone url
3. url은 git의 레파지토리가 생성된 레파지토리 url을 설정한다 
	* 내가  아이디의 레파지토리 https://github.com/yangcheollee/team-asan.git
	* 과장님의 레파지토리 : https://github.com/bluermind/team-asan.git
	* Git과 폴더의 동기화 완료
	* Git status => 커밋 할 폴더의 상태 확인
 

![커밋전](http://postfiles14.naver.net/MjAxNzA3MDNfMyAg/MDAxNDk5MDY2MDY4Nzc4.hxRb8N1UL5qbKm0nAUmUWFlzj887DtOc1V8hjTf_faEg.9cS2xXNx01sIFsP066Gt91rr9iOGh1hJPnFQsfgjvQ8g.PNG.ycy122/git1.png?type=w2)

### oomph.docx 파일이 커밋되지 않고 만들어져만 있는상태
### 커밋을 해야하는 파일 목록 : oomph.doc

---
###Git add oomph.docx  => 파일을 서버에 올린다.
### Git status
 
![status](http://postfiles16.naver.net/MjAxNzA3MDNfMjA4/MDAxNDk5MDY2MDY4OTUy.r5e8cBdxpwtOftdWDEImJe-x9vJz6i4dx6uBLoIPlSMg.18Yed1qpFsWrTFwoK84lFgU1rTMzstVuVpscoqDiypgg.PNG.ycy122/git2.png?type=w2)



###Git remote –v => 현재 설정되어져 있는 git url을 확인
 
![remote](http://postfiles15.naver.net/MjAxNzA3MDNfMTQ2/MDAxNDk5MDY2MDY5NDY3.QJULvjtIzrVfxSG08BlZ2WetjqFNjaB7-bSrhJQY0jIg.h4UJZOotsXm1LAhz-JY4deJCg3faMKj83rU3XBbRXB4g.PNG.ycy122/git3.png?type=w2)

###Git commit –m “변경내용 표시”

![commit](http://postfiles12.naver.net/MjAxNzA3MDNfMjYy/MDAxNDk5MDY2MDY5OTY3.qYO-CRcA61xEAPDIxXQz49CTcIJNbtHY0k6ErD8XNn8g.XcaeJ5Q32nceh6mo-fJBxi8mAHdyUySP2wWLUSbu5lgg.PNG.ycy122/git4.png?type=w2)
 

###Git push origin master => 로컬에 커밋한 자료를 서버에 업로드

![push](http://postfiles14.naver.net/MjAxNzA3MDNfMjMy/MDAxNDk5MDY2MDcwMjk3.caPfGSbWSlWqrbJ3Gh-o1bTkcIzMY0EkZxpGsMBKPrgg.eTeZHXy7IYuP9JNKDYDAdiR5apKerNh6OT2Iozhfj1kg.PNG.ycy122/git5.png?type=w2) 



## Git branch “이름설정”
### branch upload할때의 이름

## Git checkout “이름”


## git rm 폴더/파일 삭제

git rm -r 폴더/파일 이름

현재 git에 업로드 되어있거나 서버에 있는 파일/폴더 삭제

	=> commit시켜줘서 git과 로컬에 환경을 맞추어 준다.


### 새로운 프로젝트 업로드시

md파일 하나 생성하고 -> 브랜치 하나 생
성하고 checkout으로 생성한 브랜치로 이동
생성된 프로젝트 md파일을 로컬에 생성하고 싱크확인

### git pull origin master

### git push origin "브렌치이름"

