<template>
  <div class="CitySearch">
    <input 
        type="text" 
        placeholder="search..."
        v-model="query"
        @keypress="fetchWeather"
        />

    <div>{{ weather.name }}</div>
    <!-- <div>{{ weather.main["temp"] + " °C"}}</div> -->
  </div>
</template>

<script>
// const axios = require('axios').default;
//   methods:  {
//     searchCity(){
//          axios
//         .get('https://geo.api.gouv.fr/communes?departement&nom=${this.query}')
//         .then(response => (this.city = response.data))
//     },
//   } 
export default {
  name: 'CitySearch',
  props: {
   
  },
  data () {
    return {
      api_key: 'd2e33b810d399f2fb3d6791d161388ec',
      url_base: 'https://api.openweathermap.org/data/2.5/',
      query: '',
      weather: {}
    }
  },
  methods: {
   fetchWeather (e) {
      if (e.key == "Enter") {
        fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
          .then(res => {
            return res.json();
          }).then(this.setResults);
      }
    },
        setResults (results) {
        this.weather = results;
        },
    }
}
</script>

<style scoped>

</style>
