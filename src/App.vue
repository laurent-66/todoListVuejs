<script>
  import ToDoList from './components/ToDoList.vue';

  export default {
    components: {
        ToDoList
      },

    created() {
      this.todos = [
        {
          id:1,
          text: "Acheter du soda",
          complete: false,
          date: new Date().toDateString,
          dateCompleted: null
        },
        {
          id:2,
          text: "Préparer la salade",
          complete: false,
          date: new Date().toDateString,
          dateCompleted: null
        },
        {
          id:3,
          text: "Acheter le poulet",
          complete: false,
          date: new Date().toDateString,
          dateCompleted: null
        },
        {
          id:4,
          text: "Préparer une tarte aux pommes",
          complete: false,
          date: new Date().toDateString,
          dateCompleted: null
        },
        {
          id:5,
          text: "Prendre le matériel pour le pique-nique",
          complete: false,
          date: new Date().toDateString,
          dateCompleted: null
        },
      ]
    },
    methods: {
      deleteTodo(todoId) {
        if(confirm('est vous sûr de supprimer?')) {
          this.todos = this.todos.filter((todo)=> todo.id !== todoId)
        }
      }
    }
  }
</script>

<template>
  <div>
      <ToDoList :todos="todos" @delete-todo="deleteTodo" />
  </div>

</template>

<style scoped>


@media (min-width: 1024px) {

}
</style>
