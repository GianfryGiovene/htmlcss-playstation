<template>  
    <div id="input-search">
        <label for="search">Ricerca qui: </label>
        <input 
            v-model="getInput" 
            type="text" 
            name="search" 
            placeholder="Inizia la ricerca"
            @keyup="sendInput"
        >
    </div>
</template>

<script>

export default {
    name:'SearchComponent',
    data(){
        return{
            getInput:''
        }
    },
    methods:{
        // creo l'evento search per inviare il dato ricevuto da input
        sendInput(){
            this.$emit('search', this.getInput);
        }
    }
}
</script>

<style>
</style>