<template>
<div class="row">
    <div class="col-md-7" :class="{checked: todo.checked}">
            <div class="col-md-5">
            <i class="fa fa-clock-o fa-lg" aria-hidden="true"></i>
            {{todo.description}}        
            <button class="btn btn-danger">
            x
            </button>
            </div>
    </div>
</div>
</template>

<script>
import "font-awesome/css/font-awesome.css"

export default {
    props: {
        todo: {type: Object, required: true}
    }
};
</script>

<style scoped>

</style>