<template>
<div>
  <ol>
    <li v-for="todo in todos" :key="todo.id">
      {{todo.name}}------{{todo.description}}
    </li>
  </ol>
</div>
</template>

<script>
export default {
  name: "TodoList",
  data(){
    return {
      todos:[]
    }
  },
  // props:['todos'],
  mounted() {
    this.$bus.$on("getTodos",(todos)=>{
      this.todos = todos;
    })
  }
}
</script>

<style scoped>

</style>