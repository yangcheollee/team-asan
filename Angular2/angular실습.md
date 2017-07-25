# Angular2 실습
	폴더를 생성하고 angular-cli설치
	npm install @angular/cli 

### ng new '프로젝트 이름'  생성

	npm install npm 환경설치
	ng new s-app 생성
----
----
## 모듈 사용하기

### 모듈 사용을 위한 todo 모듈 생성
	ng generate module todo
![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_3.png)


### todo 컴포넌트 생성

	g : generate 약어
	c : componet 약어
	ng g c todo/todos --module todo/todo.module.ts --export

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_2.png)
	
### app.component.html 에서 <app-todos> 셀렉터 호출
	
	<app-todos></app-todos>
![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_5.png)

### TodoModule정의되어있지않다고 오류발생
### 오류수정 app.module.ts에 TodoModule 정의
	import { TodoModule } from './todo/todo.module';
 	 imports: [
    BrowserModule,
    TodoModule
 	 ],

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_6.png)

### TodoModule를 import하게되면
	todos.component.html에 정의된 내용이 출력
![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_7.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_8.png)

### 사용하고 싶은 컴포넌트의 모듈을 app.module.ts에 import를 해주어야 사용할 컴포넌트에 정의된 selector의 내용을 호출해서 컴포넌트에 출력할 수 있다.
----
----
### 컴포넌트
	todos.component.html 정적이게 설정

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_10.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_9.png)


### todo 컴포넌트 생성
	ng generate component todo/todos/todo –inline-template –inline-style



### todo.component.ts input text를 호출
import { Component, OnInit } from '@angular/core';


@Component({
  selector: 'app-todo',
  template: `

   <'input type="checkbox">운동하기

  `,
  styles: []
})
export class TodoComponent implements OnInit {
  
  constructor() { }

  ngOnInit() {
  }

}

	컴포넌트안에서 또 다른 컴포넌트를 사용


### 템플릿 작성하기 template

	todos.component.ts에 쓸 데이터 생성

  todos: {
    done: boolean,
    text: string
  }[];

  constructor() { 

   this.todos =[

   {done: false, text: '운동하기'},

   {done: true, text: '공부하기'}

   ];
  }


### todos.component.html의 input에 checked속성 부여하기

 <input type="checkbox" [checked]="todos[0].done">{{todos[0].text}}

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_11.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_12.png)


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_13.png)


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_14.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_15.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_16.png)
### input *ngFor사용해서 배열 반복하기

<div *ngFor="let todo of todos">
 <input type="checkbox" [checked]="todo.done">{{todo.text}}
</div>



![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_17.png)



### checkbox 실시간 변화주기
	todos.component.html 클릭이벤트 추가
	<div *ngFor=" let todo of todos" (click)="toggleTodo(todo)">

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_18.png)


#### todos.component.ts에 toggleTodo메서드 추가
  toggleTodo(todo){
    todo.done = !todo.done
  }

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_19.png)


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_20.png)


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_21.png)


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_22.png)


### newText 속성추가하기
	todos.component.html에 ngModel속성추가하기
<input type="text" placeholder="할 일 추가" [(ngModel)]="newText">

todos.component.ts에 newText속성생성

  newText='';

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_26.png)
### todo.module.ts에 FormModule추가해줘야한다.
	ngModel은 FormsModule에있다.
	@NgModule을 사용하기 위해서는 FormsModule을 추가해주어야한다.
	import { FormsModule } from '@angular/forms';



![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_23.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_25.png)


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_27.png)


### 텍스트추가하는 버튼 생성 addTodo

**todos.component.html에 버튼추가**

<button (click)="addTodo(newText)">추가하기</button>


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_30.png)

 **todos.component.ts에 addTodo메서드 생성**

  addTodo(newText: string){

   this.todos.push({

   done: false,
   text: newText

   });

   this.newText='';

  }


![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_28.png)

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/455e0219533ef5cc029b72cc87bfcbbce00841a8/img/170724/Screenshot_29.png)



### 컴포넌트 커뮤니케이션

	1. 부모컴포넌트  -> 자식컴포넌트
	@Input()사용가능 , ES6 사용가능

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_1.png)

	2. 자식컴포넌트 -> 부모컴포넌트
	@Output() 사용
	EventEmitter를 사용 부모에게 이벤트 전달
	부모컴포넌트는 $event로 이벤트의 데이터를 전달받음
	자식이 부모 컴포넌트를 직접 주입받을 수 있다.

![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_2.png)

### 자식컴포넌트 -> 부모컴포넌트 실습
* todos.component.ts 의 input을
 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_3.png)

* todo.component.ts template로 이동

 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_5.png)



하나의 모델을 만들어서 다른 클래스에서 호출해서 사용가능
사용할 모델생성

	ng g class todo/share/todo.model

todo.model.ts에 객체 생성
export class Todo {

done: boolean;

text: string;

}

 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_6.png)


 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_7.png)

#### 생성한 Todo모델을 호출
* todo.component.ts에  Todo호출

 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_8.png)

* todos.component.ts에 Todo호출
* 
 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_9.png)


### <app-todo>를 셀렉터 호출
* todos.component.html에서 <app-todo>호출

 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_10.png)


* <app-todo>는 todo.component.ts에 지정한 셀렉터 
* Todo객체를 <app-todo>에 전달해주어야한다.
* 이 떄 사용하는 것이 @Input 이용


 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_11.png)


#### todos.component.html에서 바인딩 할떄는
*  <app-todo [todo]="todo"></app-todo>

 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_12.png)

---
----


## 자식컴포넌트 -> 부모컴포넌트 바인딩 @Output이용

### add-todo 컴포넌트 생성
* ng generate component todo/todos/add-todo –-inline-style –-inline-template 

### todos.component.html의 할일추가와 버튼을 add-todo.component.ts에 생성
* todos.component.html
 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_13.png)

* add-todo.component.ts
 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_14.png)


### todos.component.ts의 addTodo메서드를 add-todo.component.ts에 이동

* todos.component.ts
 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_16.png)


* add-todo.component.ts
* addTodo메서드 생성 
* @Output을 이용한 onTodoAdded호출

 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/aa4f1fdeebb092b834f2ef163478d4dae599ed2d/img/170725/Screenshot_20.png)

### 이벤트 객체 호출
* todos.component.html에 
 ![결과](https://raw.githubusercontent.com/yangcheollee/team-asan/9aa6a8dce390795100fa8cc33f7a6c23b218afaf/img/170725/Screenshot_21.png)


### add-todo.component.ts 설정파일

import { Component, OnInit, Output, EventEmitter  } from '@angular/core';

@Component({

  selector: 'app-add-todo',

  template: `

   <button (click)="addTodo(newText)">+</button>

   <input type="text" placeholder="할일추가" [(ngModel)]="newText">

  {{newText}}
  `,

  styles: []

})

export class AddTodoComponent implements OnInit {

  @Output() onTodoAdded = new EventEmitter();

  newText: string;

  constructor() { }

  ngOnInit() {

  }

  addTodo(newText: string){

   this.onTodoAdded.emit(newText);

   this.newText = '';
  }

}


