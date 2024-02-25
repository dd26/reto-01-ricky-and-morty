<script setup lang="ts">
import { Colors } from '../../ enums/Colors.enums'
</script>

<template>
  <q-page
    class="flex flex-center"
    :style="{
      background: Colors.BLACK
    }"
  >
    <div class="home-screen-page" />

    <section
      class="home-screen-content text-white"
    >
      <img
        src="home/suazo-logo.svg"
        alt="logo-suazo-home"
      >
      <img
        src="home/rick-and-morty-letter.svg"
        alt="letter-rick-and-morty-home"
      >

      <div
        style="font-size: 36px"
      >
        Bienvenido a Rick and Morty
      </div>

      <p class="q-mt-md text-center">
        En esta prueba, evaluaremos su capacidad para construir la aplicación mediante el análisis de <br> código y la reproducción del siguiente diseño.
      </p>

      <q-btn
        class="q-mt-md montserrat-bold"
        color="primary"
        label="Continuar"
        to="/home"
        no-caps
        rounded
        unelevated
      />
    </section>
  </q-page>
</template>

<style lang="scss">
  @import './WelcomePage.scss'
</style>

