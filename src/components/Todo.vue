<template>
<div>
  <h2>代办管理</h2>
  <TodoAdd></TodoAdd><br>
  <TodoQuery></TodoQuery><br>
  <TodoList></TodoList>
</div>

</template>

<script>
import TodoAdd from "./TodoAdd";
import TodoList from "./TodoList";
import TodoQuery from "./TodoQuery";
export default {
  name: "Todo",
  components: {TodoAdd,TodoList,TodoQuery},
  data(){
    return {
      name:'ssss'
    }
  },
  mounted(){

    console.log('mounted')
  },
  methods:{
    add(){

    },
    remove(){

    },
    update(){

    },
    query(){

    }
  }
}
</script>

<style scoped>

</style>