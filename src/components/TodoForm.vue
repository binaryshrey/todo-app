<template>
    <div id='todo-form'>
        <form @submit.prevent="handleSubmit">
            <label for="name">Task Name</label>
            <input v-model="todo.name" type="text" id="name"  />
            <label for="desc">Description</label>
            <input v-model="todo.description" type="text" id="desc" />
            <button>Add Task</button>
        </form>
    </div>
</template>

<script>
export default {
    name : 'todo-form',
    data(){
        return{
           todo : {
                name : '',
                description : '',
           }
        }
    },
    methods : {
        handleSubmit(){
            this.$emit('add:todo',this.todo);
        }
    }

}
</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }
</style>