<script>
//import

   export default {
    data() {
      return{
        //dati
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
        cards: []
    }
    
  }
</script>


<template>

    <main>
        <section class="select-input">
          <select class="form-select" aria-label="select">
            <option selected>Select</option>
            <option value="1">Alien</option>
            <option value="2">Noble Knight</option>
            <option value="3">Tainted Treasure</option>
            <option value="4">Melodious</option>
            <option value="5">Archfiend</option>
          </select>
        </section>


        <div class="container">
            
            <!-- length -->
            <div class="number-container">
                qui ci sono 39 card
            </div>

          <div class="row my_row">

            <div class="col-sm-12 col-md-4 column" v-for="(singleCard, i) in cards" :key="i">

                <div class="my_card">
                <div class="card-img-box">
                    <img :src="singleCard.card_images[0].image_url_small" alt="">
                </div>

                <div class="text-center py-4">
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
  background-color: bisque;
}

.select-input{
  width: 15%;
  margin-left: 80px;
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
        background-color: chocolate;

        .my_card {
        height: 300px;

            .card-img-box {
            width: 100%;
            height: 200px;
            border: 2px solid red;

            img {
                width: 100%;
            }
            }
        }
        }
    }

}
</style>