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

### Redux-saga란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------
