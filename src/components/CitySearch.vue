<template>
  <div class="City">
     <input 
        type="text" 
        placeholder="search..."
        v-model="query"
        />
      <button type="submit" v-on:click="search">Chercher</button>

      <div v-for="cityC in city" :key="cityC.nom" >
        <input id="cityC.nom" type="radio" />
        <router-link v-bind:to="'/pagemeteo/' + cityC.nom"><label>{{ cityC.nom }}</label></router-link>
      </div>
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
      // id: null,
      query: '',
      city: {},
    }
  },
  methods: {
    search(){
       axios
        .get('https://geo.api.gouv.fr/communes?departement&nom='+this.query)
        .then(response => (this.city = response.data));
    }
  }
}   
</script>

<style scoped>

</style>
