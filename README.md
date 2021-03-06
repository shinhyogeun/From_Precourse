
# 프리코스의 프리
1. github에 fork하고 pullrequest 하는 법을 다시 보자!! 
	* https://wayhome25.github.io/git/2017/07/08/git-first-pull-request-story/ 를 참고하면 좋습니다.
2. JS 기본 문법 및 컨벤션을 확인해보자!
	* https://velog.io/@recordboy/자바스크립트-변수-명명-규칙 를 참고하면 좋습니다.
3. 좋은 코드란 어떻게 만드는 것
	* https://github.com/qkraudghgh/clean-code-javascript-ko 자바스크립트를 통해 클린코드를 보자.
---------------------------------

# 1주차 미션- 숫자야구게임 만들기!-
---------------------------------
### 구현할 기능 목록

* 랜덤으로 서로 다르고 0이 아닌 3자리 숫자배열 만들기
    * 랜덤으로 0과 9사이의 숫자를 만든다.
    * 0이 아닌지 확인한다.
    * 기존에 뽑은 숫자와 동일한 숫자를 뽑았는지 확인한다.

* 사용자의 입력이 올바른 입력인지 판별하기(아니라면 alert을 보여준다.)
    * 입력의 길이가 3인지 확인한다.
    * 모두 숫자인지 확인한다.
    * 서로 모두 다른 숫자인지 확인한다.
    * 0이 없는지 확인한다.

* 결과 계산하기
    * 주어진 index가 strike, ball인지 확인한다
    * 깔끔하게 스트라이크, 볼, 낫싱을 String으로 출력한다.

* 정답을 맞췄는지 확인하기

  (정답이 맞을 경우)
    * '축하합니다.'문구 HTML 추가하기.
    * 다시하기 버튼 생성하기.
    * 다시 시작하는 restart 함수 만들기
        * 입력창 비우기
        * 추가된 버튼과 HTML를 모두 원상복귀 시킨다.
        * 랜덤으로 서로 다르고 0이 아닌 3자리 숫자를 만든다.
    * 다시하기 버튼에 restart 이벤트 리스너 추가하기

  (정답이 아닐 경우)
    * 결과 출력하기

* 확인버튼에 게임을 진행할 수 있도록 이벤트리스너 추가하기

    
 ### 느끼는 점
 * 확실히 README 파일을 잘 만들어야한다. README를 디테일하게 작성 후 프로그래밍을 시작해야 탄탄하고 보기 좋게 만들 수 있다.</br> 
 * 지금은 확실히 함수들을 각각 만들어서 그것을 다같이 돌리는 거대한 하나의 함수를 만드는 느낌이다.</br> 
 * '클래스는 언제 만드는 것이 가장 좋을까'에 대한 깊은 고민도 필요하다. </br>
 * 클래스를 어디까지 나눠야할까? 얼마나 잘게 쪼게야 하는 걸까?
 * 메서드 체이닝이란 걸 쓰는게 어떨까? </br>
 * 실생활에서 보이는 많은 물건들을 class로 만들어보자!!!!!! </br>
 
 **JS의 본질은 사용자와의 상호작용이다. 그 상호작용은 입력과 내부 알고리즘 그리고 출력으로 이루어진다.**
  그래서 나는 어떤 걸 만들던지 저 3개를 유념해야 한다고 느꼈다.

 1. 입력
 * 사용자는 HTML에 입력을 할 것이다. 그것은 클릭일 수도 또는 textInput일 수도 있다.</br>
   단지 내가 집중해야하는 것은 그것을 그 다음단계인 내부 알고리즘을 위해 소중히 가져와야한다는 것이다.</br> 
   그러한 일들은 모두 각각의 함수가 생성되어 각각의 일에 집중하게 만들어야한다.</br>
