<template>
  <v-card
    class="pa-8 mx-auto"
    width="500"
    align="center"
  >
    <p
        class="text-h5 pa-3"
    >
      Добро пожаловать на биржу
    </p>
      <v-text-field
        v-model="inputData.login"
        label="Логин"
        class="ma-2"
      />
      <v-text-field
        v-model="inputData.password"
        type="password"
        label="Пароль"
        class="ma-2"
      />
      <div
        class="pa-2"
      />
      <v-btn
        block
        @click="getInputData"
        class="amber accent-3"
      >
          Войти
      </v-btn>
  </v-card>
</template>

<script>
export default {
    name: "Login",
    data: function(){
        return{
            inputData:{
                login: null,
                password: null
            },
        }
    },
    methods: {
        getInputData(){
            alert(this.inputData.login + " " + this.inputData.password)
        }
    }
}
</script>

<style lang="scss" scoped>
.window{
    justify-content: center;
}
</style>