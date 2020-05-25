<template>

<div class="container">
  <img src="@/assets/task.png" id="img">  
  <form v-on:submit.prevent="addTodo(todo)">
    <div class="row" id="ipt">      
        <div class="col-md-6" >
          <div class="input-group" >
            <input type="text" v-model="todo.description" class="form-control" placeholder="Nova Tarefa" >
          </div>
        </div>
        <div class="col-md-4">
          <button class="btn btn-primary">Adicionar</button>
        </div>      
    </div>
  </form>
  <div class="todo-list"><!--Aqui vamos colocar as configurações do todo-list-->
    <todo v-for="t in todos" :key="t.id" @toggle="toggleTodo" @remove="removeTodo" :todo="t"/>
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
.container {
  margin-top: 90px;
  margin-left: 140px;
}
.row {
  margin-top: 30px;
  margin-left: 210px;
}
#ipt {
  margin-left: 200px;
}
#img {
  max-width: 160px;
  margin-left: 360px;
}
.form-control {
  border: 1px solid rgb(155, 183, 206);
}
</style>
