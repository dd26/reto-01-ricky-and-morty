<script setup lang="ts">
import { PropType, ref } from 'vue';


defineProps({
  favoriteFilter: {
    type: Boolean as PropType<boolean>,
    required: false,
    default: false
  }
})

const favoriteFilter = ref<boolean>(false)

</script>

<template>
  <section
    class="star-container flex flex-center q-ml-sm cursor-pointer"
    v-ripple
  >
    <q-icon
      @click="favoriteFilter = !favoriteFilter"
      :name="favoriteFilter ? 'img:icon/star_off.svg' : 'img:icon/star_on.svg'"
      size="18px"
    />
  </section>
</template>


<style scoped>

</style>
