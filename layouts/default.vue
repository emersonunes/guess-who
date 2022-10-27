<template>
  <v-app>
    <v-main>
      <v-app-bar flat dark class="justify-center d-flex">
        <v-toolbar-title>Guess Who</v-toolbar-title>
      </v-app-bar>
      <v-container>
        <router-view></router-view>
      </v-container>
    </v-main>
    <v-footer
      dark
      padless
    >
      <v-card
        class="flex"
        flat
        tile
      >
        <v-card-text class="py-2 white--text text-center">
          {{ new Date().getFullYear() }} — <strong>Copyright © MD3</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout'
}
</script>
