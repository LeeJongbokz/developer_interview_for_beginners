# Redux 면접 기출
<br>

https://xiubindev.tistory.com/119


### Context API란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### Redux를 사용하는 이유는 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.414] 

+ 리덕스는 가장 많이 사용하는 리액트 상태 관리 라이브러리입니다. <br> 
  리덕스를 사용하면 컴포넌트의 상태 업데이트 관련 로직을 다른 파일로 분리시켜서 더욱 효율적으로 관리할 수 있습니다. <br> 
  또한, 컴포넌트끼리 똑같은 상태를 공유해야 할 때도 여러 컴포넌트를 거치지 않고 손쉽게 상태 값을 전달하거나 업데이트할 수 있습니다. <br>
  
  리덕스 라이브러리는 전역 상태를 관리할 때 굉장히 효과적입니다. <br> 
  물론 리덕스를 사용하는 것이 유일한 해결책은 아닙니다. <br> 
  이전에 배운 Context API를 통해서도 똑같은 작업을 할 수 있습니다. <br> 
  리액트 v16.3이 릴리즈되면서 Context API가 개선되기 전에는 사용 방식이 매우 불편했기 때문에 <br> 
  주로 리덕스를 사용해 전역 상태 관리를 해왔습니다. <br> 
   
  단순히 전역 상태 관리만 한다면 Context API를 사용하는 것만으로도 충분합니다. <br> 
  하지만 리덕스를 사용하면 상태를 더욱 체계적으로 관리할 수 있기 때문에, 프로젝트의 규모가 클 경우에는 <br>
  리덕스를 사용하는 편이 좋습니다. <br> 
  코드의 유지 보수성도 높여 주고, 작업 효율도 극대화해주기 때문입니다. <br> 
  추가로 아주 편리한 개발자 도구도 지원하며, 미들웨어라는 기능을 제공하여 <br> 
  비동기 작업을 훨씬 효율적으로 관리할 수 있게 해주기도 합니다. <br> 
  
</details>


-----------------------

### Redux의 액션이란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.415] 

+ 상태에 어떤 변화가 필요하면 액션(action)이란 것이 발생합니다. <br> 
  이는 하나의 객체로 표현됩니다. <br> 
  액션 객체는 다음과 같은 형식으로 이루어져 있습니다. <br> 
   
  ```
  {
    type: 'TOGGLE_VALUE' 
  }
  ``` 
  액션 객체는 type 필드를 반드시 가지고 있어야 합니다. <br> 
  이 값을 액션의 이름이라고 생각하면 됩니다. <br> 
  그리고 그 외의 값들은 나중에 상태 업데이트를 할 때 참고해야 할 값이며, <br>
  작성자 마음대로 넣을 수 있습니다. <br> 
   
  예시 액션을 한 번 살펴볼까요?
  ```
  {
    type: 'ADD_TODO',
    data: {
      id: 1,
      text: '리덕스 배우기' 
    }
  }
   
  {
    type: 'CHANGE_INPUT',
    text: '안녕하세요'
  }
   
  ``` 
</details>


-----------------------

### Redux의 액션 생성 함수란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.415] 

+ 액션 생성 함수(action creator)는 액션 객체를 만들어 주는 함수입니다. <br> 
  ```
   function addTodo(data){
    return {
     type: 'ADD_TODO',
     data
   };
   
   const changeInput = text => ({
     type: 'CHANGE_INPUT',
     text
   });
  ``` 
  어떤 변화를 일으켜야 할 때마다 액션 객체를 만들어야 하는데 매번 액션 객체를 직접 작성하기 번거로울 수 있고, <br>
  만드는 과정에서 실수로 정보를 놓칠 수도 있습니다. <br> 
  이러한 일을 방지하기 위해 이를 함수로 만들어서 관리합니다. 
</details>


-----------------------

### Redux의 리듀서란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.416] 

