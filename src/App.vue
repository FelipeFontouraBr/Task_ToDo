<template>

<div>
  <div class="container">
    <form>
      <div class="row">      
          <div class="col-md-5">
            <div class="input-group">
              <input type="text" class="form-control">
            </div>
          </div>
          <div class="col-md-2">
            <button class="btn btn-primary">Added</button>
          </div>      
      </div>
    </form>
    <div class="todo-list"><!--Aqui vamos colocar as configurações do todo-list-->
      
    </div>
  </div>
</div>

</template>

<script>
import "bootstrap/dist/css/bootstrap.css"
import "font-awesome/css/font-awesome.css"

export default {
  name: "app",
  components: {},
  data() {
    return { todos: [], todo: { checked: false}};
  },
  methods: {
    addTodo(todo) {
      todo.id = Date.now();
      this.todos.push(todo);
      this.todo = { checked: false};
    },
    toggleTodo(todo){ //Função do onclick
      const index = this.todos.findIndex(item => item.id === todo.id) 
      if (index > -1){
        const checked = !this.todos[index].checked;
        this.$set(this.todos, index, {...this.todos[index, checked]});
      }
    },
  }
  }

</script>

<style>
.row {
  margin-top: 180px;
  margin-left: 200px;  
}
</style>
