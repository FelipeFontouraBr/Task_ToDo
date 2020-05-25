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
  }
  }

</script>

<style>
.row {
  margin-top: 180px;
  margin-left: 200px;  
}
</style>
