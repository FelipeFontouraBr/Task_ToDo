<template>

<div>
  <div class="container">
    <form id="formu">
    <div class="row">      
        <div class="col-md-6">
          <div class="input-group">
            <input type="text" class="form-control">
          </div>
        </div>
        <div class="col-md-2">
          <button class="btn btn-primary">Added</button>
        </div>      
    </div>
    </form>
  </div>
</div>

</template>

<script>
import "bootstrap/dist/css/bootstrap.css"
import "font-awesome/css/font-awesome.css"

export default {
  name: 'app',
  }

</script>

<style>
.row {
  margin-top: 180px;
  margin-left: 200px;  
}
#formu {
  background-color: blue;
}
</style>
