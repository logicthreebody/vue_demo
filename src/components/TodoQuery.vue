<template>
  <div>
    <input v-model="keyword"/><button @click="query">查询</button>
  </div>
</template>

<script>
import axios from "axios"
export default {
  name: "TodoQuery",
  data(){
    return {
      keyword:""
    }
  },
  methods:{
    query(){
      axios.get("http://127.0.0.1:8080/todos").then(
          response => {
            console.log(response.data)
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