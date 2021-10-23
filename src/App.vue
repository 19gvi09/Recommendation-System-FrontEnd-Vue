<template>
  <v-app>
    <app-bar :auth="auth" />

    <v-main>
      <v-row>
        <v-spacer></v-spacer>
        <v-col>
          <router-view />
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
    </v-main>
  </v-app>
</template>

<script>
import AppBar from "./components/AppBar.vue";
export default {
  components: { AppBar },
  name: "App",
  data() {
    return {
      auth: true,
    };
  },
};
</script>
