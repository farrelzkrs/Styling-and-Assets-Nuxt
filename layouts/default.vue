<script lang="ts" setup>
import "assets/css/main.css";

const navbar = [
  { link: "/", nama: "Home", icon: "mdi-home" },
  { link: "/esdoger", nama: "Es Doger", icon: "mdi-cup" },
  { link: "/about", nama: "About", icon: "mdi-information-outline" },
  { link: "/contact", nama: "Contact", icon: "mdi-contacts" },
];
</script>
<style scoped>
header {
  font-family: "Transformer";
}
</style>
<template>
  <div>
    <v-app>
      <header class="mb-5">
        <v-app-bar>
          <v-row>
            <v-col
              style="display: flex; justify-content: center"
              v-for="nav in navbar"
              :key="nav.nama"
              cols="3"
            >
              <v-btn variant="outlined" :prepend-icon="nav.icon" :to="nav.link">
                {{ nav.nama }}
              </v-btn>
            </v-col>
          </v-row>
        </v-app-bar>
      </header>
      <v-main>
        <slot />
        <footer style="text-align: center; margin-top: 20px">&copy; Farrel 2023</footer>
      </v-main>
    </v-app>
  </div>
</template>
