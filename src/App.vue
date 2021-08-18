<template>
  <v-app>
    <v-app-bar
      dark
      >
      <v-tabs
          align-with-title>
          <v-tab
            to="/"
          >
          Tab1
          </v-tab>
          <v-tab
            to="/charts"
          >
          Графики
          </v-tab>
          <v-tab
            to='/about'
            >Котировки</v-tab>
      </v-tabs>
    </v-app-bar>
    <body>
      <v-main
        class="px-16 py-8"
      >
      <router-view></router-view>
      </v-main>
    </body>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
body, html {
  padding: 0;
  margin: 0;
  width: 100%;
  min-height: 100%;
}
body{
  background-color: #EEEEEE;
}
</style>
