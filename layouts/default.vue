<style>
  @import url("~/assets/css/main.css");
</style>
<template>
  <div>
    <v-app>
      <header>
        <v-app-bar>
          <v-btn variant="outlined"> <NuxtLink to="/">Home</NuxtLink></v-btn>
          <v-btn variant="outlined"> <NuxtLink to="/esdoger">Es Doger</NuxtLink></v-btn>
          <v-btn variant="outlined"> <NuxtLink to="/about">About</NuxtLink></v-btn>
          <v-btn variant="outlined">
            <NuxtLink to="/contact">Contact</NuxtLink>
          </v-btn>
        </v-app-bar>
      </header>
      <v-main>
        <slot />
      </v-main>
    </v-app>
  </div>
</template>
