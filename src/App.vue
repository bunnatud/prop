<template>
  <v-app>
    <v-app-bar app color="#6A76AB" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://www.computing.psu.ac.th/th/wp-content/uploads/2018/03/Logo-PSU-TH-01.png"
          transition="scale-transition"
          width="180"
        />

      </div>

      <v-spacer></v-spacer>

      <v-btn to="/" target="_blank" text>
        <span class="mr-2">Home</span>
      </v-btn>
      <v-btn to="/todo" target="_blank" text>
        <span class="mr-2">Assignment</span>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
