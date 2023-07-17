<script>
//import
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';

import axios from 'axios';

   export default {
    data() {
      return{

      }
    },
    components: {
      HeaderComponent,
      MainComponent,
     
    },
    created(){
      axios.get('')
      .then(response => {
        console.log(response.data)
      })

    }
  }
</script>



<template>
  <div>
    <HeaderComponent/>

    <MainComponent/>

    

  </div>
</template>




<style lang="scss">
@use 'assets/scss/main.scss';




</style>