+ 리듀서(reducer)는 변화를 일으키는 함수입니다. <br> 
  액션을 만들어서 발생시키면 리듀서가 현재 상태와 전달받은 액션 객체를 파라미터로 받아 옵니다. <br> 
  그리고 두 값을 참고하여 새로운 상태를 만들어서 반환해줍니다. <br> 
   
  리듀서 코드는 다음과 같은 형태로 이루어져 있습니다. <br> 
  
  ```
  const initialState = {
     counter: 1
  }
  
   function reducer(state = initialState, action){
      switch(action.type){
         case INCREMENT:
           return {
              counter: state.counter + 1;
           }
         default:
           return state;
      }
   }
   
</details>


-----------------------

### Redux의 스토어란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.416] 

+ 프로젝트에 리덕스를 적용하기 위해 스토어(store)를 만듭니다. <br>
  한 개의 프로젝트는 단 하나의 스토어만 가질 수 있습니다. <br> 
  스토어 안에는 현재 애플리케이션 상태와 리듀서가 들어가 있으며, <br> 
  그 외에도 몇 가지 중요한 내장 함수를 지닙니다. <br> 
   
</details>

-----------------------

### Redux의 디스 패치란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.417] 

+ 디스패치(dispatch)는 스토어의 내장 함수 중 하나입니다. <br> 
  디스패치는 '액션을 발생시키는 것'이라고 이해하면 됩니다. <br> 
  이 함수는 dispatch(action)과 같은 형태로 액션 객체를 파라미터로 넣어서 호출합니다. <br> 
  
  이 함수가 호출되면 스토어는 리듀서 함수를 실행시켜서 새로운 상태로 만들어줍니다. <br> 
   
</details>

-----------------------

### Redux의 구독이란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.417] 

+ 구독(subscribe)도 스토어의 내장 함수 중 하나입니다. <br> 
  subscribe 함수 안에 리스너 함수를 파라미터로 넣어서 호출해 주면, <br> 
  이 리스너 함수가 액션이 디스패치되어 상태가 업데이트될때마다 호출됩니다. <br>
  
  ```
  const listener = () => {
    console.log('상태가 업데이트됨');
  }
   
  const unsubscribe = store.subscribe(listener);
  
  unsubscribe();
   
  ```
</details>

-----------------------



### Redux의 장단점은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### Context API vs Redux?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### Redux-Thunk란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.482]
   
+ redux-thunk는 리덕스를 사용하는 프로젝트에서 비동기 작업을 처리할 때, 가장 기본적으로 사용하는 미들웨어입니다. <br>
  리덕스의 창시자인 댄 아브라모프(Dan Abramov)가 만들었으며, 리덕스 공식 매뉴얼에서도 이 미들웨어를 사용하여 <br>
  비동기 작업을 다루는 예시를 보여줍니다. <br>
   
  Thunk란 특정 작업을 나중에 할 수 있또록 미루기 위해 함수 형태로 감싼 것을 의미합니다. <br>
  
  ```
  const addOne = x => x + 1;
  addOne(1);
  ```
   
  이 코드를 실행하면 addOne을 호출했을 때 바로 1+1이 연산됩니다. 그런데 이 연산 작업을 나중에 하도록 미루고 싶다면 <br>
  어떻게 해야 할까요? <br> 
  
  ```
  const addOne = x => x + 1;
  function addOneThunk (x) {
     const thunk = () => addOne(x);
     return thunk;
  }
   
  const fn = addOneThunk(1);
  setTimeout(() => {
      const value = fn();
      console.log(value); 
  }, 1000); 
  ```
   
  - 이렇게 하면 특정 작업을 나중에 하도록 미룰 수 있습니다
    만약 addOneThunk를 화살표 함수로만 사용한다면 다음과 같이 구현할 수 있습니다. <br> 
 ```
 const addOne = x => x + 1;
 const addOneThunk = x => () => addOne(x);
 
 const fn = addOneThunk(1);
 setTimeout(() => {
    const value = fn(); 
    console.log(value);
 }, 1000);
  
 redux-thunk 라이브러리를 사용하면 thunk 함수를 만들어서 디스패치할 수 있습니다. <br> 
 그러면 리덕스 미들웨어가 그 함수를 전달받아 store의 dispatch와 getState를 파라미터로 넣어서 호출해줍니다. <br> 
 다음은 redux-thunk에서 사용할 수 있는 예시 thunk 함수입니다. <br> 
 ```
  const sampleThunk = () => (dispatch, getState) => {
     // 현재 상태를 참조할 수 있고,
     // 새 액션을 디스패치할 수도 있습니다. 
  }
 ```
</details>


-----------------------

### Redux-saga란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 리액트를 다루는 기술 p.502]
+ Redux-saga는 redux-thunk 다음으로 많이 사용하는 비동기 작업 관련 미들웨어입니다. <br> 
  
  redux-thunk는 함수 형태의 액션을 디스패치하여 미들웨어에서 해당 함수에 스토어의 dispatch와 <br>
  getState를 파라미터로 넣어서 사용하는 원리입니다. <br> 
  
  그래서 구현한 thunk 함수 내부에서 원하는 API 요청도 하고, 다른 액션을 디스패치하거나 현재 상태를 조회하기도 했습니다. <br> 
  대부분의 경우에는 이전 절에서 배운 redux-thunk로도 충분히 기능을 구현할 수 있습니다. <br> 
  
  이번에 배울 redux-saga는 좀 더 까다로운 상황에서 유용합니다. 예를 들어 다음과 같은 상황에서 redux-saga를 사용하는 것이 유리합니다. <br> 
  (1) 기존 요청을 취소 처리해야 할 때(불필요한 중복 요청 방지) <br>
  (2) 특정 액션이 발생했을 때, 다른 액션을 발생시키거나, API 요청 등 리덕스와 관계없는 코드를 실행할 때, <br>
  (3) 웹소켓을 사용할 때 <br>
  (4) API 요청 <br>
</details>


-----------------------
