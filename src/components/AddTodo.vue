<script>
export default {
    data(){
        return {
            text:''
        }
    },

    emits: ['add-todo'],

    methods : {
        
        onSubmit(e) {
            if(!this.text){
                alert("Veuillez entrer le texte pour la tâche")
            } else {
                const newTodo = {
                    id: Math.floor(Math.random()*100000),
                    text: this.text,
                    complete: false,
                    date: new Date().toDateString(),
                    dateCompleted: false
                }
                this.$emit('add-todo', newTodo)
                this.text = ''
            }
        }
    },

}
</script>
<template>
    <div>
        <form @submit.prevent="onSubmit">
            <input  v-model="text" type="text">
            <button type="submit" class="btn-primary">Ajouter une tâche</button>
        </form>
    </div>
</template>