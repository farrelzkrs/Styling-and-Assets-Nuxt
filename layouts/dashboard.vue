<script lang="ts" setup>
import { ref } from 'vue'

const navbarStyle = ref<'elegant' | 'dark'>('elegant')

const toggleNavbarStyle = () => {
  navbarStyle.value = navbarStyle.value === 'elegant' ? 'dark' : 'elegant'
}

const navbar = [
  { link: "/", nama: "Home", icon: "mdi-home" },
  { link: "/esdoger", nama: "Es Doger", icon: "mdi-cup" },
  { link: "/about", nama: "About", icon: "mdi-information-outline" },
  { link: "/contact", nama: "Contact", icon: "mdi-contacts" },
];
</script>
<template>
  <div>
    <v-app>
      <header class="mb-5">
        <!-- Navbar Elegant Style -->
        <v-app-bar v-if="navbarStyle === 'elegant'" class="navbar-elegant">
          <div class="navbar-container">
            <!-- Left: Hello Button -->
            <div class="navbar-left">
              <v-btn variant="outlined" class="btn-hello">
                Hello
              </v-btn>
            </div>

            <!-- Center: Navigation Items -->
            <div class="navbar-center">
              <v-btn
                v-for="nav in navbar"
                :key="nav.nama"
                variant="text"
                :prepend-icon="nav.icon"
                :to="nav.link"
                class="btn-elegant"
              >
                {{ nav.nama }}
              </v-btn>
            </div>

            <!-- Right: Theme Switcher -->
            <div class="navbar-right">
              <v-btn
                icon
                @click="toggleNavbarStyle"
                title="Switch Navbar Style"
                class="btn-palette"
              >
                <v-icon>mdi-palette</v-icon>
              </v-btn>
            </div>
          </div>
        </v-app-bar>

        <!-- Navbar Dark Style -->
        <v-app-bar v-else class="navbar-dark">
          <div class="navbar-container">
            <!-- Left: Hello Button -->
            <div class="navbar-left">
              <v-btn variant="outlined" class="btn-hello-dark">
                Hello
              </v-btn>
            </div>

            <!-- Center: Navigation Items -->
            <div class="navbar-center">
              <v-btn
                v-for="nav in navbar"
                :key="nav.nama"
                variant="text"
                :prepend-icon="nav.icon"
                :to="nav.link"
                class="btn-dark"
              >
                {{ nav.nama }}
              </v-btn>
            </div>

            <!-- Right: Theme Switcher -->
            <div class="navbar-right">
              <v-btn
                icon
                @click="toggleNavbarStyle"
                title="Switch Navbar Style"
                class="btn-palette-dark"
              >
                <v-icon>mdi-palette</v-icon>
              </v-btn>
            </div>
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

<style scoped>
/* Navbar Container Layout */
.navbar-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  gap: 1rem;
  padding: 0 1rem;
}

.navbar-left {
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

.navbar-right {
  flex: 0 0 auto;
  display: flex;
  align-items: center;
}

/* ============ ELEGANT STYLE (White Background) ============ */
.navbar-elegant {
  background-color: #ffffff !important;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.btn-hello {
  font-family: 'Impact', 'Arial Black', sans-serif;
  font-weight: 900;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: #333 !important;
  border-color: #333 !important;
  padding: 0 1rem;
}

.btn-elegant {
  font-family: 'Impact', 'Arial Black', sans-serif;
  font-weight: 900;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: #333 !important;
  transition: all 0.3s ease;
  padding: 0 0.75rem;
}

.btn-elegant:hover {
  transform: scale(1.05);
  color: #000 !important;
}

.btn-palette {
  color: #333 !important;
  transition: all 0.3s ease;
}

.btn-palette:hover {
  transform: rotate(180deg);
}

/* ============ DARK STYLE (Black Background) ============ */
.navbar-dark {
  background-color: #1a1a1a !important;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
}

.btn-hello-dark {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-weight: 600;
  color: #ffffff !important;
  border-color: #ffffff !important;
  padding: 0 1rem;
}

.btn-dark {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-weight: 500;
  letter-spacing: 0.5px;
  color: #ffffff !important;
  transition: all 0.3s ease;
  padding: 0 0.75rem;
}

.btn-dark:hover {
  color: #64b5f6 !important;
  background-color: rgba(255, 255, 255, 0.1);
}

.btn-palette-dark {
  color: #ffffff !important;
  transition: all 0.3s ease;
}

.btn-palette-dark:hover {
  transform: rotate(180deg);
}
</style>
