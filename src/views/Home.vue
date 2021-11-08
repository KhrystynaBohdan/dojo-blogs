<template>
  <div class="home">
    home
    <p>My name is  {{ name }} and age  {{age}}</p>
    <button v-on:click="handleClick">click me</button>
  </div>
</template>

<script>

export default {
  name: "Home",
  //this func(setup) will run before any lifecircle hooks
  setup() {
    console.log("setup");
    let name = "coco";
    let age = 1;

    const handleClick = () => {
      console.log('you clicked me')
    }

    return { name, age, handleClick };
  }

};
</script>
