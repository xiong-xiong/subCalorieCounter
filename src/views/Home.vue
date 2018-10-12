<template>
  <div class="home">
    <Calculator 
    v-bind:breads="breads"
    v-bind:sauces="sauces" 
    v-bind:meats="meats"
    v-bind:cheeses="cheeses"  
    />
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
