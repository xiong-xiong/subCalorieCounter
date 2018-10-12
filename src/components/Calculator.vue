<template>
  <div class="calcContainer">
    Kalorit: {{calories}}
    <form @submit.prevent="calculateCalories">
      <label>Valitse täyte:</label>
      <select v-model="selectedMeat">
        <option disabled value="">Valitse täyte</option>
        <option v-for="(meat, key) in meats" :key="key" v-bind:value="meat.calories">{{ meat.finnish }}</option> 
      </select>

      <label>Valitse leipä:</label>
      <select v-model="selectedBread">
        <option disabled value="">Valitse leipä</option>
       <option v-for="(bread, key) in breads" :key="key" v-bind:value="bread.calories">{{ bread.finnish }}</option> 
      </select>
      <label>Valitse kastike:</label>
      <select v-model="selectedSauce">
        <option disabled value="">Valitse kastike</option>
       <option v-for="(sauce, key) in sauces" :key="key" v-bind:value="sauce.calories">{{ sauce.finnish }}</option> 
      </select>
      <label>Valitse juusto:</label>
      <select v-model="selectedCheese">
        <option disabled value="">Valitse juusto</option>
       <option v-for="(cheese, key) in cheeses" :key="key" v-bind:value="cheese.calories">{{ cheese.finnish }}</option> 
      </select>
      <input type="submit" value="Save"/>
    </form>
  </div>
</template>

<script>
export default {
  name: "Calculator",
  data() {
    return {
      selectedBread: 0,
      selectedSauce: 0,
      selectedMeat: 0,
      selectedCheese: 0,
      calories: 0
    };
  },
  props: {
    breads: Object,
    sauces: Object,
    cheeses: Object,
    meats: Object
  },
  methods: {
    calculateCalories() {
      this.calories =
        this.selectedBread +
        this.selectedSauce +
        this.selectedMeat +
        this.selectedCheese;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
