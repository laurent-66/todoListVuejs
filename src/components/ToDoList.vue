<script>
  export default {
      props: {
        todos: Array
      },
      emits: ['delete-todo'],

    }


</script>

<template>
  <div>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">A faire</th>
          <th scope="col">Date de création</th>
          <th scope="col">Tâche effectué</th>
          <th scope="col">Editer</th>
          <th scope="col">Supprimer</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="todo in todos" :key="todo.id">
          <th scope="row">{{ todo.text }}</th>
          <td>{{ todo.date}}</td>
          <td>tâche complète</td>
          <td>Editer</td>
          <td>
            <button @click="$emit('delete-todo', todo.id )" 
            class="btn btn-danger">
            Supprimer
            </button>
          </td>    
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>


@media (min-width: 1024px) {

}
</style>
