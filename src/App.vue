
<script setup>
import MyBarVue from './components/MyBar.vue';
import MyCardVue from './components/MyCard.vue';
import items from './attractions.json'
</script>

<template>
  <header>
    <MyBarVue />
  </header>

  <main>
    <h1 style="paddingLeft: 10px">Attractions</h1>
    <div className="grid-container">
      <MyCardVue v-for="item in items" v-bind="item" />
    </div>
  </main>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-column-gap: 1rem;
  grid-row-gap: 1rem;
}
@media (min-width: 576px) {
  .grid-container { grid-template-columns: repeat(1, 1fr); }
}
@media (min-width: 992px) {
  .grid-container { grid-template-columns: repeat(3, 1fr); }
}
</style>