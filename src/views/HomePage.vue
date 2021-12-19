<template>
  <div class="Search">
    <CitySearch />
  </div>
</template>

<script>
// @ is an alias to /src
import CitySearch from '../components/CitySearch.vue'

export default {
  name: 'Search',
  components: {
    CitySearch
  },
  data() {
    return {
      idCity: '',
      
    }
  }
}
</script>
