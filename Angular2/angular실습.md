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