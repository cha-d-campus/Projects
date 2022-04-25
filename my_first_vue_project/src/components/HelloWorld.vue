<template>
  <div>
    <h1>{{ msg }}</h1>
    <CityMeteo :cityname="cityname" :weather="weather" :temperature="temperature" :updatedAt="updatedAt"/>
  </div>
</template>


<script>
import CityMeteo from './CityMeteo.vue'

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components: {
    CityMeteo
  },
  data() {
      return {
        cityname: "Grenoble", // nom de la ville
        weather: "Peu nuageux", // descriptif météo
        temperature: 20.55, // température en °C
        updatedAt: new Date('April 24, 2022'), // date de dernière mise à jour
      };
    },
};
</script>