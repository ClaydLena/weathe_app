<script>
  export default {
    name:'CityCard',
    data() {
      return {
        text: ''
      }
    },
    
   props:['nome', 'temp_max','temp_min','ceu']
} 
</script>

<template>
    <div class="item">
        <div class="titulo">
            <h3><slot name="heading">{{nome}}</slot> </h3>
        </div>
        <div class="icone">
            <p class="ceu">{{ceu}}</p>
            <div class="img">
              <img v-if="ceu ==='Clouds'" src="./imgs/cloudy.png" class="img"/>
              <img v-if="ceu ==='Clear'" src="./imgs/sun.png" class="img"/>
              <img v-if="ceu ==='Haze'" src="./imgs/cloudy.png" class="img"/>
            </div>
        </div>
        <div class="detalhes" v-if="temp_max"> 
            <div>Max {{temp_max}}</div>
            <div>Min {{temp_min}}</div>
        </div>
    </div>
  </template>


  <style scoped>
    *{
        color:white;
    }
    .item {
      margin-top: 2rem;
      background-color: #3c6f91;
      width: 350px;
      height: 450px;
      border-radius: 3%;
      margin:55px 50px 10px 50px;
      display:grid;
      grid-template-rows: 10% 50% 40%;
      place-content: center;
    }

    .titulo {
      font-size: 1.2rem;
      font-weight: 500;
      margin: 20px;
    }

    .ceu{
      font-size: 18px;
      margin:25%;
      place-self: center;
    }
    
    .icone {
      place-items: center;
      place-content: center;
      margin-bottom: 0.4rem;
    }
    .img{
      align-self: center;
      position: absolute;
      width: 80%;
      height: 70%;
    }
    
    .detalhes{
      column-gap: 2%;
      margin-top:50%;
      display: grid;
      grid-template-columns: auto auto;
      justify-content: space-between;
    }
    </style>