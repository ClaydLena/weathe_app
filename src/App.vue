<script setup>
  import Weather from './components/WeatherPage.vue';
  </script>
  
  <template>  
     <Weather/>
  </template>
  
  <style>
   header{
    width: 100%;
    display: flex;
    place-content: center;
   }
  .inputSearch{
    margin: 100px 0px 0px 0px;
    width: 500px;
    background-color: whitesmoke;
    height: 38px;
    border-radius: 10%;
  }
  .cont{
    place-self: center;
    width: 80%;
    display: grid;
    grid-template-columns: auto auto auto;
  }
  
  @media (min-width: 1024px) {
   
  }
  </style>