<script lang="ts" setup>
useSeoMeta({
  title: "About Page",
  description: "Ini adalah about page",
});
const panels = [
  {
    title: "Profile",
    content:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias illo vero iusto assumenda exercitationem corrupti, nulla fugiat voluptatum ducimus tempore nisi labore excepturi sunt praesentium fugit cupiditate sapiente quisquam! Nam.",
    isHtml: false,
  },
  {
    title: "Affiliator",
    content: `<ul>
      <li>Lorem</li>
      <li>Ipsum</li>
      <li>Dolor</li>
      <li>Sit</li>
      <li>Amet</li>
    </ul>`,
    isHtml: true,
  },
  {
    title: "Jobdesk",
    content:
      "Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias illo vero iusto assumenda exercitationem corrupti, nulla fugiat voluptatum ducimus tempore nisi labore excepturi sunt praesentium fugit cupiditate sapiente quisquam! Nam.",
    isHtml: false,
  },
  {
    title: "Address",
    content: "Entah dimana dirimu berada",
    isHtml: false,
  },
];
</script>
<style scoped>
h1,
h3 {
  font-family: "Transformer";
}
</style>
<template>
  <h1 style="margin-bottom: 12px">About Us</h1>
  <v-expansion-panels color="primary" variant="inset">
    <v-expansion-panel v-for="(panel, index) in panels" :key="index">
      <v-expansion-panel-title collapse-icon="mdi-minus" expand-icon="mdi-plus">
        <h3>{{ panel.title }}</h3>
      </v-expansion-panel-title>
      <v-expansion-panel-text v-if="!panel.isHtml">
        {{ panel.content }}
      </v-expansion-panel-text>
      <v-expansion-panel-text v-else v-html="panel.content"></v-expansion-panel-text>
    </v-expansion-panel>
  </v-expansion-panels>
</template>
