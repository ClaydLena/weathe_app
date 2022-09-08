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
          input_city:" ",
          nome:" ",
          max: " ",
          min:" ",
          ceu:" ",

      }
  },
  methods:{
      submitForm(e){
          e.preventDefault();
          this.cidade = this.input_city;
      },

      temperaturas(){
        const temp = []
        const cities =["Maputo", "Macia", "Inhambane", "Xai-xai","Boane","Beira","Chimoio", "Pemba","Vilanculos", "Tete", "Quelimane", "Nampula"]  
        cities.forEach((city)=>{
          fetch(
            "https://api.openweathermap.org/data/2.5/weather?q="+city+",mz&units=metric&APPID=43102702ba5a4fb88e0aaff670064883"
          )
            .then((resp) => resp.json())
            .then((data) => {
            temp.push(data)
            console.log(data)    
            this.nome =data.name
            this.temp_max = data.main.temp_max
            this.temp_min = data.main.temp_min
            this.ceu = data.weather[0].main
            console.log(this.ceu)
            })
        })
      },
  },

  created(){
    this.temperaturas();
  },
  mounted(){
    var a = 1
    while (a==1){
      setTimeout(this.temperaturas(), 1000)
    }
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

    <div class="cont" >
      <ul class="cards">

        <li class="cards_item">
          <div class="card">
              <CityCard :nome = 'nome' :temp_max="temp_max" :temp_min = 'temp_min' :ceu="ceu"></CityCard>
          </div>
        </li>

        <li class="cards_item">
          <div class="card">
              <CityCard :nome = 'nome' :temp_max="temp_max" :temp_min = 'temp_min' :ceu="ceu"></CityCard>
          </div>             
        </li>

        <li class="cards_item">
          <div class="card">
              <CityCard :nome = 'nome' :temp_max="temp_max" :temp_min = 'temp_min' :ceu="ceu"></CityCard>
          </div>  
        </li>

      </ul>
    </div>
    <li v-for="(technology, index) in dados" v-bind:key="index">
              {{technology.name}}</li>
    <h3 class="txt">Clayd Lena Agostinho Nandza</h3>
  </template>