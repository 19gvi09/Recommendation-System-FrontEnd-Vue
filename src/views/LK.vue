<template>
  <v-container>
    <v-tabs v-model="tab" centered>
      <v-tab v-for="item in items" :key="item.tab">{{ item.tab }}</v-tab>
    </v-tabs>
    <v-tabs-items v-model="tab">
      <v-tab-item v-for="item in items" :key="item.tab">
        <v-card flat>
          <Results :hidden="item.reservationHidden" :books="item.books" />
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </v-container>
</template>

<script>
import Results from "../components/Results.vue";
import json from "../data/books.json";
export default {
  name: "LK",
  components: { Results },
  data() {
    return {
      tab: null,
      items: [
        { tab: "Мои заказы", books: json, reservationHidden: true },
        { tab: "Избранное", books: json, reservationHidden: false },
        { tab: "История", books: json, reservationHidden: false },
      ],
    };
  },
};
</script>
