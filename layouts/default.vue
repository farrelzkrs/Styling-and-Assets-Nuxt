<script lang="ts" setup>
import { ref } from "vue";

const navbarStyle = ref<"terang" | "hytam">("terang");

const toggleNavbarStyle = () => {
  navbarStyle.value = navbarStyle.value === "terang" ? "hytam" : "terang";
};
</script>
<style scoped>
.navbar-icon {
  flex: 0 0 auto;
  display: flex;
  align-items: center;
}
.navbar-center {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.5rem;
}
.navbar-terang {
  background-color: #ffffff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
.btn-hello-terang {
  font-family: "Transformer";
  font-weight: 900;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: #333;
  border-color: #333;
  padding: 0 1rem;
}
.btn-terang {
  font-family: "Transformer";
  font-weight: 900;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: #333;
  transition: all 0.3s ease;
  padding: 0 0.75rem;
}
.btn-terang:hover {
  transform: scale(1.05);
  color: #000;
}
.btn-palette-terang {
  color: #333;
  transition: all 0.3s ease;
}
.navbar-hytam {
  background-color: #1a1a1a;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
}
.btn-hello-hytam {
  font-family: sans-serif;
  font-weight: 600;
  color: #ffffff;
  border-color: #ffffff;
  padding: 0 1rem;
}
.btn-hytam {
  font-family: sans-serif;
  font-weight: 500;
  letter-spacing: 0.5px;
  color: #ffffff;
  transition: all 0.3s ease;
  padding: 0 0.75rem;
}
.btn-hytam:hover {
  color: #f1f664;
  background-color: rgba(255, 255, 255, 0.1);
}
.btn-palette-hytam {
  color: #ffffff;
  transition: all 0.3s ease;
}
</style>
<template>
  <div>
    <v-app>
      <header class="mb-5">
        <v-app-bar
          v-if="navbarStyle === 'terang'"
          class="navbar-terang d-flex align-items-center w-100 justify-content-between"
        >
          <div class="navbar-icon">
            <v-btn to="/" class="btn-hello-terang" text="Latihan" />
          </div>
          <div class="navbar-center">
            <v-btn to="/" prepend-icon="mdi-home" class="btn-terang" text="Home" />
            <v-btn
              to="/esdoger"
              prepend-icon="mdi-cup"
              class="btn-terang"
              text="Es Dogwer"
            />
            <v-btn
              to="/about"
              prepend-icon="mdi-information-outline"
              class="btn-terang"
              text="About"
            />
            <v-btn
              to="/contact"
              prepend-icon="mdi-contacts"
              class="btn-terang"
              text="Contact"
            />
          </div>
          <div class="navbar-icon">
            <v-btn
              icon="mdi-palette"
              @click="toggleNavbarStyle"
              title="Switch Navbar Style"
              class="btn-palette-terang"
            />
          </div>
        </v-app-bar>

        <v-app-bar v-else class="navbar-hytam">
          <div class="navbar-icon">
            <v-btn to="/" class="btn-hytam" text="Latihan" />
          </div>
          <div class="navbar-center">
            <v-btn to="/" prepend-icon="mdi-home" class="btn-hytam" text="Home" />
            <v-btn
              to="/esdoger"
              prepend-icon="mdi-cup"
              class="btn-hytam"
              text="Es Dogwer"
            />
            <v-btn
              to="/about"
              prepend-icon="mdi-information-outline"
              class="btn-hytam"
              text="About"
            />
            <v-btn
              to="/contact"
              prepend-icon="mdi-contacts"
              class="btn-hytam"
              text="Contact"
            />
          </div>
          <div class="navbar-icon">
            <v-btn
              icon="mdi-palette-outline"
              @click="toggleNavbarStyle"
              title="Switch Navbar Style"
              class="btn-palette-hytam"
            />
          </div>
        </v-app-bar>
      </header>
      <v-main>
        <slot />
        <footer style="text-align: center; margin-top: 20px">&copy; Farrel 2023</footer>
      </v-main>
    </v-app>
  </div>
</template>
