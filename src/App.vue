<template>
  <v-app>
      <v-card
      color="grey lighten-4"
      flat
      tile
    >
      <v-toolbar dense>
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-toolbar-title>Vuetify</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn color="success" outlined>Ingresar
          <v-icon right>how_to_reg</v-icon>
        </v-btn>
        <v-btn color="error" outlined>Salir
          <v-icon right>directions_walk</v-icon>
        </v-btn>
      </v-toolbar>
    </v-card>

    <v-navigation-drawer app v-model="drawer" dark temporary>
      <v-layout mt-4 column align-center>
        <v-flex>
          <v-avatar>
            <v-img src="https://media-exp1.licdn.com/dms/image/C4E03AQFFzIl3pZ48UQ/profile-displayphoto-shrink_200_200/0?e=1584576000&v=beta&t=tP1LFmtC_zNRk0_g5yRTWjAp0KxBER3hkamiDW_DtFU">
            </v-img>
          </v-avatar>
        </v-flex>
        <v-flex>
          <p class="white--text mt-3 headline">Bill Jherson Ttimpo</p>
        </v-flex>
      </v-layout>
    </v-navigation-drawer>

    <v-content>
      <router-view></router-view><!-- Aquí va todo el contenido dinámico -->
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: "App",
  data: () => ({
    drawer: false,
  }),
};
</script>
