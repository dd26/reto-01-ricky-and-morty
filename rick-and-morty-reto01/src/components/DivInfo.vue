<script setup lang="ts">

defineProps({
  title: {
    type: String,
    required: true,
  },
  value: {
    type: String,
    required: true,
  }
});

</script>

<template>
  <div class="container-info-div-episode">
    <div class="row items-center q-gutter-x-xs">
      <q-icon
        name="img:icon/info-circle 1.svg"
        size="12px"
      />
      <span
        style="font-size: 11px; font-weight:  400; color:#828282"
      >
        {{ title }}:
      </span>

    </div>

    <span
      class="montserrat-bold"
      style="font-size: 14px; color: #081F32; font-weight: 600px;"
    >
      {{ value }}
    </span>
  </div>
</template>


<style scoped lang="scss">

.container-info-div-episode {
  width: auto;
  height: 60px;
  border: 1px solid #BDBDBD;
  border-radius: 8px;
  padding: 10px;
  min-width: 163px;
}

</style>
