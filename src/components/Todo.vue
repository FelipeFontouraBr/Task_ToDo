<template>
<div class="row">
    <div class="col-md-7" :class="{checked: todo.checked}">
        <i class="fa fa-clock-o fa-lg" aria-hidden="true" :class="todo.checked ? 'fa-check-square' : 'fa-clock-o'"></i>
            {{todo.description}}        
            <button v-on:click="$emit('toggle', todo)" class="btn btn-outline-primary" id="bt1">
                <span v-if="todo.checked">Desmarcar</span>
                <span v-else>Concluído</span>
            </button>
            <button v-on:click="$emit('remove', todo)" class="btn btn-outline-danger ml-2" id="bt2">Remover
            </button>            
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
.checked {
    text-decoration: line-through;
    color: lightblue;
}
#bt1 {
    padding: 4px;
}
#bt2 {
    padding: 4px;
}
</style>