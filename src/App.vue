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
  width: 100%;
  display: grid;
  grid-template-columns: auto auto auto;
}

.cards {
display: flex;
flex-wrap: wrap;
list-style: none;
margin: 0;
padding: 0;
}

.cards_item {
display: flex;
padding: 1rem;
}

@media (min-width: 40rem) {
.cards_item {
  width: 50%;
}
}

@media (min-width: 56rem) {
.cards_item {
  width: 33.3333%;
}

}

.detalhes{
  display: grid;
  grid-template-columns: auto auto;
}
.card {
background-color: transparent;
display: flex;
flex-direction: column;
overflow: hidden;
border: none;
}

.txt{
font-weight: 400;
font-size: 13px;
margin-top: 35px;
text-align: center;
}
.cidade{
font-weight: 400;
margin-top: 35px;
text-align: center;
position:absolute;
}
</style>