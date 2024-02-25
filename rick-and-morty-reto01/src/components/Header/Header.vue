<script setup lang="ts">
import FilterInput from '../FilterInput.vue';
</script>

<template>
  <section
    class="header-container flex flex-center column"
  >
    <q-img
      src="home/rick-and-morty-letter.svg"
      alt="letter-rick-and-morty"
      style="width: 347px; height: 122px;"
    />

    <FilterInput
      class="q-mt-md"
      style="width: 500px"
    />

  </section>
</template>


<style scoped lang="scss">
@import url('./Header.scss');

</style>
