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
    content: `<div class="ms-10 my-4"><ul>
      <li>Lorem</li>
      <li>Ipsum</li>
      <li>Dolor</li>
      <li>Sit</li>
      <li>Amet</li>
    </ul></div>`,

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
    content: `<iframe class="w-100 m-4" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3957.496022809602!2d112.77720677476083!3d-7.298032792709562!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2dd7fbd148aaa1d1%3A0xd976a53a2b123c!2sPT.%20Greatsoft%20Solusi%20Indonesia!5e0!3m2!1sen!2sid!4v1768789050298!5m2!1sen!2sid" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>`,
    isHtml: true,
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
  <v-expansion-panels color="primary" variant="inset" multiple>
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
