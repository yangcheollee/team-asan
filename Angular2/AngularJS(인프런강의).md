#AngularJS (인프런강의)

## 브라우저 , 서버 관계
브라우저 : 서벌 url요청
서버 : html, css js 응답

* 사용자가 버튼 클릭

브라우저 : 새로운 리퀘스트
서버 : json,xml을 브라우저에 전달

* 앵귤러 공식사이트
<https://docs.angularjs.org/guide/concepts>

### Directives
* 확장된 html

### expressions
* js의 내용을 html에 출력해주고 싶을 때 이용한다.

### module
* 다른모듈을 주입해서 사용가능

### controller 
* view의 비지니스로직을 구현하는데에만 사용한다.

### service
* 비지니스로직
* 재사용할 수 잇는 비지니스로직
* 싱글톤 구현, 어플리케이션 데이터를 관리하는데에 이용된다.


### 개발환경
pluker


### ng-app , ng-init
* ng-app : ng-app이 선언된 부분부터 앵귤러를 적용하겠다.
* ng-init : 자바 함수와 변수를 초기화하는데에 사용한다.   <body ng-app ng-init="name = 'Chris'">
* 표현식 : {{name}}


### 모듈과 컨트롤러
* script.js
(function (){

  var app = angular.module('todo',[]);

})();

	angular.module이란 script단에 angular를 추가해주었기 때문에 사용가능
	app이라는 변수에 todo라는 모듈이 배열형태로 할

* index.html
* <body ng-app="todo" ng-init="name = 'Chris'">
	script에 선언된 todo모듈이 ng-app에 선언되어졌다. todo모듈을 사용할 수 있다.

* 모듈의 controller
* script.js
   
app.controller('TodoCtrl',['$scope',function($scope){

  $scope.name = "Chris";  

  }]);
		
 	$scope 역할
	컨트롤로와 html파일간의 연결고리 역할
* ng-init 대신 ng-cotroller사용

* <body ng-app="todo" ng-controller="TodoCtrl">
* controller에서 설정한 컨트롤로명을 적어주어야한다. "TodoCtrl"

### ng-model , 양방향 바인딩
값을 바인딩해주어서 해당값을 출력시켜주면서 해당값이 변경되었을때 바로바로 반영해준다.

### ngRepeat
* for문처럼 반복해서사용할 수 있다.
* <div ng-repeat="todo in todos">
* 객체를 반복해서 출력시켜준다.


### ngFilter 
* 해당 데이터의 형식을 원하는 포맷형태로 지정해서 출력할 수 있다.
* <date>{{todo.createdAt | date: 'yyyy-MM-dd HH:ss'}}</date>
* 표현이 가능하다.


### ngClick 핸들
*  클릭이벤트를 지정해준다.
*  <button class="btn btn-danger" type="button" ng-click="remove(todo)">삭제!</button>

### 필터 버튼

* <li ng-repeat="todo in todos | filter:statusFilter">
	* filter를 지정가능
* <button class="btn btn-primary" ng-click="statusFilter={completed:true}">Completed</button> 
* <button class="btn btn-primary" ng-click="statusFilter={completed:false}">Active</button>  
* <button class="btn btn-primary" ng-click="statusFilter={}">All</button>    
 


## Form 검증

### ng-show
* angular에서 해당 요소에 대한 표현식을 기반으로 HTML의 요소를 표시하거나 숨기는 역할을 한다.

    <div ng-show="todoForm.$dirty && todoForm.$invalid">

    < div class="alert alert-warning" role="alert">3글자 이상 입력하세요.< /div>
    < /div>


* input box에 스타일주기
	* .ng-valid.ng-dirty 클래스이름은 input-box에 글자가 입력한 값이 valid한 경우에 클래스이름을 사용한다.



* 다른 공간말고 input부분에만 css적용시키기
	* .input-group .ng-valid.ng-dirty{
  border: solid 1px green;
}
	* .input-group .ng-invalid.ng-dirty{
  border: solid 1px red;
}


----


### 디렉티브
* 스크립트에서 지정해서 html에 호출시켜준다. 
* html단에서 <toodo-title></todo-title>을 지정

app.directive('todoTitle',function(){

  return {
    
template : 'h1>투두 목록 </h1>'

  }

* angular에서는 html에서 todo-title로 지정한 태그명을
* js에서는 todoTitle 대문자로 해주는것이 일반적인 방식이다.


### todoItem
* ng-repeat로 호출한 자료를 디렉티브로 호출


### angular.module('todo').directive
* angulalr.module에서 directive사용할 수 있도록 해준다.

### todoFilters
angular.module('todo').directive('todoFilters',function(){

  return {
    
templateUrl : 'todoFilter.tpl.html'
  }

});

### todoForm
* form태그를 디렉티브 별로 분리하여 코드를 간편화 시킬 수 있다.

