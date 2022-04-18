<template>
  <div id="app">
    <HeaderComponent :navBar="navPrimary" />
    <MainComponent/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue'
export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },
  data(){
    return{
      navPrimary:[
        {
          name:'Giochi',
          clicked: false,
        },
        {
          name:'Hardware',
          clicked: false,
        },
        {
          name:'Servizi',
          clicked: false,
        },
        {
          name:'Novità',
          clicked: false,
        },
        {
          name:'Fai acquisti',
          clicked: false,
        },
            
        {
          name:'Supporto',
          clicked: false,
        }],
    }
  },
}
</script>

<style lang="scss">
@import './style/general';


</style>
