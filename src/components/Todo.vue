<template>
    <div class="row">
        <div class="col-md-5" :class="{checked: todo.checked}">

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