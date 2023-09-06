<script>
  import ToDoList from './components/ToDoList.vue';
  import AddTodo from './components/AddTodo.vue';

  export default {
    components: {
        ToDoList,
        AddTodo
      },
    data(){
      return{
        todos:[]
      }
    },

    created() {

      const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };

      this.todos = [
        {
          id:1,
          text: "Acheter du soda",
          complete: false,
          date: new Date().toLocaleDateString('fr-FR', options),
          dateCompleted: null
        },
        {
          id:2,
          text: "Préparer la salade",
          complete: false,
          date: new Date().toLocaleDateString('fr-FR', options),
          dateCompleted: null
        },
        {
          id:3,
          text: "Acheter le poulet",
          complete: false,
          date: new Date().toLocaleDateString('fr-FR', options),
          dateCompleted: null
        },
        {
          id:4,
          text: "Préparer une tarte aux pommes",
          complete: false,
          date: new Date().toLocaleDateString('fr-FR', options),
          dateCompleted: null
        },
        {
          id:5,
          text: "Prendre le matériel pour le pique-nique",
          complete: false,
          date: new Date().toLocaleDateString('fr-FR', options),
          dateCompleted: null
        },
      ]
      console.log(this.todos);
    },

    methods: {
      deleteTodo(todoId) {
        if(confirm('est vous sûr de supprimer?')) {
          this.todos = this.todos.filter((todo)=> todo.id !== todoId)
          console.log(this.todos);
        }
      },
      addTodo(todo) {
          this.todos = [...this.todos,todo];
          console.log(this.todos);

      },      
    }
  }
</script>

<template>
  <div>
      <AddTodo @add-todo="addTodo" />
      <ToDoList :todos="todos" @delete-todo="deleteTodo" />
  </div>
</template>

<style scoped>


@media (min-width: 1024px) {

}
</style>
