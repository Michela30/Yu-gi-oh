<script>
//import
import {store} from '../store.js'

   export default {
    data() {
      return{
        //dati
        store,
      
      }
    },
    methods: {
        //function
    },
    components: {
        //dichiarazione
    },
    props:{
        //utilizzo per file padre
    }
    
  }
</script>


<template>


<div class="loader"></div>


</template>




<style lang="scss" scoped>
@use '../assets/scss/variables.scss' as *;

.loader {
margin: auto;
margin-top: 70px;
border: 20px solid #EAF0F6;
border-radius: 50%;
border-top: 20px solid #D48F38;
width: 100px;
height: 100px;
animation: spinner 4s linear infinite;

}


@keyframes spinner {

0% { transform: rotate(0deg); }
100% { transform: rotate(360deg); }
}




</style>