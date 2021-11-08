<template>
  <div class="home">
    <h1>Home</h1>
    <h1>Refs</h1>
    <p>{{cocoOne.name}} - {{cocoOne.age}}</p>
    <button v-on:click="updatecocoOne">update</button>
    <h2>reactive</h2>
    <p>{{cocoTwo.name}} - {{cocoTwo.age}}</p>
    <button v-on:click="updatecocoTwo">update</button>

  </div>
</template>

<script>

import { ref, reactive } from "vue";

export default {
  name: "Home",
  //this func(setup) will run before any lifecircle hooks
  setup() {
    const cocoOne = ref ({name: 'coco', age: 1})
    const cocoTwo = reactive({name: 'anna', age: 36})

    const updatecocoOne = ()=>{
      cocoOne.value.age = 5
    }

    const updatecocoTwo= ()=>{
      cocoTwo.age = 85
    }


    return { cocoOne, updatecocoOne, cocoTwo, updatecocoTwo};
  }

};
</script>
