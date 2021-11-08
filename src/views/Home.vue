<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search"/>
    <p>search term -{{search}}</p>
    <div v-for="name in matchNames" :key="name">{{ name }}</div>
  </div>
</template>

<script>

import { computed, ref } from "vue";

export default {
  name: "Home",
  setup() {
    const search = ref('')
    const names = ref(['coco', 'anna', 'ola'])
    //we use computed property to return an updated value based on other values

    const matchNames = computed (() => {
      return names.value.filter(name => name.includes(search.value))
    })
    return {names, search, matchNames};
  }

};
</script>
