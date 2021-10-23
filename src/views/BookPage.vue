<template>
  <v-container>
    <v-row>
      <v-col>
        <div v-if="book.title" class="text-h2 pb-6" v-text="book.title"></div>
        <div v-if="book.author_fullName" class="text-body-1" v-text="'Автор: ' + book.author_fullName"></div>
        <div v-if="book.serial_name" class="text-body-1" v-text="'Серия: ' + book.serial_name"></div>
        <div v-if="book.rubric_name" class="text-body-1" v-text="'Тематика: ' + book.rubric_name"></div>
        <div v-if="book.language_name" class="text-body-1" v-text="'Язык издания: ' + book.language_name"></div>
        <div v-if="book.material_name" class="text-body-1" v-text="'Тип издания: ' + book.material_name"></div>
        <div v-if="book.year" class="text-body-1" v-text="'Год издания: ' + book.year"></div>
        <div v-if="book.annotation" class="text-h4 pt-6" v-text="'Аннотация'"></div>
        <div v-if="book.annotation" class="text-body-1 pt-1" v-text="book.annotation"></div>
      </v-col>
    </v-row>
    <reservation />
  </v-container>
</template>

<script>
import Reservation from '../components/Reservation.vue';
export default {
  components: { Reservation },
  name: "BookPage",
  props: {
    book: Object,
  },
};
</script>
