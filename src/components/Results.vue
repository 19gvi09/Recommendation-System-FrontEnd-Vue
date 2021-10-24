<template>
  <v-row>
    <v-col>
      <v-card
        class="my-2"
        outlined
        v-for="book in books"
        :key="book.id"
        @click="$router.push({ name: 'BookPage', params: { id: book.id } })"
      >
        <div class="d-flex flex-no-wrap justify-space-between">
          <div>
            <v-card-title class="text-h5" v-text="book.title"></v-card-title>
            <v-card-subtitle v-text="book.author_fullNameAlt"></v-card-subtitle>
          </div>
          <v-avatar class="ma-3" tile>
            <v-icon x-large>mdi-book</v-icon>
          </v-avatar>
        </div>
      </v-card>
      <v-btn v-if="this.$route.name === 'Search'" text color="primary"
        >Загрузить еще</v-btn
      >
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "Results",
  props: {
    books: Array,
    hidden: Boolean,
  },
};
</script>
