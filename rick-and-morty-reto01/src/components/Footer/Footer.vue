<script setup lang="ts">
import { Colors } from '../../ enums/Colors.enums'
</script>

<template>
  <section
    style="height: 142px;"
    :style="{
      background: Colors.BLACK
    }"
  >
    <div
      class="footer-screen-page"
    />
  </section>
</template>


<style scoped lang="scss">
@import url('./Footer.scss');
</style>
