<template>
  <div id='todo-item'>
     <el-checkbox v-model="checked"
    
      v-bind:key="todo.id"
      v-bind:title="todo.title"
       type="success"
    >{{ todo.title }}
    <el-button type="danger" icon="el-icon-delete" circle @click="deleteItem(todo.id)" size="mini"></el-button>
    </el-checkbox>
  </div>
  
</template>

<script>
export default {
  name: 'todolist',
  props: {
    todo:Object,
    deleteItem:Function 
  },
  data() {
      return {
        checked: false
      };
    }
}
</script>

 <style scoped>

#todo-item {
 text-align: left;
}
</style>
