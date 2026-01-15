<script lang="ts" setup>
  import 'assets/css/main.css'
</script>
<template>
  <div>
    <v-app>
      <header class="mb-5">
        <v-app-bar>
          <template v-slot:default>
            <div style="width: 100%; display: flex; justify-content: center; align-items: center;">
              <div style="display: flex; gap: 50px;">
                <v-btn variant="outlined" prepend-icon="mdi-home"> <NuxtLink to="/">Home</NuxtLink></v-btn>
                <v-btn variant="outlined" prepend-icon="mdi-cup"> <NuxtLink to="/esdoger">Es Doger</NuxtLink></v-btn>
                <v-btn variant="outlined" prepend-icon="mdi-information-outline"> <NuxtLink to="/about">About</NuxtLink></v-btn>
                <v-btn variant="outlined" prepend-icon="mdi-contacts">
                  <NuxtLink to="/contact">Contact</NuxtLink>
                </v-btn>
              </div>
            </div>
          </template>
        </v-app-bar>
      </header>
      <v-main>
        <slot />
      </v-main>
    </v-app>
  </div>
</template>
