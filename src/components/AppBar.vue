<template>
  <v-container>
    <v-app-bar app color="primary" dark>
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

      <v-spacer></v-spacer>

      <v-btn v-if="auth" @click="$router.push('lk')" icon x-large>
        <v-icon>mdi-account</v-icon>
      </v-btn>
      <v-btn v-else @click="$router.push('auth')" icon x-large>
        <v-icon>mdi-login</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="primary--text text--accent-4"
        >
          <v-list-item @click="$router.push('/')">
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Главная</v-list-item-title>
          </v-list-item>
          <v-list-item @click="$router.push('search')">
            <v-list-item-icon>
              <v-icon>mdi-magnify</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Поиск</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-container>
</template>

<script>
export default {
  name: "AppBar",
  props: {
    auth: Boolean,
  },
  data() {
    return {
      drawer: false,
      group: null,
    };
  },
};
</script>
