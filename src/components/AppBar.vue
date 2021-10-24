<template>
  <v-container>
    <v-app-bar app color="primary" dark>
      <div>
        <v-btn @click="$router.push({ name: 'Home' })" icon x-large>
          <v-icon>mdi-home</v-icon>
        </v-btn>
        <v-btn @click="$router.push({ name: 'Search' })" icon x-large>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </div>

      <v-spacer></v-spacer>

      <div v-if="id">
        <v-btn @click="$router.push({ name: 'LK' })" icon x-large>
          <v-icon>mdi-account</v-icon>
        </v-btn>
        <v-btn @click="quit" icon x-large>
          <v-icon>mdi-logout</v-icon>
        </v-btn>
      </div>
      <v-btn v-else @click="$router.push({ name: 'Auth' })" icon x-large>
        <v-icon>mdi-login</v-icon>
      </v-btn>
    </v-app-bar>
  </v-container>
</template>

<script>
export default {
  name: "AppBar",
  data() {
    return {};
  },
  computed: {
    id() {
      return this.$store.state.id;
    },
  },
  methods: {
    quit() {
      delete localStorage.id;
      this.$store.commit("setID", localStorage.id);
      if (this.$route.name === "LK") {
        this.$router.push({ name: "Home" });
      }
    },
  },
};
</script>
