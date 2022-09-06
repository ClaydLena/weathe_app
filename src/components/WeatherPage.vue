<script>
    import 'bootstrap/dist/css/bootstrap.css'  
    import CityCard from './CityCard.vue';

    const temp = []
      const cities =["Maputo", "Macia", "Inhambane", "Xai-xai","Boane","Beira","Chimoio", "Pemba","Vilanculos", "Tete", "Quelimane", "Nampula"]  
      cities.forEach((city)=>{
        fetch(
          "https://api.openweathermap.org/data/2.5/weather?q="+city+",mz&units=metric&APPID=43102702ba5a4fb88e0aaff670064883"
        )
          .then((resp) => resp.json())
          .then((data) => {
          temp.push(data)    
          })
      })
      
    export default {      
      name:'WeatherPage',
      components:{
         CityCard
      },

      data(){
        return{
            cidade: "",
            input_city:" ",
            dados:temp
        }
    },
    methods:{
        submitForm(e){
            e.preventDefault();
            this.cidade = this.input_city;
            console.log(this.dados)
        },
    },
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
                <CityCard nome="lena" temp_max="10" temp_min="10" foto="10"></CityCard>
            </div>
          </li>

          <li class="cards_item">
            <div class="card">
                <CityCard nome="Lena" temp_max="10" temp_min="10" foto="10"></CityCard>
            </div>             
          </li>

          <li class="cards_item">
            <div class="card">
                <CityCard nome="Lena" temp_max="10" temp_min="10" foto="10"></CityCard>
            </div>  
          </li>

        </ul>
      </div>
      <li v-for="(technology, index) in dados" v-bind:key="index">
                {{technology.name}}</li>
      <h3 class="txt">Clayd Lena Agostinho Nandza</h3>
    </template>