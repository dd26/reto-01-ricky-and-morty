<script setup lang="ts">

defineProps({
  title: {
    type: String,
    required: true,
  },
  value: {
    type: String,
    required: true,
  },
  date: {
    type: String,
    required: true,
  }
});

</script>

<template>
  <div class="container-info-div column">
    <span
      style="font-size: 11px; font-weight:  400; color:#828282"
    >
      {{ title }}:
    </span>

    <span
      class="montserrat-bold"
      style="font-size: 14px; color: #081F32; font-weight: 600px;"
    >
      {{ value }}
    </span>

    <span
      style="font-size: 11px; color: #081F32; font-weight: 600px;"
    >
      {{ date }}
    </span>
  </div>
</template>


<style scoped lang="scss">

.container-info-div {
  width: auto;
  height: 80px;
  border: 1px solid #BDBDBD;
  border-radius: 8px;
  padding: 10px;
}

</style>
