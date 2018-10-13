<template>  
  <div class="home">
    <h1>Subway Kalorilaskuri</h1>
    <div class="bg" />
    <div class="calculator">
      <Calculator 
      v-bind:breads="breads"
      v-bind:sauces="sauces" 
      v-bind:meats="meats"
      v-bind:cheeses="cheeses"  
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Calculator from "@/components/Calculator.vue";
import { breads, cheeses, meats, sauces } from "@/data/data.js";
export default {
  name: "home",
  components: {
    Calculator
  },
  data() {
    return {
      breads: breads,
      cheeses: cheeses,
      meats: meats,
      sauces: sauces
    };
  }
};
</script>
<style scoped lang="scss">
h1 {
  color: yellow;
  -webkit-text-stroke: 1px black;
  text-transform: uppercase;
}
.home {
  position: relative;
}
.bg {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  background: url("../assets/veggies.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  z-index: -2;
  opacity: 0.06;
}
</style>
