<script setup lang="ts">
import { PropType } from 'vue';

import FavoriteBtn from '../FavoriteBtn.vue';

// props
defineProps({
  name: {
    type: String as PropType<string>,
    required: true
  },
  status: {
    type: String as PropType<string>,
    required: true
  },
  species: {
    type: String as PropType<string>,
    required: true
  },
  lastLocation: {
    type: String as PropType<string>,
    required: true
  },
  firstSeen: {
    type: String as PropType<string>,
    required: true
  },
  isOnline: {
    type: Boolean as PropType<boolean>,
    required: true
  },
  isFavorite: {
    type: Boolean as PropType<boolean>,
    required: false,
    default: false
  }
})

</script>

<template>
  <q-card class="card-container" flat bordered>
    <q-card-section horizontal>
      <section
        class="relative-position"
      >
        <img
          src="character.svg"
          class="full-height img-character"
          alt="character"
          style="width: 100px;"
        />
        <FavoriteBtn
          class="favorite-btn"
          :favoriteFilter="isFavorite"
        />
      </section>
      <q-card-section>
        <section class="column">
          <div class="row items-center q-gutter-x-sm">
            <q-badge
              rounded
              :color="isOnline ? 'positive' : 'negative'"
            />
            <div
              style="font-size: 10px; weight: 400; color: #4F4F4F"
            >
              {{ status }} - {{ species }}
            </div>
          </div>
        </section>
        <div class="q-pt-sm" style="font-size: 16px">
          {{ name }}
        </div>

        <section
          class="column q-pt-sm"
        >
          <span class="q-mb-xs" style="font-size: 12px; color: #4F4F4F">
            Last known location:
          </span>
          <span style="font-size: 12px;">
            {{ lastLocation }}
          </span>
        </section>

        <section
          class="column q-pt-sm"
        >
          <span class="q-mb-xs" style="font-size: 12px; color: #4F4F4F">
            First seen in:
          </span>
          <span style="font-size: 12px;">
            {{ firstSeen }}
          </span>
        </section>
      </q-card-section>
    </q-card-section>
  </q-card>
</template>


<style scoped lang="scss">
@import url('./ItemCharacter.scss');
</style>
