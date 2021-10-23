<template>
  <v-container>
    <v-row>
      <v-col>
        <v-text-field
          v-model="input"
          label="Поиск книг"
          append-outer-icon="mdi-magnify"
          clearable
          @click:append-outer="Search"
        ></v-text-field>
      </v-col>
    </v-row>
    <results :books="result" />
  </v-container>
</template>

<script>
import Results from "../components/Results.vue";
import json from "../data/books.json";
export default {
  components: { Results },
  name: "Search",
  data() {
    return {
      input: null,
      result: json,
    };
  },
  methods: {
    Search() {
      console.log(this.input);
    },
  },
};
</script>
