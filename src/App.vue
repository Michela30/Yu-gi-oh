<script>
//import
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import LoaderComponent from './components/LoaderComponent.vue';

import {store} from './store.js'

import axios from 'axios';

   export default {
    data() {
      return{
        store,
        isLoad: false,
      }
    },
    components: {
      HeaderComponent,
      MainComponent,
      LoaderComponent
     
    },
    created(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(response => {
        console.log(response.data);
        this.store.cards = response.data.data;
        isLoad = true;
      })

    }
  }
</script>



<template>
  <div>
    <HeaderComponent/>

    <LoaderComponent v-if="isLoad = false"/>

    <MainComponent v-else/>

  </div>
</template>




<style lang="scss">
@use 'assets/scss/main.scss';




</style>
