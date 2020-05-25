<template>
<div class="row">
    <div class="col-xs-10" :class="{checked: todo.checked}">
        <table class="table">
            <thead>
            <tr>
            <th>Task Name</th>
            <th></th>
            </tr>
            </thead>
            <tbody>
            <tr>
            <td class="col-xs-11">
            {{todo.description}}
            </td>
            <td class="col-xs-1">
            <button class="btn btn-danger">
            x
            </button>
            </td>
            </tr>
            </tbody>
        </table>
    </div>
</div>
</template>

<script>
export default {
    props: {
        todo: {type: Object, required: true}
    }
};
</script>

<style scoped>

</style>