<template>
<v-app>
  <div id="app">

    <v-app-bar app flat dark dense color="blue darken-1" >
      <v-app-bar-title style = "min-width:100px;">MyPortfolio</v-app-bar-title>

      <v-tabs
        centered
        class="mr-16"
      >
        <v-tab
          v-for="[link,address] in links"
          :key="link"
          :to ="address"
        >
          {{ link }}
        </v-tab>
      </v-tabs>
    </v-app-bar>

    <v-main>
      <router-view/>
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


#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #42b983;

    &.router-link-exact-active {
      color: #2c3e50;
    }
  }
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
      ['開発記録','/DevRec'],
    ],
  }),
} 
</script>