</br>

 2. 내부 알고리즘
 * 여러번 쓰인다면 주저하지말고 클래스를 만들자. 다만 여기서 주의할 점은 그 클래스의 속성과 기능들이다. </br>
   <strong>각각의 함수는 하나의 일을 해야한다.</strong> (#으로 외부에서 데이터를 조작하지 못하도록 하는 것도 잊지말자)</br>
   또한 내부 알고리즘이 끝난다면 우리는 user에게 출력해줄 준비가 끝나야 한다. 출력파트에서는 오로지!!!! </br>
   사용자에게 보여주기 위해 DOM과 소통하는 JS만 있어야한다.(UI와 알고리즘의 이분화)</br>
</br>

 3. 출력
 * DOM과 소통해서 올바른 결과를 사용자에게 보여주고 재시작을 준비해야한다.</br>

#### 그렇다면 위의 3개를 만들어 놓으면 끝일까? 그렇지 않다.
#### 3개가 연결이 되어야 한다.  사용자가 입력을 끝내면 바로 내부에서 알고리즘이 돌고 출력이 되고 재시작까지 준비되어야한다.
#### 위 3개가 완성된다고 바로 이러한 프로그램이 만들어지는 것은 아니다. 이것은 큰 하나의 줄기가 필요하다.
#### 그러한 큰 흐름의 프로그램은 결국 하나의 클래스가 실행될 때 시작되는 것이다. 
#### 다른 분들 20~30명 정도 코드를 본 결과 1.2.3.을 파일을 나누어 class를 분리해서 푸신 분들 있었고 굳이 그렇게 하지 않고 index.js에서 모두 하신 분들도 있었다. 
#### 나는 후자이다. 다만 한 클래스에서 앞(내부알고리즘)과 뒤(UI)로 나누었다. 다음주 주차에서는 나누어서 만들어보자.부디 이 내용이 공통피드백에 있었으면 좋겠다..

---------------------------------

# 2주차 미션- 레이싱게임 만들기!-
---------------------------------
## 📝 구현 기능 목록

- 입력
  - 자동차 이름들
  - 시도할 횟수

- 중간 과정.
  - 자동차의 이름들이 올바른 이름인지 확인한다.
  <br>**(예외처리)**<br>
  - 1.) 자동차의 이름이 5글자보다 길 때
  - 2.) 자동차의 이름이 공백일때
  - 3.) 자동차의 이름이 다른 자동차의 이름과 같을 때

- 시도할 횟수가 정상적인 입력인지 확인한다.
  <br>**(예외처리)**<br>
  - 1.) 음수가 입력되었을 때
  - 2.) 소수(ex1.5)가 입력되었을 때
  - 3.) 아무것도 입력이 안되었을 때

- 1회의 레이스를 진행한다.

- 화면에 결과를 출력한다.

- 위의 과정 시도할 횟수만큼 반복한다.

- 1등을 찾는다.

- 최종 1등을 출력한다.

------------------------
 

## 📝 생각했던 부분

- class.. 어떻게 나눠야할까?
  <p>이 부분은 프리코스를 진행하는 분들 모두가 고민하는 부분일 것입니다. 저도 너무 많이 고민하고 찾아가며 이전에 다른 분들이 쓴 코드들을 정말 많이 찾아봤습니다. 저는 프로그램으 크게 input과 output 그리고 내부 알고리즘으로 나누고 여기서 서로 소통하는 부분(예를 들어 input의 조건이 내부알고리즘을 필요할 경우)을 위한 별도의 파일을 만들었습니다.(저의 파일에서는 inputView.js에서 input.js와 carNameCheckor.js가 같이 만나 하나의 과정을 수행합니다.) 또한 내부알고리즘에서는 자동차(car)객체를 만들어 자동차가 가져야하는 기능들을 수행할 수 있게 했습니다. 또한 자동차들(cars)라는 객체도 추가로 만들어 자동차들의 경주 1이닝을 다룰 수 있게 하고 그에대한 결과HTML생성 기능 그리고 1등찾기 및 우승자HTML생성 기능을 구현하였습니다. 또한 cars를 생성한 이유로는 일급컬렉션을 위한 의도도 있습니다. 추후 자동차의 집합을 사용하는 모든 곳에 쉽게 제약을 줄 수 있기때문입니다. 이렇게 2주차에서는 프로그램을 만들 때 이용할 객체지향 구조에 대해 깊게 생각해보았습니다. </p>
  
