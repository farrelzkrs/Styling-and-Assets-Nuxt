<script lang="ts" setup>
useSeoMeta({
  title: "Contact Page",
  description: "Ini adalah contact page",
});

const cards = [
  {
    title: "Instagram",
    href: "https://instagram.com/farrelzkrs",
    flex: 6,
    icon: "mdi-instagram",
  },
  {
    title: "WhatsApp",
    href: "https://wa.me/6285746007677",
    flex: 6,
    icon: "mdi-whatsapp",
  },
  {
    title: "Instagram",
    href: "https://github.com/farrelzkrs",
    flex: 6,
    icon: "mdi-github",
  },
];
</script>
<template>
  <h1>Contact Me</h1>
  <v-card class="mx-auto">
    <v-container fluid>
      <v-row>
        <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
          <v-card
            :href="card.href"
            target="_blank"
            append-icon="mdi-open-in-new"
            :prepend-icon="card.icon"
            :title="card.title"
          >
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>
