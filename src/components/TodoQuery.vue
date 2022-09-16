<template>
  <div>
    <input /><button @click="query">查询</button>
    <ol>
      <li v-for="todo in todos" index="todo.id">
        {{todo.name}}------{{todo.description}}
      </li>
    </ol>
  </div>
</template>

<script>
import axios from "axios"

export default {
  name: "TodoQuery",
  data(){
    return {
      todos:[]
    }
  },
  methods:{
    query(){
      axios.get("http://127.0.0.1:8080/todos").then(
          response => {
            console.log(response.data)
            const data = response.data;
            // const flag = data.flag;
            this.todos = data.data;
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