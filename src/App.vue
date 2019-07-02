<template>
  <div id="app" class="small-container">
   <h1>Todo List</h1>
   <todo-form />
   <todo-table :tasks="tasks"/>
  </div>
</template>

<script>
import TodoTable from './components/TodoTable.vue'
import TodoForm from './components/TodoForm.vue'

export default {
  name: 'app',
  components: {
    TodoTable,
    TodoForm
  },
  data(){
    return{
      tasks : [
        {
          id : 1,
          name : 'Shop for clothes, shoes and accessories',
          description : 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
        },
        {
          id : 2,
          name : 'Apply for Visa',
          description : 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
        },
        {
          id : 3,
          name : 'Book flight tickets',
          description : 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
        },
        {
          id : 4,
          name : 'Book hotel tickets',
          description : 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
        }
      ],
    }
  }
}
</script>

<style>
button {
    background: #009435;
    border: 1px solid #009435;
  }

  .small-container {
    max-width: 680px;
  }
</style>
