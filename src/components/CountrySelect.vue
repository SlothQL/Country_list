<template>
  <div>
      <select v-on:select="handleSelect" v-model="country">
          <option v-for="(country, index) in countries" :country="country" :key="index">{{country.name}}</option>
      </select>
  </div>
</template>

<script>
import { eventBus } from '@/main.js'

export default {
    name: 'country-select',
    data() {
        return {
            country: ''
        }
    },

    props: ['countries'],

    methods: {
        handleSelect: function() {
            eventBus.$emit('country-selected', this.country)
        }
    }

}
</script>

<style>

</style>