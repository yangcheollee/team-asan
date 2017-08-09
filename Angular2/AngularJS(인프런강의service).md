# Service, factory

* service를 통
* 데이터 관리방식을 분리시켜준다.
* service , factory , provider
* 3가지의 정의방식이 있다.

### todoStorage : get()
* angular.module('todo').factory('todoStorage',function(){
	* factory('서비스이름', 함수)

#### factory방식으로 모듈정의
angular.module('todo').factory('todoStorage',function(){
  
var storage = {

   todos: [

   {
   
   title: 'sample',
   
   completed: false,
   
   createdAt: Date.now()
   
 },
   
{
   
   title: 'test',
   
   completed: false,
   
   createdAt: Date.now()
      },
   
  {
   
   title: 'home',
   
   completed: true,
   
   createdAt: Date.now()
   
 }
   
 ],
    
 get: function(){
   
return storage.todos;
   
 }
  
} 
 return storage;

});

#### todoStorage : remove(), add()
* 디렉티브로 나눠서 함수를 호출


#### 지금까지 실습에서 이해한 angular 동작 흐름
* 1. form에서 버튼클릭시 ng-submit="add()" 동작
* 2. controller.js에서 add함수로 전달
* 3. add의 함수에서 todoStorage.add() 함수 호출
* 4. service.js로 add함수 전달
* 5. 실제로 input box에 입력한 값을 화면에 추가시켜준다.


#### todoStorage : localStorage
* 브라우저를 새로고침하면 데이터가 남아 있지않기 때문에
* 자체적으로 저장가능한l localStorage이용
* 하드디스크에 저장시켜보기, 파일저장, 디비에 저장
* 크롬에서 localStorage라고 제공

	localStorage :
	* Key, Value 저장소
	* localStorage.setItem(key, value)
	* localStorage.getItem(key) //value,localStorage[key] 접근가능
	* 입력은 무조건 string으로 처리됨
	* 최대 약 5mb용량
	* 크롬은 SQLite 사용함
	

-----
	* localStorage.length
	* localStorage.key(value) //key
	* 영구보관
	* sessionStorage는 새탭, 새 윈도우로 범위가 제한된다는 점이 localStorage와 차이점
	* 참고 : <http://ohgyun.com/417>



### todoStorage : update()


#### ng-blur : 포인트가 벗어나면 blur 이벤트 가능