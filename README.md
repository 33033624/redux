# 关于redux的基本用法
##首先 npm install redux
//引入redux 
const redux = require('redux'); 

//将redux的createStore的方法独立出来

const createStore = redux.createStore;

//创建一个对象

const initState = {

 state:[]

}

//下面是创建一个函数
function getUser(state,action){

   state = state || initState;
   
  //initState就是不传递参数的时候我们的默认值，执行过一次之后就默认会存在state这个状态了，以后就不会走initState
  switch(action.type){
  
     case 1;
     
      return {state:[1,2,3]};
      
      break;
      
      default:
      
      return initState;
   
   }

}
//将我们上面创建的函数放置到仓库中

var store = createStore(getUser);

//下面是redux提供的属性组件 当我们执行完store.dispatch(all())这个方法之后执行这个方法

store.subscribe(function(){

   const currentState = store.getState();
   
   currentState.state.push(4,5,6);

})

function all(){

   return {
    type:1
   }
}

``store.dispatch(all())``//all其实就是一个action，只是这个时候才进行传递

//现在只要我们执行

``store.getState()``//这个方法就会将所有的状态全部都显示出来

//如果想显示state可以使用 

``store.getState().state``
