<script setup lang="ts">
import { ref } from 'vue'

const text = ref<string>('')

</script>

<template>
  <section>
    <q-input
      outlined
      v-model="text"
      label="Buscar personaje..."
      label-color="white"
      :input-style="{ color: '#fff' }"
      style="border: 2px solid #fff; border-radius: 5px !important; background-color: #081F32;"
    >
      <template v-slot:prepend>
        <q-icon
          name="img:icon/search.svg"
          class="cursor-pointer"
        />
      </template>
      <template v-slot:append>
        <q-icon
          name="img:icon/filter-icon.svg"
          class="cursor-pointer"
        />
      </template>
    </q-input>
  </section>
</template>


<style scoped>

</style>
