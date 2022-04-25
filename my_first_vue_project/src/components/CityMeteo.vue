<template>
  <div class="hello">
    <h3>Nom de la ville</h3>
    <p>{{ cityname }}</p>
    <h3>Météo</h3>
    <ul>
      <li>Temps : {{ weather }}</li>
      <li>Température : {{ temperature }}</li>
    </ul>

    <h3>Date</h3>
    <p>{{ updatedAt.toLocaleString() }}</p>
    <p>{{formatedDate}}</p>
  </div>
</template>

<script>
import * as timeago from 'timeago.js';
export default {
  name: "CityMeteo",
  props: {
    cityname: String,
    weather: String,
    temperature: Number,
    updatedAt: Date
  },
  computed: {
    formatedDate: function(){
      return timeago.format(this.updatedAt, 'fr_FR');
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  /* display: inline-block; */
  margin: 15px 15px;
}
a {
  color: #42b983;
}
</style>
