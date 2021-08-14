# 예전 코드

```jsx

 class Profile extends React.Component {
   constructor(){
     super();
     this.state = { name : 'Kim', age : 30 }
   }

   changeName = () => {
     this.setState( {name : 'Park'} )
   }

   render(){
     return (
       <div>
         <h3> 저는 { this.state.name } 입니다 </h3>
         <button onClick={ this.changeName }> 버튼 </button>
      </div>
     )
   }
 }
```



