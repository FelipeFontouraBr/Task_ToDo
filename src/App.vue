<template>

<div>
  <div class="container">
    <form v-on:submit.prevent="addTodo(todo)">
      <div class="row">      
          <div class="col-md-6">
            <div class="input-group">
              <input type="text" class="form-control" placeholder="New Task">
            </div>
          </div>
          <div class="col-md-4">
            <button class="btn btn-primary">Added</button>
          </div>      
      </div>
    </form>
    <div class="todo-list"><!--Aqui vamos colocar as configurações do todo-list-->
      <todo v-for="t in todos" :key="t.id" @toggle="toggleTodo" @remove="removeTodo" :todo="t"/>
    </div>
  </div>
</div>

</template>

<script>
import "bootstrap/dist/css/bootstrap.css"
import "font-awesome/css/font-awesome.css"
import Todo from './components/Todo'

export default {
  name: "app",
  components: { Todo },
  data() {
    return { todos: [], todo: { checked: false}};
  },
  methods: { // Ação de adicionar
    addTodo(todo) {
      todo.id = Date.now();
      this.todos.push(todo);
      this.todo = { checked: false};
    },
    toggleTodo(todo){ //Função do onclick -> Vamos alterar o estado do componente (trocar para true ou false)
      const index = this.todos.findIndex(item => item.id === todo.id) 
      if (index > -1){
        const checked = !this.todos[index].checked;
        this.$set(this.todos, index, {...this.todos[index], checked});
      }
    },
    removeTodo(todo) { //Ação de deletar
      const index = this.todos.findIndex(item => item.id === todo.id);
      if (index > -1) {
        this.$delete(this.todos, index); 
      }
    }
  }
};
</script>

<style>
.row {
  margin-top: 180px;
  margin-left: 200px;  
}
</style>
