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
    methods:{
      getCards(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0', {
        params: {
          archetype: this.store.searchType
        }
        })
        .then(response => {
          console.log(response.data);
          this.store.cards = response.data.data;
          
        });
      },

      getArchetype(){
          axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(response => {
          console.log(response.data);
          this.store.archetype = response.data;
          
        })
      },

      searchType(){
        
        this.getArchetype();
        this.getCards();
        
        console.log('intercettato evento emit')
      }
    },
    created() {
     
      this.getCards();
      this.getArchetype();
      
    },
    mounted(){
        setTimeout(() => {
          this.isLoad = true;
        }, 5000);
    },
  }
</script>



<template>
  <div>
    <HeaderComponent/>

    <LoaderComponent v-if="isLoad == false"/>

    <MainComponent v-else @search="searchType()"/>

  </div>
</template>




<style lang="scss">
@use 'assets/scss/main.scss';




</style>
