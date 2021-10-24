<template>
  <v-container>
    <v-card class="pa-6 mb-3">
      <div class="text-h4" v-text="'Новинки'"></div>
      <Results :books="newBooks" />
    </v-card>
    <v-card class="pa-6 mb-3">
      <div class="text-h4" v-text="'Общие рекомендации'"></div>
      <Results :books="allRecs" />
    </v-card>
    <v-card class="pa-6" v-if="persRecs">
      <div class="text-h4" v-text="'Персональные рекомендации'"></div>
      <Results :books="persRecs" />
    </v-card>
  </v-container>
</template>

<script>
import Results from "../components/Results.vue";
import json from "../data/books.json";
export default {
  name: "Home",
  components: { Results },
  data() {
    return {
      newBooks: json,
      allRecs: json,
      persRecs: json,
    };
  },
};
</script>
