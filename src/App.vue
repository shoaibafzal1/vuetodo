<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>
<script>
import AddTodo from './components/AddTodo.vue';
import Todos from './components/Todos';
export default {
  name: 'app',
  components:{
    Todos,
    AddTodo
  },
  data() {
    return {
      todos:[
        {
          id:1,
          title:'first task',
          completed:false
        },

        {
          id:2,
          title:'do Laundary',
          completed:false
        },
        {
          id:3,
          title:'make arrangement for living',
          completed:false
        }
      ],
    }
  },

  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj]
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
  }
}
</script>
