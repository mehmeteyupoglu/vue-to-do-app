<template>
  <div class="hello">
    <h1>{{ todo }}</h1>
    <form @submit.prevent="addTodo">
      <input  v-model="todos" placeholder="Add Todos..."/>
    </form>
    
    <div v-if="todoList.length  > 0" >
      <ul class="todo" >
        <li v-for="item in todoList" :key="item" class="items">
          {{ item }}
          <button @click="deleteTodo" > X </button>
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
      todoList: [] 

    }
  }, 
  methods : {
    addTodo() {
      this.todoList.push(this.todos)
      this.todos = ""
    }, 

    deleteTodo() {
      this.todoList.filter(element => element !== this.todos)
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

.todo {
  position: relative;
  display: flex; 
  flex-direction: column;
  align-items: flex-start;
  width: 250px; 
  margin-left: 31%;   
  background: whitesmoke; 
  box-shadow: 2px 2px 10px gray; 
   
}

.items {
  display: flex;   
  align-items: center; 
  margin-bottom: 10px;
  padding: 15px 0;  
}

input {
  width: 245px; 
  height: 20px; 
  margin-left: 7px; 
  margin-bottom: 10px; 
}

button {
  width: 20px; 
  height: 20px; 
  display: flex; 
  justify-content: center; 
  align-items: center; 
  border: none; 
  background-color: gray; 
  border-radius: 2px; 
  color: white; 
  position: absolute; 
  right: 10px; 

}
</style>
