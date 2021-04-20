<template>
  <div class="todolist">
    <h1>Todo</h1>
    <ul v-if="todos.length">
      <TodoListItem
        v-for="todo in todos"
        :key="todo.id"
        :todo="todo"
        @remove="removeTodo"
        
      />
      <TodoInputText
        @add="addItem"
      />
    </ul>
    <p v-else>
      TODO 一覧はありません
    </p>
  </div>
</template>

<script>
import TodoListItem from "../components/TodoListItem";
import TodoInputText from "../components/TodoInputText";
export default {
  components:{
    TodoListItem,
    TodoInputText
  },
  data() {
    return {
      todos: [
        { id: 1, text: "Learn Vue" },
        { id: 2, text: "Learn about single file components" },
        { id: 3, text: "Learn about components" }
      ]
    };
  },
  methods:{
    removeTodo(idToRemove){
      this.todos = this.todos.filter(todo => {
      return todo.id !== idToRemove;
    });
    },
    addItem(inputText){
      var latestId = this.todos[this.todos.length-1].id;
      this.todos.push( { id: latestId+1, text: inputText });
    }
  }
};
</script>

<style>
h1 {
  text-align: center;
}

.todolist {
  max-width: 400px;
  margin: 0 auto;
  text-align: left;
}
</style>