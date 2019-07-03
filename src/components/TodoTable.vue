<template>
    <div id="todo-table">
        <table>
            <thead>
                <tr>
                    <th>Tasks</th>
                    <th>Description</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="todo in todos" :key="todo.id">
                    <td>{{ todo.name }}</td>
                    <td>{{ todo.description }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name : 'todo-table',
    props : {
        todos : Array
    }

}
</script>

<style>

</style>