- class 생성 할 때 조건을 주는 것은 어떨까?
  <p>객체를 생성하면서 constructor안에서 조건을 주어 조건에 맞지 않으면 error 던지게 하여 존재하는 객체는 특정 조건 만족을 보장할 수 있게 만들 수 있습니다.예를 들면 car라는 객체를 만들 때 constructor에서 car의 이름이 만족해야하는 조건들을 넣어두고 이를 만족하지 못하면 error를 던지는 것입니다.이는 일급 컬렉션을 만들 때도 이용될 수 있지만 생각해보면 car의 이름이 5글자 이하여야 한다는 것은 이 RacingGame의 규칙이지 car의 규칙은 아니었습니다. 만약 다른 게임에서 만약 7자리 이하로 조건을 다르게 적용한다면 그 게임에서는 car class를 사용하지 못할 것 입니다. 따라서 car와 cars에 생성할 때의 조건을 주어 만드려고 했으나 이번 미션에서는 별도의 class를 만들어 이름을 검사했습니다. 그런데 반대로 만약 positive라는 객체를 만들 때 음수값이 들어오면 error를 발생시키는 것은 positive자체의 지켜져야하는 규칙이므로 이는 적절합니다. 여기서 저는 "그럼 언제 내부적으로 조건을 주는 것이 좋을까?"에 대해서 생각해 보았고 "꼭 필요하고 만족되지 않으면 프로그램에 영향을 줄 수 있는 객체의 조건이면 이렇게 객체속에 조건을 주는 것이 좋을 수 있다"고 생각했습니다.</p>
  
## 📝 노력했던 부분

- 모듈을 분리해서 체계적인 프로그램을 만드려고 노력했습니다.
  
- 하드코딩을 하지않으려고 했습니다.
  - 하드코딩을 하지 않으면 제 코드가 가독성이 떨어지는 것같습니다. 상수들을 의미있게 바꾸어 가독성을 높이려고 노력했습니다.

- 추상화 정도를 맞추려고 노력했습니다.
  - 추상화가 되어 있다면 코드보다는 영어 문장에 가까워져 코드의 가독성이 높아졌습니다. 따라서 글처럼 부드럽게 읽을 수 있게 만드려고 노력했습니다.

- 위에서 아래로 읽을 수 있게 만들어 보고자 했습니다.
  - 가장 추상적인 부분은 위에 그리고 그보다 조금은 구체적인 부분은 밑으로 위치시켜 위에서부터 아래로 읽을 수 있게 구성하려고 노력했습니다.
     
     
