<script setup lang="ts">
import { PropType } from 'vue';

import DivInfo from '../DivInfo.vue';
import DivEpisode from '../DivEpisode.vue';
import ItemCharacter from '../ItemCharacter/ItemCharacter.vue';

// props
const props = defineProps({
  character: {
    type: Object as PropType<any>,
    required: true,
  },
});


</script>

<template>
  <q-card
    class="card-container-profile-character"
  >
    <section class="relative-position">
      <q-img
        src="portrait-character.svg"
        class="full-height img-character"
        alt="character"
        style="width: 100%; height: 220px;"
      />
      <q-icon
        name="img:icon/closet.svg"
        class="icon-closet cursor-pointer"
        size="30px"
        v-ripple
        v-close-popup
      />
    </section>

    <section
      class="section-img-container"
    >
      <section
        class="row justify-center "
      >
        <div
          class="profile-img-container"
        >
          <img
            src="character.svg"
            alt="profile"
            class="profile-img"
          >
        </div>
        <div class="col-12 flex flex-center">
          <div class="start-container">
            <q-icon
              :name="!character.isFavorite ? 'img:icon/star_on.svg' : 'img:icon/star_off.svg'"
              class="icon-star"
              size="18px"
            />
          </div>
        </div>
      </section>
      <section class="flex flex-center column container-info-img">
          <span
            class="text-uppercase"
            style="color: #4F4F4F; font-size: 12px;"
          >
            {{ character.status }}
          </span>

          <span
            style="color: #081F32; font-size: 20px;"
          >
            {{ character.name }}
          </span>

          <span
            class="text-uppercase q-pt-xs"
            style="color: #4F4F4F; font-size: 12px;"
          >
            {{ character.species }}
          </span>
      </section>
    </section>

    <section class="q-pt-lg bg-white container-additional-info text-black full-width q-px-md q-pb-xl">
      <span
        style="color:#4F4F4F; font-size: 20px; font-weight: 600"
      >
        Información
      </span>

      <section class="row justify-between q-pt-md">
        <DivInfo
          class="col-4"
          title="Género:"
          value="Male"
        />
        <DivInfo
          class="col-4"
          title="Origin:"
          value="Earth (C-112)"
        />
        <DivInfo
          class="col-4"
          title="Type:"
          value="Unknown"
        />
      </section>

      <hr class="q-mt-lg hr-style">

      <section class="row justify-center q-pt-md">
        <span
          class="col-12 q-pb-md"
          style="color:#4F4F4F; font-size: 20px; font-weight: 600"
        >
          Episodios
        </span>
        <div
          class="col-4 q-pa-xs transform-div-episode"
          v-for="n in 6"
          :key="n"
        >
          <DivEpisode
            class="col-12"
            title="Pilot"
            value="S01E01"
            date="December 2, 2013"
          />
        </div>
      </section>

      <hr class="q-mt-lg hr-style">

      <section class="q-mt-lg row">
        <span
          class="q-pb-md col-12"
          style="color:#4F4F4F; font-size: 20px; font-weight: 600"
        >
          Personajes interesantes
        </span>

        <ItemCharacter
          class="col-6 q-pr-xs"
          v-if="character"
          v-bind="character"
        />
        <ItemCharacter
          class="col-6 q-pl-xs"
          v-if="character"
          v-bind="character"
        />
      </section>

      <section class="row justify-end q-pt-lg">
        <q-btn
          class="q-mt-md montserrat-bold"
          color="primary"
          label="Compartir personaje"
          to="/home"
          no-caps
          rounded
          unelevated
        />
      </section>
    </section>

  </q-card>
</template>

<style scoped lang="scss">
@import url("./CardProfile.scss");
</style>
