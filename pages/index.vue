<script lang="ts" setup>
useSeoMeta({
  title: "Home Page",
  description: "Ini adalah homepage",
});
const dialog = ref("");
const chips = [
  { nama: "Label" },
  { nama: "Tags", icon: "mdi-label" },
  { nama: "Farrel Lerri", icon: "mdi-account" },
  { nama: "Game Baru", icon: "mdi-controller" },
];
const dialogg = [
  { val: "Surabaya", nama: "surabaya" },
  { val: "Jakarta", nama: "jakarta" },
  { val: "Sidoarjo", nama: "sidoarjo" },
  { val: "Gresik", nama: "gresik" },
  { val: "Malang", nama: "malang" },
  { val: "Cirebon", nama: "cirebon" },
  { val: "Demak", nama: "demak" },
  { val: "Semarang", nama: "semarang" },
  { val: "Bandung", nama: "bandung" },
];
</script>
<template>
  <div>
    <h1 style="margin-bottom: 12px">Ini Halaman Index</h1>
    <div class="text-center">
      <v-chip
        v-for="chp in chips"
        class="ma-2"
        color="primary"
        :prepend-icon="chp.icon"
        closable
        label
      >
        {{ chp.nama }}
      </v-chip>
    </div>
    <div class="pa-4 text-center">
      <v-dialog width="300px" scrollable>
        <template v-slot:activator="{ props: activatorProps }">
          <v-btn
            color="primary"
            prepend-icon="mdi-earth"
            text="Pilih Tempat Tinggalmu"
            v-bind="activatorProps"
          ></v-btn>
        </template>
        <template v-slot:default="{ isActive }">
          <v-card prepend-icon="mdi-earth" title="Pilih Tempat Tinggalmu">
            <v-divider class="mt-3"></v-divider>
            <v-card-text class="px-4" style="height: 250px">
              <v-btn-group
                v-for="dlg in dialogg"
                v-model="dialog"
                direction="vertical"
                class="w-100"
                messages="Pilih daerah tempat tinggalmu"
              >
                <v-btn color="primary" variant="text" :key="dlg.nama" :value="dlg.nama" block>
                  {{ dlg.val }}
                </v-btn>
              </v-btn-group>
            </v-card-text>
            <v-divider></v-divider>
            <v-card-actions>
              <v-btn class="mx-auto w-100" text="Tutup" @click="isActive.value = false" block></v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </div>
  </div>
</template>
