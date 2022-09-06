<script>
    import InputSearch from './InputSearch.vue'; 
    import CityCard from './CityCard.vue';

    export default {
      name:'Weather',
      components:{
        InputSearch, CityCard
      }
    }
</script>
    
    <template>
      <header>
        <InputSearch/>
      </header>
      <div class="cont">
        <div>
          <CityCard @click="getData()">
          <template #icon>
           
          </template>
          <template #heading></template>
    
        </CityCard>
        </div>
        
        <div>
          <CityCard>
          <template #icon>
           
          </template>
          <template #heading></template>
    
        </CityCard>
        </div>
        <div >
          <CityCard>
          <template #icon>
           
          </template>
          <template #heading></template>
    
        </CityCard>
        </div>
      </div>
    </template>