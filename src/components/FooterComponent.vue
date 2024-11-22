<template>
    <v-footer app color="primary" dark>
      <v-container class="text-center white--text">
        © {{ currentYear }} Christopher Carlson
      </v-container>
    </v-footer>
  </template>
  
  <script>
  export default {
    data: () => ({
      
    }),
    computed: {
        currentYear() {
            return new Date().getFullYear();
        }
    },
  };
  </script>
  
  <style scoped>
  </style>
  