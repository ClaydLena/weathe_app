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
        </div>
        <div class="detalhes"> 
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
      margin:35%;
      place-self: center;
    }
    
    .icone {
      place-items: center;
      place-content: center;
      margin-bottom: 0.4rem;
    }
    
    .detalhes{
      margin-top:50%;
      display: grid;
      grid-template-columns: auto auto;
      justify-content: space-between;
    }
    </style>
    