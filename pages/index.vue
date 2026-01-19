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
  { type: "subheader", title: "DKI Jakarta" },
  { title: "Jakarta", nama: "jakarta", value: 1 },
  { type: "divider" },
  { type: "subheader", title: "Jawa Timur" },
  { title: "Surabaya", nama: "surabaya", value: 2 },
  { title: "Sidoarjo", nama: "sidoarjo", value: 3 },
  { title: "Malang", nama: "malang", value: 4 },
  { title: "Gresik", nama: "gresik", value: 5 },
  { type: "divider" },
  { type: "subheader", title: "Jawa Tengah" },
  { title: "Surakarta", nama: "surakarta", value: 6 },
  { title: "Kudus", nama: "kudus", value: 7 },
  { title: "Semarang", nama: "semarang", value: 8 },
  { title: "Demak", nama: "demak", value: 9 },
  { type: "divider" },
  { type: "subheader", title: "Jawa Barat" },
  { title: "Bogor", nama: "bogor", value: 10 },
  { title: "Bekasi", nama: "bekasi", value: 11 },
  { title: "Cirebon", nama: "cirebon", value: 12 },
  { title: "Bandung", nama: "bandung", value: 13 },
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
                <v-btn
                  color="primary"
                  variant="text"
                  :key="dlg.nama"
                  :titleue="dlg.nama"
                  block
                >
                  {{ dlg.title }}
                </v-btn>
              </v-btn-group>
            </v-card-text>
            <v-divider></v-divider>
            <v-card-actions>
              <v-btn
                class="mx-auto w-100"
                text="Tutup"
                @click="isActive.value = false"
                block
              ></v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </div>
    <v-card>
      <v-list>
        <v-list-item v-for="(itam, i) in dialogg" :key="i" :value="itam" color="success">
          <v-list-item-title v-if="itam.type === 'subheader'" class="fs-3 text-center">{{
            itam.title
          }}</v-list-item-title>
          <v-list-item-subtitle v-else-if="itam.type === 'divider'"
            ><v-divider></v-divider
          ></v-list-item-subtitle>
          <v-list-item-subtitle v-else
            >{{ itam.value }}. {{ itam.title }}</v-list-item-subtitle
          >
        </v-list-item>
      </v-list>
    </v-card>
  </div>
</template>
