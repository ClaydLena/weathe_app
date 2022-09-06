<script>
  export default {
    name:'CityCard',
    data() {
      return {
        text: ''
      }
    }
  }
</script>

<template>
    <div class="item">
        <div class="titulo">
            <h3> <slot name="heading"></slot> </h3>
        </div>
        <div class="icone">
            <i> <slot name="icon"></slot></i>
        </div>
        <div class="detalhes"> 
            <div></div>
            <div></div>
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
      margin-bottom: 0.4rem;
    }
    
    .icone {
      place-items: center;
      place-content: center;
      margin-bottom: 0.4rem;
    }
    
    .detalhes{
    display: grid;
    grid-auto-columns: auto auto;
     }
    </style>
    