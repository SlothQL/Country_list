<template>
  <div>
    <h1>All countries</h1>
    <countries-list :countries='countries'></countries-list>
    <country-detail :country='selectedCountry'></country-detail>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import { eventBus } from '@/main.js';

export default {
    name: 'app',
    data() {
        return {
            countries: [],
            selectedCountry: null
        };
    },
    mounted() {
        fetch('https://restcountries.eu/rest/v2/all')
        .then(response => response.json())
        .then(countries => this.countries = countries)

    },
    components: {
      'countries-list': CountriesList,
      'country-detail': CountryDetail
    }
}
</script>


<style>

</style>