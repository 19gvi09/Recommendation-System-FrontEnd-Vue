<template>
  <v-container>
    <v-row>
      <v-col>
        <v-tabs v-model="tab">
          <v-tab v-for="tab in tabs" :key="tab.name">{{ tab.name }}</v-tab>
        </v-tabs>
        <v-tabs-items v-model="tab">
          <v-tab-item v-for="tab in tabs" :key="tab.name">
            <v-card>
              <v-card-text>
                <v-text-field
                  v-model="id"
                  label="Your ID"
                  :rules="[rules.required]"
                  required
                ></v-text-field>
              </v-card-text>
              <v-card-actions>
                <v-btn @click="$router.go(-1)" text>Назад</v-btn>
                <v-spacer></v-spacer>
                <v-btn text color="primary">{{ tab.buttonText }}</v-btn>
              </v-card-actions>
            </v-card>
          </v-tab-item>
        </v-tabs-items>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Auth",
  data() {
    return {
      tab: null,
      tabs: [
        {
          name: "Вход",
          buttonText: "Войти",
        },
        {
          name: "Регистрация",
          buttonText: "Зарегистрироваться",
        },
      ],
      id: "",
      rules: {
        required: (value) => {
          return !!value || "Необходимо заполнить это поле";
        },
      },
    };
  },
};
</script>
