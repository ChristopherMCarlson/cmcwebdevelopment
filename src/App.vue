<template>
  <v-app>
    <v-main>
      <v-container>
        <router-view />
        <!-- <FooterComponent /> -->
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
// import FooterComponent from "./components/FooterComponent.vue";

export default {
  components: {
    // FooterComponent,
  },
};
</script>

<style>
/* Add global styles here */
</style>
