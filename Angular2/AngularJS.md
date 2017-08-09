## AngularJS

###Scope
* 컨트롤러나 디렉티브의 유효범위내의 저장공간 
*  뷰는 scope를 통해 컨트롤러 내부에 정의된 모델(데이터)이나 핸들러 함수에 접근가능
*  뷰에서는 해당 컨트롤러의 scope에서 모델과 핸들러 함수를 찾게 된다.

### html 태그에 ng관련 변수를 지정
 ' script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
* angularjs를 사용하기 위해서는 script에 추가를 해주어야지 기능을 사용할 수있다.

<div ng-app="">

  <p>Name: input type="text" ng-model="name"></p>

  <p ng-bind="name"></p>

</div>

* ng-model="name" 
* 해당 input text에 값을 입력하면 필드값이 저장(?)
* ng-bind="name" 을 통해서 웹페이지에 실시간으로 데이터가 바인딩되어진다.

* input type="number" : 숫자만 입력가능
* ng-repeat : HTML요소를 복제

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