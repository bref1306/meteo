<template>
  <div class="City">
        <div>{{ weather.name }}</div>
        <div>{{ weather.main["temp"] + " °C"}}</div>
        <button v-on:click="back()">Retour</button>
  </div>
</template>

<script>
const axios = require('axios').default;
export default {
  name: 'City',
  props: {
   
  },
  data () {
    return {
      id: this.$route.params.id,
      api_key: 'd2e33b810d399f2fb3d6791d161388ec',
      url_base: 'https://api.openweathermap.org/data/2.5/',
      weather: {}
    }
  },
  
  mounted() {
         axios
        .get('https://api.openweathermap.org/data/2.5/weather?q='+this.id+'&units=metric&APPID=d2e33b810d399f2fb3d6791d161388ec')
        .then(response => (this.weather = response.data));
    },
 methods: {
   back(){
     this.$router.push({name:'HomePage'})
   }
 }
}   
</script>

<style scoped>

</style>
