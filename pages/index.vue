<script lang="ts" setup>
useSeoMeta({
  title: "Home Page",
  description: "Ini adalah homepage",
});
definePageMeta({
  layout: "dashboard",
});
const chips = [
  {nama: 'Label'},
  {nama: 'Tags', icon: 'mdi-label'},
  {nama: 'Farrel Lerri', icon: 'mdi-account'},
  {nama: 'Game Baru', icon: 'mdi-controller'},
]
</script>
<template>
  <div>
    <h1 style="margin-bottom: 12px;">Ini Halaman Index</h1>
      <div class="text-center">
        <v-chip v-for="chp in chips" class="ma-2" :prepend-icon="chp.icon" closable label> {{ chp.nama }} </v-chip>
      </div>
  </div>
</template>
