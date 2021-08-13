<template>
  <div>
    <Sales 
      msg="Hello, World 🌎" 
      v-bind:items="['6am','7am','8am','9am', 'daily location total']"
      v-bind:stores="stores"
    />
  </div>
</template>

<script>
import Sales from './components/Sales.vue'

function hourlySales(min, max, average) {
  const result = [];
  for (let i = 0; i < 4; i++) {
    const customersPerHour = (Math.random() * (max - min)) + min;
    result.push(Math.floor(customersPerHour) * average);
  }
  return result
}
const stores = [];
class Store {
  constructor(location, max, min, average){
    this.location = location;
    this.hourlySales = hourlySales(max, min, average)
  }
}

stores.push(new Store('London',10,2,3));
console.log(stores);
export default {
  name: 'App',
  data() {
    
  },
  components: {
    Sales
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
