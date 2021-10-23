<template>
  <v-container>
    <v-tabs v-model="tab" centered>
      <v-tab v-for="item in items" :key="item.tab">{{ item.tab }}</v-tab>
    </v-tabs>
    <v-tabs-items v-model="tab">
      <v-tab-item v-for="item in items" :key="item.tab">
        <v-card flat>
          <v-card-text>{{ item.content }}</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </v-container>
</template>

<script>
export default {
  name: "LK",
  data() {
    return {
      tab: null,
      items: [
        { tab: "Мои заказы", content: "Мои заказы" },
        { tab: "Избранное", content: "Избранное" },
        { tab: "История", content: "История" },
      ],
    };
  },
};
</script>
