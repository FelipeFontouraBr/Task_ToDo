<template>
<div class="row">
    <div class="col-md-7" :class="{checked: todo.checked}">
            <div class="col-md-5">
            <i class="fa fa-clock-o fa-lg" aria-hidden="true"></i>
            {{todo.description}}        
            <button v-on:click="$emit('toggle', todo)" class="btn btn-outline-primary">
                <span v-if="todo.checked">Desmarcar</span>
                <span v-else>Concluído</span>
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