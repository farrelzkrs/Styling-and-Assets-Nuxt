<script lang="ts" setup>
useSeoMeta({
  title: "Home Page",
  description: "Ini adalah homepage",
});
definePageMeta({
  layout: "dashboard",
});
const changeLayout = () => {
  setPageLayout("default");
};
</script>
<template>
  <div>
    <h1 style="font-family: Transformer">Ini Halaman Index</h1>
    <h3 style="font-family: Transformer">TRANSFORMERS</h3>
    <button @click="changeLayout">Change Layout</button>
  </div>
</template>
