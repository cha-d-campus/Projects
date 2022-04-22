<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>Nom de la ville</h3>
    <p>{{ name }}</p>

    <h3>Météo</h3>
    <ul>
      <li>Temps : {{ weather }}</li>
      <li>Température : {{ temperature }}</li>
    </ul>

    <h3>Date</h3>
    <p>{{ updatedAt.toLocaleString() }}</p>
  </div>
</template>

<script>
export default {
  name: "CityMeteo",
//   props: {
    
//   },
  data() {
      return {
        name: "Grenoble", // nom de la ville
        weather: "Peu nuageux", // descriptif météo
        temperature: 20.55, // température en °C
        updatedAt: new Date(), // date de dernière mise à jour
      };
    },
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
