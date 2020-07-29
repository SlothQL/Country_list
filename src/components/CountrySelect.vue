<template>
  <div>
      <select v-model="country" v-on:change="handleSelect">
          <option v-for="(country, index) in countries" :country="country" :key="index" v-bind:value="country">{{country.name}}</option>
      </select>
  </div>
</template>

<script>
import { eventBus } from '@/main.js'

export default {
    name: 'country-select',
    data() {
        return {
            country: {}
        }
    },

    props: ['countries'],

    methods: {
        handleSelect() {
            eventBus.$emit('country-selected', this.country)
        }
    }

}
</script>

<style>

</style>