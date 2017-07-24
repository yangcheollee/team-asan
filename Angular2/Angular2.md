##TypeScript

	=> javascript + 타입

### angular2 파일 구조화

	main.ts : 앱초기화 및 첫번쨰 컴포넌트 로딩
	app.component.ts : 페이지 헤더


### Component 구조

	index.html을 로딩하고 main.ts를 호출시킨다.
 	main.ts가 로딩이 되면 첫번쨰 컴포넌트를 호출하고 접첸 맴 부트스트래핑시켜준다.
	app.component.ts 첫번쨰 컴포넌트이면서, 헤더를 로딩시키고 파일에 포함된 컴포넌트들을 로딩시켜준다.



### @Component

화면단을 구성하는 요소

컴포넌트 장식자 컴포넌트와 관련된 설정 정보를 입력 할 수 있다.

@Component({

selector :   컴포넌트 이름을 정의한다.

template : 내부 파일에  HTML과 템플릿 문법을 이용해서 템플릿을 정의

templateUrl :  외부 파일에 HTML과 템플릿 문법을 이용해서 템플릿을 정의

### 화살표 함수

function(){ } 
 
간랸하게 사용위해
 
() => { }



### NgModule

NgModule({

	import :호출할 모듈

	providers : 주입할 서비스

	declarations : 사용할 컴포넌트

	bootstrap : 애플리케이션 컴포넌트	
})


### import { Component, OnInit, ViewChild } from '@angular/core';


	=> 현재의 ts파일내부에서 예를들어

import { Component, OnInit, ViewChild } from '@angular/core';

@Component({

  selector: 'sample-app',

  template: `

  <p name="member-name">{{ myName | uppercase | honor }}</p>

  <p name="member-name">{{ myName | uppercase | honor | geekMark }}</p>

<p name="member-name">{{ itsName | uppercase | honor | geekMark:'I' }}</p>

  `,

})

export class AppComponent implements OnInit {

  myName = 'Test';

  itsName = 'testing';

}

	=> TS파일 내부에서 사용할 class나 상속받을 class를 import에 지정시켜주고 해당파일에서 생성하고 사용하면 된다.



## main.ts
angular에서 일반적으로 이파일로부터 프로젝트가 동작되어진다.

ng --help : angular-cli에서 사용할 수 있는 ng설명을 볼 수 있다.

ng doc : ng의 문서를 열어준다.

ng build : 빌드를 통해 dist폴더를 생성해서 그곳에 빌드파일을 생성시켜준다.

	=> ng build 자세히 모르겠음 (이해가 가지않음)

ng generate : 새로운 컴포넌트 router를 만들어준다.

ng lint : 프로젝트가 ng표준에 맞게 작성됬는지 체크시켜준다.


### main.ts의 platformBrowserDynamic.bootstrapModule(AppModule)
앵귤러가 컴파일해서 JS파일을 만들어 동작시키는데 브라우저상에서 동적으로 컴파일을 시켜준다는 의미이다.

#### bootStrapModule(AppModule) 
루트모듈로 appmodule을 실행시켜준다.

#### NgModule({ }) 
클래스를 앵굴러 모듈러 설정하고 사용가능하도록 한다.

#### Module 
1. 자바스크립트에서의 모듈


	세부구현이 숨겨져 있는 공개 API 이용해 다른코드에서 재사용가능한 코드
2.  ES6에서의 모듈
	
	자바스크립트에서의 모듈 + 변수스콥이 모듈로 제한 ( 각각 파일이 모듈로 정의)

3. 앵귤러의 모듈

	컴포넌트, 파이프, 서비스 등과 같은 앵귤러 애플리케이션의 주요부분을 기능단위로 그룹핑을 하게 해준다

모든 앵귤러 애플리케이션은 하나의 Root Module을 가진다. 

여러 Feature Module을 가질 수 있다.

재사용할 수 있는 기능을 외부에 배포하기 위해 사용되기도 한다.

----

#angular 실습 

#### greeting.ts파일 생성해서 연습해보기

ng new 프로젝트 이름

기본적인 angular/cli를 이용 할 수 있는 angular파일을 생성


#### src폴더의 app폴더의 greeting.ts를 생성
클래스 파일 하나 생성

export class Greeting{

  sayHello(name: string){

    console.log("hello " + name);

  }

}



export를 붙여주는 이유는 파일을 main.ts에서 호출하여 import해서 사용 할 수 있도록 하기 위해 export를 붙여주므로써 import가 가능하다.

#### main.ts
import {Greeting} from './app/greeting';

const g = new Greeting();

g.sayHello(" Yang");


	 추가할 ts파일과 클래스의 이름 그리고 폴더의 위치를 지정해주면 ts의 파일을 import해서 사용 할 수 있다.
	자바에서 사용하는거 처럼 객체를 생성해주고 클래스에서 생성한 메서드를 호출해서 사용해주면 된다.
	콘솔창에 지정한 내용이 출력되어진다.

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170720_1.png?raw=true)

	

### 모듈생성하기
ng generate module todo

	ng generate module "모듈이름"


### todos라는 컴포넌트 생성
g : generate 약어

c : componet 약어

#### ng g c todo/todos --module todo/todo.module.ts --export 

	todo클래스 컴포넌트시켜서 사용가능


ng serve : 여러파일들을 밴들링한다.

	서버를 동작시켜준다.

### 생성한 모듈 todo폴더에 todo.module.ts생성과 todos폴더에 todos.component파일들이 생성된다.

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_1.png?raw=true)