## 📝 참고했던 자료들
- [우아한테크세미나] 190425 TDD 리팩토링 by 자바지기 박재성님(https://www.youtube.com/watch?v=bIeqAlmNRrA&t=4062s)
- 생각하라 객체지향처럼 -우아한 형제들-(https://woowabros.github.io/study/2016/07/07/think_object_oriented.html)
- 일급 컬렉션 (First Class Collection)의 소개와 써야할 이유(https://jojoldu.tistory.com/412)

---------------------------------

# 3주차 미션- 지하철 노선도 관리 시스템 만들기!-
---------------------------------

## 📝 구현 기능 정리

### 1. 입력
- 역관리의 경우
  - 추가할 역이름
- 노선관리의 경우
  - 추가할 노선이름
  - 상행 종점
  - 하행 종점
- 구간관리의 경우
  - 수정할 노선
  - 추가할 역이름
  - 순서

### 2. 알고리즘(과정)
***localStorage에는 역관리 정보를 가지는 stationRepository와 노선관리 정보를 가지는 lineRepository가 있다.***

**1) 역관리의 경우**<br>
 ##### (추가)
  - 역이름을 입력받는다.
   <br>**(예외처리)**<br>
    - 지하철역의 이름이 1글자 이하인지 확인한다. (공백포함)
    - 이미 존재하는 지하철역의 이름을 입력하였는지 확인한다. 
  - 지하철 역 목록 마지막에 새로운 역에 대한 행을 추가한다.
  - stationRepository에 새로운 역을 추가한다.

  ##### (삭제)
   <br>**(예외처리)**<br>
    - 지하철 노선에 등록된 역인지 확인한다.
  - 표에서 삭제한다.
  - stationRepository에서 역을 삭제한다.
    
**2) 노선관리의 경우**<br>
  #### (추가)
  - 노선이름을 입력받는다.
   <br>**(예외처리)**<br>
    - 노선이름을 공백으로 입력하지 않았는지 확인한다.
    - 이미 존재하는 노선이름을 입력하지 않았는지 확인한다.
  - 상행 종점과 하행종점을 입력받는다.(순환선일 수 있기에 두 개가 같을 경우도 허락한다.)
  - 지하철 노선 목록 마지막에 새로운 노선에 대한 행을 추가한다.
  - 새로운 노선정보를 lineRepository에 추가한다.

  #### (삭제)
  - 지하철 노선 목록에서 제거한다.
  - lineRepository에서 노선정보를 삭제한다.
  
**3) 구간관리의 경우**<br>
  #### (추가)
  - 구간을 수정할 노선을 선택받는다.
  - 구간 등록할 역을 선택받는다.
  - 삽입할 순서를 입력받는다.
	<br>**(예외처리)**<br>
    - 순서가 0이상인지 확인한다.
    - 순서가 소수(ex1.2)가 아닌지 확인한다.
    - 순서가 지금 존재하는 가장 마지막 순서 + 1 보다 큰지 확인한다(ex. 순서가 3번재까지 있는 노선에서 5번째 순서에 등록하는 경우)
  - lineRepository에서 수정할 노선의 순서에 구간등록할 역을 삽입한다.
  - update된 lineRepository에서 Data를 가져와 표를 다시 보여준다.

  #### (삭제)
  - lineRepository에서 선택된 노선의 삭제할 구간 순서를 삭제한다.
  - update된 lineRepository에서 Data를 가져와 표를 다시 보여준다.

**4) 지하철 노선도 출력의 경우**<br>
  - lineRepository에서 모든 노선에 대한 정보를 가져온다.
  - 모든 노선에 대한 모든 역을 출력한다.
----------------------------------------------------------------
<TIP>

**1. Data로 저장하는 것을 객체로 만들까?**<br>
ex) stationRepository = {
                           신림역 : new Station("신림역"),
                           신도림역 : new Station("신도림역"),
                           신풍역 : new Station("신풍역")
                        }
                                 
ex) line Repository ={
                           1호선 : new Line("1호선","인천","소요산"), 
                           2호선 : new Line("2호선","신촌","신도림")
                        }
                                   
<p>그리고 저 객체 안에는 호선이 포함하는 역들의 배열이 있다.<br>
    새로운 역을 만들때 포함하는지 검사한다면 <br>
    stationRepository.hasOwnProperty(새로운 역의 이름)<br>
    새로운 호선을 만들때 포함하는지 검사한다면<br>
    lineRepository.hasOwnProperty(새로운 호선의 이름)<br>
    이렇게 만들어서 Line 객체안에서 stationArray라는 속성으로 그 호선의 역순서를 저장한다.</p>
    
