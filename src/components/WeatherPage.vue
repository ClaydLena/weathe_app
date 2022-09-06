<script>
    import 'bootstrap/dist/css/bootstrap.css'
  
    import CityCard from './CityCard.vue';

    export default {      
      name:'WeatherPage',
      components:{
         CityCard
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
        },
    },
    
    created(){
      const temp =[]
      const cities =["Maputo", "Macia", "Inhambane", "Xai-xai","Boane","Beira","Chimoio", "Pemba","Vilanculos", "Tete", "Quelimane", "Nampula"]  
      cities.forEach((city)=>{
        fetch(
          "https://api.openweathermap.org/data/2.5/weather?q="+city+",mz&units=metric&APPID=250585e7bf3a2a19e0c48b7945ca6982"
        )
          .then((resp) => resp.json())
          .then((data) => {
          temp.push(data)
          console.log(data)
          })
      })

    }
  }  
</script>
    
    <template>
      <header>
        <h6 class="cidade">{{input_city}}</h6>
        <div class="inputSearch">
          <div class="input-group mb-3">
            <input type="text" v-model="input_city" class="form-control" placeholder="Pesquisar uma cidade">
            <input type="submit" class="btn btn-outline-secondary" value="Pesquisar" v-on:click="submitForm">
          </div>
        </div>
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