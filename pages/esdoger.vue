<script lang="ts" setup>
import Jeli from './esdoger/jeli.vue';


  useSeoMeta({
      title: "Es Doger",
      description: "Ini adalah page orang kehausan",
  })
</script>
<template>
  <div>
    <h1 style="margin-bottom: 12px; text-align: center;">Ini Es Doger - Parent</h1>
    <NuxtPage />
    <v-divider color="secondary" opacity=".7" thickness="5" variant="dashed" gradient></v-divider>
    <h1 style="margin-top: 12px; text-align: center;">Ini Pakai Topping</h1>
    <Jeli />
  </div>
</template>
