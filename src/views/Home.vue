<template>
  <div class="home">
    home
    <p>My name is {{ name }} and age {{ age }}</p>
    <button v-on:click="handleClick">click me</button>
    <button v-on:click="age++">add 1</button>
    <input type="text" v-model="name"/>
  </div>
</template>

<script>

import { ref } from "vue";

export default {
  name: "Home",
  //this func(setup) will run before any lifecircle hooks
  setup() {

    // const p = ref(null);

    const name = ref("coco");
    const age = ref(1);

    const handleClick = () => {
      name.value = "bohdan";
      age.value = 2;
    };

    return { name, age, handleClick };
  }

};
</script>
