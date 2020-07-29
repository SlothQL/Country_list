<template>
  <div v-if="country">
      <h2>{{country.name}}</h2>
      <p>Population: {{country.population}}</p>
      <p>Capital: {{country.capital}}</p>

  </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']
}
</script>

<style>

</style>