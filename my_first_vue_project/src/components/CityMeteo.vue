<template>
  <div>
    <p>{{cities}}</p>
    <div class="container m-4">
      <div class="row justify-content-center">
        <div class="card border border-info border-4 col-4" style="width: 28rem">
          <div class="hello card-body">
            <h3 class="card-title">Nom de la ville</h3>
            <p>{{ name }}</p>
            <h3 class="card-subtitle mb-2">Météo</h3>
            <ul>
              <li class="card-text">Temps : {{ weather }}</li>
              <li class="card-text">Température : {{ temperature }}</li>
            </ul>

            <h3 class="card-subtitle mb-2">Date</h3>
            <p class="card-text">{{ updatedAt.toLocaleString() }}</p>
            <p class="card-text">{{ formatedDate }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import * as timeago from "timeago.js";
export default {
  name: "CityMeteo",
  props: {
    name: String,
    weather: String,
    temperature: Number,
    updatedAt: Date,
  },
  computed: {
    formatedDate: function () {
      return timeago.format(this.updatedAt, "fr_FR");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: auto;
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
