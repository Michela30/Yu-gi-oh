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
    },
    
    
  }
</script>


<template>

    <main>
        <section class="select-input">
          <select  @change="$emit('search')" v-model="store.searchType" class="form-select" aria-label="select">

            <option value="" selected> Select</option>

            <option :value="singleType.archetype_name" v-for="(singleType, index) in store.archetype" :key="index" > {{singleType.archetype_name}} </option>

          </select>
          
        </section>


        <div class="container">
        
            <!-- length -->
            <div class="number-container">
                Found {{store.cards.length}} card 
            </div>

          <div class="row gx-0 my_row">

            <div class="col-6 col-md-4 column" v-for="(singleCard, i) in store.cards" :key="i">

                <div class="my_card">
                    <div class="card-img-box">
                        <img :src="singleCard.card_images[0].image_url_small" alt="" class="img-fluid">
                    </div>

                    <div class="text-center description-image pt-md-0 pt-lg-5">
                        <h6 class="text-white fw-bold text-uppercase">
                            {{ singleCard.name }}
                        </h6>

                        <h6>
                            {{ singleCard.archetype }}
                        </h6>
                    </div>
                </div>

            </div> 
            
          </div>
        </div>


    </main>

</template>




<style lang="scss" scoped>
@use '../assets/scss/variables.scss' as *;

main{
  background-color: #D48F38;
}

.select-input{
  width: 15%;
  margin-left: 100px;
  padding: 20px 0;
}

.container{
  background-color: white;
  padding: 40px 0;

  .number-container{
    background-color: black;
    height: 40px;
    color: white;
    margin: 0 30px;
    line-height: 40px;
    padding-left: 15px;
  }

  .my_row {
   margin: 0 20px;

    >* {
        margin-bottom: 20px;
    }

        .column {
        width: calc((100% / 5) - 20px);
        background-color: #D48F38;

        .my_card {
        height: 50%;

            .description-image{
                background-color: #D48F38;
                word-wrap: break-word;
            }
            .card-img-box {
            width: 100%;
            height: 200px;

            img {
                width: 100%;
            }
            }
        }
        }
    }

}
</style>