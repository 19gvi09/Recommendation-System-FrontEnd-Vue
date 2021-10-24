<template>
  <v-container>
    <v-row>
      <v-col>
        <v-row>
          <v-spacer></v-spacer>
          <v-btn icon :color="color" @click="favorites = !favorites">
            <v-icon x-large>mdi-star</v-icon>
          </v-btn>
        </v-row>
        <div v-if="book.title" class="text-h2 pb-6" v-text="book.title"></div>
        <div
          v-if="book.author_fullName"
          class="text-body-1"
          v-text="'Автор: ' + book.author_fullName"
        ></div>
        <div
          v-if="book.serial_name"
          class="text-body-1"
          v-text="'Серия: ' + book.serial_name"
        ></div>
        <div
          v-if="book.rubric_name"
          class="text-body-1"
          v-text="'Тематика: ' + book.rubric_name"
        ></div>
        <div
          v-if="book.language_name"
          class="text-body-1"
          v-text="'Язык издания: ' + book.language_name"
        ></div>
        <div
          v-if="book.material_name"
          class="text-body-1"
          v-text="'Тип издания: ' + book.material_name"
        ></div>
        <div
          v-if="book.year"
          class="text-body-1"
          v-text="'Год издания: ' + book.year"
        ></div>
        <div
          v-if="book.annotation"
          class="text-h4 pt-6"
          v-text="'Аннотация'"
        ></div>
        <div
          v-if="book.annotation"
          class="text-body-1 pt-1"
          v-text="book.annotation"
        ></div>
      </v-col>
    </v-row>
    <reservation :libraryAvailability="book.libraryAvailability" />
  </v-container>
</template>

<script>
import Reservation from "../components/Reservation.vue";
import json from "../data/books.json";
export default {
  components: { Reservation },
  name: "BookPage",
  data() {
    return {
      book: null,
      favorites: false,
    };
  },
  computed: {
    color() {
      return this.favorites ? "yellow" : "";
    },
  },
  methods: {
    parseBooks() {
      this.book = json.filter((e) => e.id === this.$route.params.id);
      this.book = this.book[0];
      console.log(this.book);
    },
  },
  mounted() {
    this.parseBooks();
    console.log(this.book);
  },
};
</script>
