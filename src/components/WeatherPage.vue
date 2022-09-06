<script>
    import InputSearch from './InputSearch.vue'; 
    import CityCard from './CityCard.vue';

    export default {
      name:'WeatherPage',
      components:{
        InputSearch, CityCard
      },
      data(){
        return{
            cidade: "",
            input_city:""
        }
    },
    methods:{
        submitForm(e){
            e.preventDefault();
            this.cidade = this.input_city;
        }
    }
    }
</script>
    
    <template>
      <header>
        <h6>{{input_city}}</h6>
        <form action="" id="app-form">
            <input type="text" v-model="input_city" placeholder="Digite seu nome">
            <input type="submit" value="Enviar" v-on:click="submitForm">
        </form>
        <InputSearch v-model="input_city" v-on:click="submitForm" @change="submitForm"/>
        <h6>{{input_city}}</h6>
      </header>

      <div class="cont">
        <ul class="cards">
          <li class="cards_item">
            <div class="card">
                <CityCard @click="getData()">
                  <template #icon></template>
                  <template #heading></template>
                </CityCard>
            </div>
          </li>

          <li class="cards_item">
            <div class="card">
                <CityCard>
                  <template #icon></template>
                  <template #heading></template>
                </CityCard>
            </div>
             
          </li>
          <li class="cards_item">
            <div class="card">
                <CityCard>
                  <template #icon></template>
                  <template #heading></template>
                </CityCard>
            </div>  
          </li>
        </ul>
      </div>
      <h3 class="txt">Clayd Lena Agostinho Nandza</h3>
    </template>