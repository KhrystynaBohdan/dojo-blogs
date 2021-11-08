<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search"/>
    <p>search term -{{search}}</p>
    <div v-for="name in matchNames" :key="name">{{ name }}</div>
    <button v-on:click="handleClick">stop watching </button>
  </div>
</template>

<script>

import { computed, ref, watch, watchEffect } from "vue";

export default {
  name: "Home",
  setup() {
    const search = ref('')
    const names = ref(['coco', 'anna', 'ola'])

    const stopwatch= watch(search, () => {
      console.log ('watch')
    })

    //watchEffect when component first run
    const stopwatchEffect = watchEffect(() => {
      console.log('watchEffect', search.value)
    })
    //we use computed property to return an updated value based on other values

    const matchNames = computed (() => {
      return names.value.filter(name => name.includes(search.value))
    })

    const handleClick = () => {
      stopwatch()
      stopwatchEffect()
    }
    return {names, search, matchNames, handleClick};
  }

};
</script>
