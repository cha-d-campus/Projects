<template>
  <div>
    <h1>{{ msg }}</h1>
    <div class="flex d-inline-flex">
      <div v-for="city in cities" :key="city.id">
        <CityMeteo
          :name="city.name"
          :weather="city.weather[0].description"
          :temperature="city.main.temp"
          :updatedAt="updatedAt"
        />
      </div>
    </div>
  </div>
</template>


<script>
import CityMeteo from "./CityMeteo.vue";
import axios from "axios";

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
      // cities: [
      //   {
      //     id: 1,
      //     name: "Saint-Martin d'Hères",
      //     weather: "Ensoleillé",
      //     temperature: 22.0,
      //     updatedAt: new Date(),
      //   },
      //   {
      //     id: 2,
      //     name: "Grenoble", // nom de la ville
      //     weather: "Peu nuageux", // descriptif météo
      //     temperature: 19.5, // température en °C
      //     updatedAt: new Date("April 24, 2022"), // date de dernière mise à jour
      //   },
      // ],
      cities: null,
      updatedAt: new Date(),
      loading: true,
      errored: false,
    };
  },
  mounted() {
    axios
      .get(
        "https://api.openweathermap.org/data/2.5/find?lat=45.188&lon=5.724&cnt=20&cluster=yes&lang=fr&units=metric&APPID=d6cd480572e34633f541e2604a02fdf4"
      )
      .then((response) => {
        console.log(response);
        this.cities = response.data.list;
      })
      .catch((error) => {
        console.log(error);
        this.errored = true;
      })
      .finally(() => (this.loading = false));
  },
};
</script>

