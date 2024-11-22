<template>
  <v-app>
    <v-app-bar>
      <v-toolbar-title>My Portfolio</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text to="/" exact>Home</v-btn>
      <v-btn text to="/about">About</v-btn>
      <v-btn text to="/projects">Projects</v-btn>
      <v-btn text to="/contact">Contact</v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <router-view />
        <FooterComponent />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import FooterComponent from "./components/FooterComponent.vue";

export default {
  components: {
    FooterComponent,
  },
};
</script>

<style>
/* Add global styles here */
</style>
