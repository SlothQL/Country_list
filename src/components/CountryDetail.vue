<template>
  <div v-if="country" class="wrapper">
      <img class="lrg-flag" :src="country.flag" />
      <div class="country-details">
      <h2>{{country.name}}</h2>
      <p>Population: {{country.population}}</p>
      <p>Capital: {{country.capital}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']
}
</script>

<style scoped>
.wrapper {
    display:flex;
}
.lrg-flag {
    height: 100px;
    margin-top: 30px;
    margin-right: 30px;
}

.country-details {
    margin-top: 10px;
}
</style>