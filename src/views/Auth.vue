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
                  v-if="tab.input"
                  v-model="id"
                  label="Your ID"
                  :rules="[rules.required]"
                  required
                ></v-text-field>
              </v-card-text>
              <v-card-actions>
                <v-btn @click="$router.go(-1)" text>Назад</v-btn>
                <v-spacer></v-spacer>
                <v-btn @click="tab.buttonAction" text color="primary">{{
                  tab.buttonText
                }}</v-btn>
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
          input: true,
          buttonText: "Войти",
          buttonAction: this.auth,
        },
        {
          name: "Регистрация",
          input: false,
          buttonText: "Зарегистрироваться",
          buttonAction: this.register,
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
  methods: {
    auth() {
      console.log("auth");
      localStorage.id = this.id;
      this.$store.commit("setID", localStorage.id);
      this.$router.go(-1);
    },
    register() {
      console.log("register");
    },
  },
};
</script>
