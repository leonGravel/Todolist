<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h3>Todolist</h3>
    <div class="body">
      <el-input
      v-model="newTodoText"
      id="new-todo"
      placeholder="今天做什么呢？"
    >
    <el-button type="primary" slot="append" size="mini" @click="addNewTodo">Add</el-button>
    </el-input>
     <ul>
   <todolist v-for="todo in todos" :key="todo.id" :todo="todo" :deleteItem="deleteItem" />
   </ul>
   </div>
   
  </div>

</template>

<script>
import todolist from './components/todolist.vue'

export default {
  name: 'app',
  components: {
    todolist
  },
   data: function () {
    return {
      newTodoText:"打豆豆",
      todos: [ 
      {
        id: 1,
        title: '吃饭',
      },
      {
        id: 2,
        title: '睡觉',
      }
    ]
    }
  },
  

  methods: {
    addNewTodo: function () {
      this.todos.push({
        id: this.todos.length+1,
        title: this.newTodoText
      })
      this.newTodoText = '打豆豆'
    },
    deleteItem: function(key){
      this.todos = this.todos.filter((item)=> item.id!=key)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.body {
  width: 300px;
  margin: 0 auto;
}
</style>
