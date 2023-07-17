<script>
//import
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';

import axios from 'axios';

   export default {
    data() {
      return{
        cards : []
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
        this.cards = response.data
      })

    }
  }
</script>



<template>
  <div>
    <HeaderComponent/>

    <MainComponent :cards="cards.data" />

    

  </div>
</template>




<style lang="scss">
@use 'assets/scss/main.scss';




</style>