**2. HTML과의 상호작용에 대한 공부가 더 필요하다.**
  - 표를 만드는 것은
	<table border="1">/
	<th>첫번째 열의 제목</th>/
	<th>두번째 열의 제목</th>
	<th>세번째 열의 제목</th>
	<tr>
	<td>첫번째 열</td>
	<td>두번째 열</td>
	<td>세번째 열</td>
	</tr>
	<tr>
	<td>첫번째 열</td>
	<td>두번째 열</td>
	<td>세번째 열</td>
	</tr>
	</table>"
                

  - 선택을 하는 것(select 태그를 이용한 것)은
    
	<select>/
        <option>1번째 선택할 것</option>/
        <option>2번째 선택할 것</option>
        <option>3번째 선택할 것</option>
        <option>4번째 선택할 것</option>
	</select>

<p> 선택된 것을 얻는 방법은 다음과 같다.<br>
    const selectOption = document.getElementById()<br>
    selectOption.options[selectOption.selectedIndex].value</p>

## 📝 3주차에 고민하고 배웠던 부분

**1. innerHTML vs appendChild** <br/>
<p>저는 이 2개중에 고민을 많이 했습니다. appendChild를 사용한다면 이벤트가 사라지지 않는다는 장점이 있었고 그대신 innerHTML을 사용하는 것보다 보고 이해하는 것이 어려웠고 코드가 복잡해지는 것 같았습니다. 그래서 저는 innerHTML을 주로 사용하기로 하고 그러는 와중에도  최대한 innerHTML은 적게 사용하려고 노력했습니다.(모두 지우고 다시 작성하는 방식이므로) 또한 복잡한 표 혹은 select 태그는 ``안에서 함수를 실행시켜 코드를 보기 좋게 하려고 노력했습니다.</p>

**2. 구조는 어떻게 할까?**<br/>
<p>3주동안 가장 저를 고민하게 만들었던 것은 구조였습니다. 3주차에 미션을 진행하며 결국 View와 controller 그리고 manager라는 3가지로 나누어 만들었고 피드백에도 있던 단일 책임을 지키기 위해 책임을 나눌 수 있었습니다. (view는 HTML관련 작업, controller는 입력값 검증 및 기타 내부적 알고리즘, 그리고 manager는 둘을 이용한 종합적인 관리를 하는 역할을 부여했습니다) 또한 이러한 구조를 1주차와 2주차 과제에 다시 대입하며 생각을 해보며 다양한 곳에 적용해보려고 노력했습니다.</p>

**3. HTML에 데이터 저장하기**<br/>
<p>HTML에 데이터를 저장하라는 추가 요구사항을 처음 봤을 때 의도를 깊게 생각해보았습니다. 물론 처음 보는 개념이기에 찾아봤었고 제가 내린 결론은 localStorage에 접근하기 위해 HTML에 데이터를 저장한다는 것이었습니다. 선택된 태그의 데이터로 localStorage에 접근해 원하는 정보를 찾아볼 수 있었습니다.</p>

**4.localStorage이용하자.**<br/>
<p>localStorage에 stationRepository와 lineRepository를 만들었고 각각을 객체로 만들었습니다. 여기서 “배열로 만들까?” 생각했지만 원하는 정보를 찾는 경우 객체가 더 깔끔했고 데이터를 출력해도 이해가 더 쉬웠기에 객체로 만들기로 결심했습니다. 또한 그 객체의 key가 태그의 데이터와 일치하게 만들어 원하는 localStorage데이터에 쉽게 접근할 수 있게 만들었습니다.</p>

**5. true / false를 리턴한다면 한줄로.**<br/>
<p>함수중에 boolean값을 리턴한다면 한줄로 끝낼 수 있게 하려고 노력했습니다. 설령 if문이 안에서 필요할 경우 그 부분을 다시 함수로 만들어 boolean을 리턴값으로 가지는 함수는 한줄로 만들었습니다.</p>

**6. 다른 분의 코드에서 감명받았던 점.**<br/>
<p>처음으로 올리신 분의 코드에서 HTML태그를 만드는 함수는 정말 인상깊었습니다. 저도 거기에서 영감받아서 document.creatElement() 후에 해야하는 여러 작업들(id,class 설정등)을 하나의 함수로 한번에 처리 할 수 있었습니다.</p>

