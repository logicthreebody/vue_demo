<template>
<div>
  <input v-model="todo_name"><input v-model="description"><button @click="add">新增</button>
</div>
</template>

<script>
import axios from "axios";

export default {
  name: "TodoAdd",
  data(){
    return {todo_name:"",description:""}
  },
  props:['getAllTodo'],
  methods:{
    add(){
      axios.post("http://127.0.0.1:8080/todos",
          {todo_name:this.todo_name,description:this.description},
        {headers: {'Content-Type': 'multipart/form-data'}}).then(
          response => {
            response.data.flag
            console.log('保存成功')
            this.getAllTodo();
          },
          error =>{
            console.log(error.message)
          }
      )
    },
  }

}
</script>

<style scoped>

</style>