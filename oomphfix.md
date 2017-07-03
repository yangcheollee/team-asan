# 이클립스 Oomph #
---

* 프로젝트에 사용되어지는 프로젝트 구성요소, 인스턴스의 설치와 구성을 더 쉽게하기 위한 도구를 제공해준다.  
* 개인 설정 기록, 원본체크아웃 환경설정을 통해 전체 개발 환경을 쉽게 설정할 수 있습니다. 
### => 실제로 편리한 것인지 Setup 파일의 분석이 필요하다. (자료조사가 부족한 상태)


## oomph 설정
* 이 설정을 통해서 프로젝트에 쉽게 참여가능하고 쉽게 구성하도록 하기위한다.
* Oomph 설치시 Bundle pool은  플러그인과 기능을 저장하는 장소
* 이클립스 설치시 생성된 플러그인 & 기능이 저장되어져 있다.
* 이클립스 Install New Software에서 Oomph 업데이트 & 플러그인 설치 가능하다.

### link : <http://download.eclipse.org/oomph/updates>

---

* File – other 통해 Oomph 폴더에서 생성할 모델 선택
* 개발환경을 설정해둔 프로젝트를 setup모델로 생성

![Alt text](/oomph1.png)

생성된 모델은 기본적인 파일이 생성

---
###생성된 Setup 파일
![Alt text](oomph2.png)

![Alt text](oomph3.png)

 
* JRE 버전에 따른 위치를 지정 
	*	oomph 사용자의 JRE 위치를 지정	
* Eclipse Ini : 초기의 JVM의 힙메모리 크기를 지정
* P2 저장소 : Oomph 설정파일을 설치하려는 P2저장소의 위치를 지정 
* Oomph 업데이트 사이트위치 식별하는데 도울 수 있다.
* 이클립스 소프트웨어 저장소로 이클립스에서 저장소의 자료를 호출하여 사용가능합니다.
ith Table support) and GitHub Flavored Markdown.

---
###참조 페이지
<http://codeandme.blogspot.kr/p/oomph-articles.html>
<br>

<https://wiki.eclipse.org/Eclipse_Oomph_Authoring#Using_the_Setup_Editor>
<br>

<https://www.bsi-software.com/en/scout-blog/article/oomph-changes-the-way-you-handle-multiple-eclipse-installations.html>
<br>

<https://jaxenter.de/eclipse-oomph-bringt-schwung-ins-projekt-12977>
