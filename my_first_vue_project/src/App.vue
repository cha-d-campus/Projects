<template>
  <div id="app">
    <nav class="p-3 bg-dark text-white">
      <ul class="nav col-12 col-lg-auto me-lg-auto mb-2 justify-content-center mb-md-0">
          <li class="link ms-5 me-5"><router-link to="/">Home</router-link></li>
          <li class="link ms-5 me-5"><router-link to="/cities">Cities</router-link></li>
          <li class="link ms-5 me-5"><router-link to="/about">About</router-link></li>
        </ul>
    </nav>

    <img alt="Vue logo" src="./assets/logo-meteo.png">

    <router-view/>
    
  </div>
</template>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}

.link>a {
  text-decoration: none;
  color: azure;
  font-size: 1.2rem;
  font-weight: bold;
}

.link>a:hover {
  text-decoration: none;
  color: rgb(87, 94, 94);
  font-size: 1.2rem;
  font-weight: bold;
}

@import'~bootstrap/dist/css/bootstrap.css';
</style>
