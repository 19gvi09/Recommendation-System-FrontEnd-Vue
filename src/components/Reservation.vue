<template>
  <v-row>
    <v-col>
      <div class="text-h4" v-text="'Бронирование книги'"></div>
      <v-card
        v-for="item in libraryAvailability"
        :key="item.libraryId"
        outlined
      >
        <v-card-title>Название библиотеки</v-card-title>
        <v-card-subtitle>Адрес библиотеки</v-card-subtitle>
        <v-card-subtitle>Номер библиотеки</v-card-subtitle>
        <v-card-subtitle
          v-text="'Свободных книг: ' + item.freeCount"
        ></v-card-subtitle>
        <v-card-actions>
          <v-btn text>Забронировать</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "Reservation",
  props: {
    libraryAvailability: Array,
  },
};
</script>
