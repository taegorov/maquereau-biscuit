<template>
  <div class="sales">
    <header>
      <h2>🐟 Salmon Cookies 🐟</h2>
    </header>
    <form>
      <fieldset>
        Add New Cookie Stand
        <label>
          Location:
          <input
            name="location"
            type="text"
            placeholder="enter a city name..."
          />
        </label>
        <label>
          Minimum Custies per Hour:
          <input name="minimum" type="number" placeholder="0" min="0" />
        </label>
        <label>
          Maximum Custies per Hour:
          <input name="maximum" type="number" placeholder="0" min="0" />
        </label>
        <label>
          Average # of Cookies per Custie:
          <input name="average" type="number" placeholder="0" min="0" />
        </label>
        <button type="submit">Submit</button>
      </fieldset>
    </form>
    <section>
      <table id="sales">
        <tr>
          <th></th>
          <th v-for="item in items" :key="{ item }">
            {{ item }}
          </th>
        </tr>
        <tr v-for="store in stores" :key="{ store }">
          <td>
            {{ store.location }}
          </td>
          <td v-for="sale in store.hourlySales" :key="{ sale }">
            {{ sale }}
          </td>
          <td>
            {{ store.totalSales() }}
          </td>
        </tr>
      </table>
    </section>
  </div>
</template>

<script>
export default {
  name: "Sales",
  props: {
    items: Array,
    stores: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  background: #888;
}
h3 {
  margin: 40px 0 0;
}
table {
  border: 1px solid black;
  background: #42b983;
}
tr {
  border: 1px solid black;
}
th {
  border: 1px solid black;
}
td {
  border: 1px solid black;
}
a {
  color: #42b983;
}
</style>
