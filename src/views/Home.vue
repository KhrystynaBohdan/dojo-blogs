<template>
  <div class="home">
    home
    <p ref="p">My name is  {{ name }} and age  {{age}}</p>
    <button v-on:click="handleClick">click me</button>
  </div>
</template>

<script>

import { ref } from "vue";

export default {
  name: "Home",
  //this func(setup) will run before any lifecircle hooks
  setup() {

    const p = ref(null);

    console.log(p, p.value);
    let name = "coco";
    let age = 1;

    const handleClick = () => {
      console.log(p, p.value)
      p.value.classList.add('test')
      p.value.textContent = 'bohdan'
    }

    return { name, age, handleClick, p};
  }

};
</script>
