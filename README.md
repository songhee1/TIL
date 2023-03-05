# redux-study

리덕스 동작방법

- 하나의 중앙 저장소(store)만을 가진다.전체 애플리케이션 상태를 저장하며, 우리 컴포넌트 안에서 그걸 사용할 수 있다.
- 컴포넌트에서 상태 변경을 인지하면 ui를 업데이트하게 된다. 저장소가 컴포넌트에 알려주는 구독기능을 사용한다.
- 저장된 데이터 변경 방법: 컴포넌트가 직접 조작하지 않으며, 리듀서 함수를 이용한다.

리듀서 함수
저장소 데이터 변경하며, useReducer hook과 다른 개념이다. 입력을 변환해 새로운 출력 결과를 나타낸다.

- 저장소 데이터의 업데이트 담당
- 데이터 변경할때마다 컴포넌트 렌더링이 트리거 되는데, 컴포넌트가 원하는 액션을 dispatch하면 그 액션을 리듀서 함수에 전달되어 action 수행
- 원하는 액션을 수행해 새로운 상태 뱉어내고 저장소에 저장되어 ui가 업데이트 된다.

[노드 JS 이용해 리덕스 실행시]
초기세팅:npm init > npm i redux
실행방법:node 파일이름.js

const redux=require('redux')
: 서드파티 패키지를 임포트하기 위한 기본 노드 js 임포트 구분 이용

1. 저장소 생성
   const store=redux.createStore()

2. 저장소 관리 = 리듀서 함수 생성
   const counterReducer=(state:{counter:0}, action)=>{
   return {
   counter:state.counter+1
   }
   }
   : 매개변수 두 가지, 첫 번째는 state, 두 번째는 발송된 액션
   출력은 항상 새로운 상태 객체 리턴을 해야한다.
   리턴값은 대부분 객체인 경우가 많다. \*저장소가 처음 생성될때, 리듀서 함수를 실행시켜 state 초기화시키기에 default값 필수

3. 저장소 구독할 주체 작성
   const counterSubscriber=()=>{
   console.log(store.getState())
   };
   store.subscribe(counterSubscriber)
   : 상태가 변경될 때마다 트리거되는 함수로 최신 상태를 받을 수 있다.
   여기서는 단지 counterSubscriber 함수를 가리킬 뿐이다.

4. action 발송할 주체 작성
   store.dispatch({type:'increment'})
   : 액션 발송하며, type의 문자열에 따라 리듀서의 다양한 동작 실행 가능

(참고)
리듀서 중 if문으로 type 구분안하는 경우는 디폴트 리턴값으로 현재 상태를 리턴해주면 된다.
return state;
