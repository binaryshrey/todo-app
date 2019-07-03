<template>
    <div id='todo-form'>
        <form @submit.prevent="handleSubmit">
            <label for="name">Task Name</label>
            <input 
            ref="first"
            type="text"
            :class="{ 'has-error' : submitting && invalidName }"
            v-model="todo.name"
            @focus="clearStatus"
            @keypress="clearStatus"
            />

            <label for="desc">Description</label>
            <input
            type="text"
            :class="{ 'has-error' : submitting && invalidDescription }"
            v-model="todo.description"
            @focus="clearStatus"
            />
            <p v-if="error && submitting" class="error-message">
                ❗Please fill out all required fields
            </p>
            <p v-if="success" class="success-message">
                ✅ Task successfully added
            </p>
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
           },
           submitting : false,
           error : false,
           success : false
        }
    },
    methods : {
        handleSubmit(){
            this.submitting = true;
            this.clearStatus();
            if(this.invalidName || this.invalidDescription){
                this.error = true
                return
            }
            this.$emit('add:todo',this.todo);
            this.employee = {
                name : '',
                description : '',
            }
            this.error = false
            this.success = true,
            this.submitting = false
        },
        clearStatus(){
            this.success = false
            this.error = false;
        }
    },
    computed : {
        invalidName() {
            return this.todo.name === ''
        },
        invalidDescription(){
            return this.todo.description === ''
        }
    }

}
</script>

<style scoped>
form {
  margin-bottom: 2rem;
}

[class*="-message"] {
  font-weight: 500;
}

.error-message {
  color: #d33c40;
}

.success-message {
  color: #32a95d;
}
</style>