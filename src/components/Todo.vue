<template>
<div>
  <h2>代办管理</h2>
  <TodoAdd getAllTodo="getAllTodo"></TodoAdd><br>
  <TodoQuery></TodoQuery><br>
  <TodoList></TodoList>
</div>

</template>

<script>
import TodoAdd from "./TodoAdd";
import TodoList from "./TodoList";
import TodoQuery from "./TodoQuery";
import axios from "axios";
export default {
  name: "Todo",
  components: {TodoAdd,TodoList,TodoQuery},
  // data(){
  //   return {
  //     todos:[]
  //   }
  // },
  mounted(){
    console.log('加载完毕。。。开始获取数据')
    this.getAllTodo();
  },
  methods:{
    add(){

    },
    remove(){

    },
    update(){

    },
    query(){

    },
    //获取所有代办信息
    getAllTodo(){
      axios.get("http://127.0.0.1:8080/todos").then(
          response => {
            const data = response.data;
            // const flag = data.flag;
            this.$bus.$emit("getTodos",data.data)
          },
          error => {
            console.log(error.message)
          }
      )
    }
  }
}
</script>

<style scoped>

</style>