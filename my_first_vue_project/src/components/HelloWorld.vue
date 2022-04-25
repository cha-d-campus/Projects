<template>
  <div>
    <h1>{{ msg }}</h1>
    <CityMeteo/>
  </div>
</template>


<script>
import CityMeteo from './CityMeteo.vue'

export default {
  name: "HelloWorld",
  props: {
    msg: String,
    cityname: CityMeteo.name ,
  },
  components: {
    CityMeteo
  }
};
</script>