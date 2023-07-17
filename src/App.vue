<script>
//import
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import {store} from './store.js'

import axios from 'axios';

   export default {
    data() {
      return{
        store,
      }
    },
    components: {
      HeaderComponent,
      MainComponent,
     
    },
    created(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(response => {
        console.log(response.data);
        this.store.cards = response.data.data
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
