<template>
  <div class="CityC">
    <CityId />
  </div>
</template>

<script>
// @ is an alias to /src
import CityId from '../components/CityId.vue'

export default {
  name: 'CityC',
  components: {
    CityId
  },
  data() {
    return {
      idCity: '',
    }
  }
}
</script>
