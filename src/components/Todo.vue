<template>
    <div class="row" :class="{checked: todo.checked}">
        <!--<div class="col-md-5" :class="{checked: todo.checked}">-->
        <div class="col-md-2">
            <i class="icon" :class="todo.checked ? 'icon-check' : 'icon-time'"></i>
        </div>        
        <div class="col-md-5">
            {{ todo.description }}
        </div>        
    </div>
</template>

<script>
export default {
    props: {
        todo: {type: Object, required: true}
    }
}
</script>

<style scoped>

</style>