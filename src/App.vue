<template>
<v-app :style="{ background: $vuetify.theme.themes.light.background }">
  <div id="app">

    <v-app-bar flat dark dense color="blue darken-1" >
      <v-app-bar-title style = "min-width:120px;">MyPortfolio</v-app-bar-title>
    </v-app-bar>
    
    <v-toolbar flat dark dense color="blue darken-1">
      <v-tabs>
        <v-tab
          v-for="[link,address] in links"
          :key="link"
          :to ="address"
        >
          {{ link }}
        </v-tab>
      </v-tabs>
    </v-toolbar>

    <v-main>
      <v-container>
       <router-view/>
      </v-container>
    </v-main>

  </div>
</v-app>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

</style>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data: () => ({
    links: [
      ['ホーム','/'],
      ['成果物','/Product'],
      ['開発記録','/DevelopmentRecord'],
    ],
  }),
} 
</script>