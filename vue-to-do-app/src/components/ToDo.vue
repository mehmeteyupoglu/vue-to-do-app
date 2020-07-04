<template>
  <div class="hello">
    <h1>{{ todo }}</h1>
    <form @submit.prevent="addTodo">
      <input  v-model="todos" placeholder="Add Todos..."/>
    </form>
    
    <div v-if="todoList.length > 0">
      <ul>
        <li v-for="item in todoList" :key="item" >
          {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
  props: {
    todo: String
  }, 

  data(){
    return {
      todos :  "",
      todoList: ["Mehmet", "Sena"] 

    }
  }, 
  methods : {
    addTodo() {
      this.todoList.push(this.todos)
      this.todos = ""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
