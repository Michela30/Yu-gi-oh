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
    }
    
    
  }
</script>


<template>
    
    <header>
      <div class="title">

        <div class="img-box">
            <img src="https://occ-0-990-987.1.nflxso.net/dnm/api/v6/LmEnxtiAuzezXBjYXPuDgfZ4zZQ/AAAABdpYalFU9SD9K6dNwu9SlKsNaQ3AIGWFrN_uDy6R7N3TS5DHIatIETtgeqwC0kM01zJyor2znGql_ixTWzVueA-GllV7Hn03ygETN_Nd7oZA.png?r=81f" alt=""> 
            
        </div>
        <h1>
          Titolo
        </h1>
      </div>
    </header>

</template>



<style lang="scss" scoped>
@use '../assets/scss/variables.scss' as *;

header {
  height: 70px;
  width: 100%;
  background-color: aquamarine;
  padding-top: 15px;

  .title{
    >* {
      display: inline-block;
      vertical-align: middle;
    }
    
    .img-box {
      width: 70px;
      height: 30px;
      margin-left: 20px;
      
      img {
        width: 100%;
      }
    }
    
      h1 {
       font-size: 1.9em;
       padding-left: 10px;
       margin-bottom: 0;
      }
    
  }
    
}
</style>