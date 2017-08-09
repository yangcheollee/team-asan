## Angular2 필요한 모듈 포함하기

* 외부 함수 또는 클래스를 현재 페이지에서 사용하기 위한 절차 import구문
* 앵귤러는 모든 기능이 모듈화 되어져 있다.
* @angular/core
* @angular/http
* @angular/forms
* @angular/route

## import구문
	import {Component} from "@angular/core";

* import : import 키워드
* Component : 멤버이름, 콤마 구분으로 여러 모듈 로드
* @angular/core : 앵귤러 라이브러리 모듈이름

## 양방향 바인딩 
* [(ngModel)] 사용하기 위해서는
* import{FormsModule} from '@angular/forms'; 필요하다
* input type="text" [(ngModel)]="name"/>

## 의존성주입 DI
* @Injectable() 서비스클래스 만들 떄 사용


## Angular의 selector에 host설정
* selector: selector이름
* host : { '(click)' : 'onClick()' }
* host : { 클릭이벤트 : 클릭이벤트 후 호출할 함수 }

----
# ☆☆☆☆☆☆☆☆☆
# app.module.ts에 import해야만 새롭게 정의된 지시자들을 호출하여 사용할 수 있다.
# ☆☆☆☆☆☆☆☆☆
----

