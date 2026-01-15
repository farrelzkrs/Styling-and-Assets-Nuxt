<script lang="ts" setup>
    import {shallowRef} from 'vue'

    const sheet = shallowRef(false)
</script>
<template>
    <div class="pa-8 text-center">
    <v-btn class="ma-auto" size="x-large" text="Klik" @click="sheet = !sheet"></v-btn>
    <v-bottom-sheet v-model="sheet">
        <v-card class="text-center" height="200">
            <v-card-text>
                <v-btn variant="text" @click="sheet = !sheet">Tutup</v-btn>
                <br>
                <br>
                <div>Ini topping biasa dari es doger</div>
            </v-card-text>
        </v-card>
    </v-bottom-sheet>
    </div>
</template>