## 📝 프리코스를 하면서 배웠던 점

**1. 절대로 잊지못할 3주**<br/>
<p>정말로 몰입했던 3주였던 것 같습니다. 3주의 프리코스동안 저는 자기주도학습을 배웠습니다. 좋은 코드를 만들기 위해 다른 분들의 코드를 보고 계속 생각하고 찾아보면서 더 좋은 코드를 위해 자기주도적으로 가장 몰입했던 기간이었습니다. 이러한 좋은 기회가 있어서 좋았습니다!!</p>

**2. 구현과 속도보다 중요한 것**<br/>
<p>프리코스에 참여하기 전에는 구현이 1순위였습니다. 그리고 2순위는 시간이 었습니다.알고리즘을 하면서도 "풀 수 있나"그리고 "얼마나 걸릴까?"가 언제나 가장 중요했습니다. 그러면서 제가 놓치고 있었던 것을 프리코스에서 깊게 느낄 수 있었습니다. "구현하더라도 이해할 수 있는 코드로 구현해야 한다."가 바로 그것입니다.</p>
	
**3. 프로그래밍 공예**<br/>
<p>클린코드라는 책에는 프로그래밍은 과학보다는 차라리 공예에 가깝다는 말이 나옵니다. 계속 수정하고 더 이쁘게 만들어나가야 하기때문입니다. 프리코스를 하기전에는 혼자서 만들거나 구현하라면 공예와는 거리가 멀었습니다. 그렇게 할 동기부여가 크지 않았기 때문입니다. 하지만 이번 프리코스에서 계속 수정하며 깔끔해지는 코드를 보면서 정말 필요한 작업이라는 것 그리고 이렇게 해야 나중에 더 복잡한 것을 만들 수 있다는 것을 몸으로 느낄 수 있었습니다. </p>

# 프리코스 그 후에
---------------------------------

## 📝 내 코드에서 마음에 안드는 부분.

<p>다른 분들의 코드를 많이 보면서 사람들이 크게 다르지 않다는 것을 느꼈고 나는 어떤 부분을 보완할 수 있을지 생각해보았다. 코딩테스트까지는 2일 뿐 혼자서 poss기도 만들고 해보았지만 떨리는 느낌은 잘 없어지지 않는다. 이제부터 내 코드를 생각해보자.</p>

- 가장 마음에 안드는 부분
 <p>"누가 읽어도 이해할 수 있을까?"가 가장 마음에 걸린다. 더 단순화 할 수 없을까? 더 깔끔하고 더 우아한 느낌이 나게는 못 만드나? 라는 생각이 계속든다.
 이 마음은 솔직히 절대 없어지지는 않겠지만 그래도 내 코드는 갈 길이 멀다. 구체적으로 적어보자.</p> 

  - 1. document.querySelector("~")를 너무 남발하는 것 같다. 
    - 그렇다고 하나의 함수를 만들어 선택하게 만드는 것은 오히려 더 복잡하게 만드는 것같다. 최대한 적게 쓰게하려고 알고리즘적으로 생각해야한다.
  - 2. HTML을 그리고 나중에 버튼에 이벤트를 추가하는 방식이 우아해보이지 않는다.
    - addEventListner를 1줄로 만들려고 노력해라.
  - 3. 상수 이름 더 더 고민해서 만들어라!! 제발
    - 정말 누가봐도 알아볼 수 있도록 만들자!! 시간 정말 많이 쏟아야 하는 부분

- 파일을 어떻게 나눌까?
 - view를 만드는 View폴더, 값들을 validation을 검증하는 그리고 일반객체를 가지는 Model폴더, 이벤트를 더하고 전반적 흐름을 관장하는 controller폴더, HTMLmaker와 text를 포함하는 components

### 수고했습니다!


 