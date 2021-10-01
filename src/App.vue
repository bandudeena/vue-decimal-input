<template>
<div v-for="(cost, idx) in costs" :key="idx">
<VueDecimalInput v-model="costs[idx]" :step="0.005" :decimal="3"/>
</div>
</template>

<script>
import VueDecimalInput from './components/VueDecimalInput.vue'

export default {
  name: 'App',
  components: {
    VueDecimalInput
  },
  data() {
    return {
      costs: [45,56.1,200,254.56,89.0]
    }
  },
}
</script>
``
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
