<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="./assets/pokemon-logo.png"
          transition="scale-transition"
          width="120"
        />

      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://pokeapi.co/docs/v2"
        target="_blank"
        text
      >
        <span class="mr-2">Pokedex API</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <Index/>
    </v-main>
  </v-app>
</template>

<script>
import Index from './components/home/Index';

export default {
  name: 'App',

  components: {
    Index,
  },

  data: () => ({
    //
  }),
};
</script>
