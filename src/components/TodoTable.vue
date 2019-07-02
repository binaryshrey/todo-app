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
                <tr v-for="task in tasks" :key="task.id">
                    <td>{{ task.name }}</td>
                    <td>{{ task.description }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name : 'todo-table',
    props : {
        tasks : Array
    }

}
</script>

<style>

</style>
