<script setup lang="ts">
import { ref } from 'vue'

import Tab from 'src/components/Tab/Tab.vue'
import ItemCharacter from 'src/components/ItemCharacter/ItemCharacter.vue'
import CardProfile from 'src/components/CardProfile/CardProfile.vue'

const tabList = [
  { label: 'All', value: 'all' },
  { label: 'Unknown', value: 'unknown' },
  { label: 'Female', value: 'female' },
  { label: 'Male', value: 'male' },
  { label: 'Genderless', value: 'genderless' }
]

const favoriteFilter = ref<boolean>(false)

const characterClicked = ref<any>({})
const isShowCharacter = ref<boolean>(false)

const characters = ref<any[]>([
  {
    id: 1,
    name: 'Rick Sanchez',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline: true
  },
  {
    id: 2,
    name: 'Morty Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline: false
  },
  {
    id: 3,
    name: 'Summer Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline:  true
  },
  {
    id: 4,
    name: 'Beth Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline: false
  },
  {
    id: 5,
    name: 'Beth Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline: false
  },
  {
    id: 6,
    name: 'Beth Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline: false
  },
  {
    id: 7,
    name: 'Beth Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline: false
  },
  {
    id: 8,
    name: 'Beth Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Earth',
    firstSeen: 'Never Ricking Morty',
    isOnline: true
  },
  {
    id: 9,
    name: 'Beth Smith',
    status: 'Alive',
    species: 'Human',
    lastLocation: 'Story Train',
    firstSeen: 'Never Ricking Morty',
    isOnline: false
  }
])

const handleClickCard = (character: any) => {
  characterClicked.value = character
  isShowCharacter.value = true

}
</script>

<template>
  <section class="full-width">
    <Tab
      :initialTab="'all'"
      :tabs="tabList"
    />

    <section
      class="row q-mt-xl"
      :style="{
        padding: $q.screen.lt.sm ? '0 10px' : $q.screen.lt.md ? '0 20px' : $q.screen.lt.lg ? '0 100px' : '0 200px'
      }"
    >

      <div class="row items-center">
        <div>Mostrar favoritos: </div>
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
      </div>

      <section
        class="row justify-center q-mt-md col-12"
      >
        <div
          class="col-4 row q-pa-md"
          v-for="character in characters"
          :key="character"
        >
          <ItemCharacter
            class="col-12"
            @click="handleClickCard(character)"
            v-bind="character"
            :isFavorite="favoriteFilter"
          />
        </div>
      </section>

    </section>

    <q-dialog
      v-model="isShowCharacter"
      persistent
    >
      <CardProfile
        :character="characterClicked"
      />
    </q-dialog>
  </section>
</template>


<style scoped lang="scss">
@import url('./Content.scss');
</style>
