<template>
  <div>
    <h1>{{ msg }}</h1>
    <div class="flex d-inline-flex">
      <div v-for="city in cities" :key="city.id">
        <CityMeteo
          :name="city.name"
          :weather="city.weather"
          :temperature="city.temperature"
          :updatedAt="city.updatedAt"
        />
      </div>
    </div>
  </div>
</template>


<script>
import CityMeteo from "./CityMeteo.vue";

export default {
  name: "CitiesList",
  props: {
    msg: String,
  },
  components: {
    CityMeteo,
  },
  data() {
    return {
      cities: [
        {
          id: 1,
          name: "Saint-Martin d'Hères",
          weather: "Ensoleillé",
          temperature: 22.0,
          updatedAt: new Date(),
        },
        {
          id: 2,
          name: "Grenoble", // nom de la ville
          weather: "Peu nuageux", // descriptif météo
          temperature: 19.5, // température en °C
          updatedAt: new Date("April 24, 2022"), // date de dernière mise à jour
        },
      ],
    };
  },
};
</script>