![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_2.png?raw=true)



![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_3.png?raw=true)

### 생성한 todo모듈을 사용하려면
**app.module.ts에 import를 시켜주어야한다.**

import { TodoModule } from './todo/todo.module';

 imports: [
    BrowserModule,
    TodoModule
  ],


![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_4.png?raw=true)


### Component 컴포넌트

	@Component 함수를 호출시킨다고 생각하면 된다.
	selector : css적용하는거처럼 . , #을 이용해서 id와 class의 이름을 찾아서 적용시킬 수 있다.

#### todo 컴포넌트 생성

	ng generate component todo/todos/todo –inline-template –inline-style

#### todo.moudle.ts  생성한 todo.component 추가
![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_7.png?raw=true)


##### todos.component.html 수정


![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_5.png?raw=true)
##### todo.component.ts template 수정 멀티 바인딩

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_6.png?raw=true)


---
### 컴포넌트 로직을 template으로 어떻게 표현을 하는지
Angular Template 

HTML 코드로서 템플릿을 표현, Template 표현식 Expression과 Template 문장statement 가진다.

바인딩 : 데이터와 로직을 담고있는 컴포넌트 브라우저 뷰와의 커뮤니케이션이라고 생각하면 된다.

 바인딩 대상 - 속성, 이벤트, ngModel, class, style


### 바인딩

**component(클래스) DOM(브라우저단) 단방향 & 양방향**

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_8.png?raw=true)


### imput 박스의 체크박스속성 부여하기
 **todos.component.html**
	

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_9.png?raw=true)


### 체크박스속성 부여한 것을 ngFor함수로 이용하기

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_10.png?raw=true)

---
### 클릭이벤트를 부여하고 실시간으로 변동하기

#### todos.component.html

 
toggleTodo버튼 만들기

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_11.png?raw=true)

---

#### todos.component.ts

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_12.png?raw=true)

### 실행화면
![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_13.png?raw=true)


### 할일추가 input박스에 데이터 입력시 실시간으로 바인딩

	입력한 데이터를 출력시켜준다.

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_18.png?raw=true)


	todos.component.html에 newText 변수생성

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_15.png?raw=true)


	todos.component.ts에 newText 설정지정

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_16.png?raw=true)


### input 박스 값을 실시간으로 바인딩하기 위해서는 모듈을 추가 시켜주어야한다.

	todo.component.ts에 모듈추가 FormsModule
![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_17.png?raw=true)

### input박스에 입력한 값을 버튼으로 추가하기
	todos.component.html에 button클릭 생성

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_20.png?raw=true)


### addTodo 함수 생성하기
	todos.component.ts에 addTodo생성하기

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_21.png?raw=true)

### 식사하기 체크박스 추가하기
![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_22.png?raw=true)

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_19.png?raw=true)

**실시간으로 메뉴를 추가시켜줄 수 있다. 데이터베이스를 활용한 것이 아니기 때문에 현재 웹을 새로고침하면 조금전에 생성한 메뉴는 다시 사라진다.**


----
### 컴포넌트 커뮤니케이션

	모델 생성
	ng g class todo/todos/share/todo.model
	app폴더에 todo폴더안에todos폴더안에 share폴더에 todo.model생성

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/96e102039c49cce561bea53f01960b1d59acefbd/img/170721_23.png)

### 생성된 모델에 Todo에 done, text 객체설정
![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/96e102039c49cce561bea53f01960b1d59acefbd/img/170721_24.png)

### todos.component.ts에서  todo모듈 지정
![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/96e102039c49cce561bea53f01960b1d59acefbd/img/170721_27.png)

	Todo모듈을 todo aias로 지정해준다.



### todo.component.ts todo모듈지정
![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/96e102039c49cce561bea53f01960b1d59acefbd/img/170721_25.png)

	export된 클래스 모듈todo를 다른 component에서 사용하기위해서는 @Input를 사용하여 Input되도록 해주어야한다. 
	todos.component.html에서 app-todo에서 todo를 호출하기 위해서는 @Input가 필요하다.


### todos.component.html에서 todo모듈 객체 호출
![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/96e102039c49cce561bea53f01960b1d59acefbd/img/170721_26.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/bb77779e0d23f039f0870bb135ae397ebd0c5696/img/170721_22.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/20d7c6f473d77e30b69e8e22456b437150c751ec/img/170727_19.png)

	todo모듈을 사용하기전과 같이 똑같이 실행되어진다.

---
### add-todo 모델생성
![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_28.png?raw=true)

**ng generate component todo/todos/add-todo –inline-template –inline-style**

----
### add-todo.component.ts template에 todos.component.html에 있는 클릭버튼을 옮긴다.
### @Output onTodoAdded 생성 , addTodo 메서드 생성, 
### EventEmitter 이벤트 버튼 , add클릭시 버튼동작

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_29.png?raw=true)


### todos.component.html에서

![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_30.png?raw=true)

### <app-add-todo (onTodoAdded)="addTodo($event)"></app-add-todo> 생성



### todos.component.ts에서 TodosComponent클래스에  addTodo이벤트 메서드 생성


![결과](https://github.com/yangcheollee/team-asan/blob/master/img/170721/170721_31.png?raw=true)
