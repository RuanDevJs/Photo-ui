<template>
  <div id="app">
    <Header @update:activeComponent="activeComponent = $event" />
    <keep-alive>
      <component :is="activeComponent" />
    </keep-alive>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
    Header: () => import("./components/Header.vue"),
    Home: () => import("./components/Home.vue"),
    Login: () => import("./components/Login.vue")
  },
  data(){
    return {
      activeComponent: 'Login'
    }
  },
  methods: {
    handleActiveComponent(e){
      console.log(e)
    }
  }
}
</script>

<style>
body,h1,h2,h3,ul,li,a {
  margin: 0;
  padding: 0;
}

body {
  font-family: Poppins, sans-serif;
  color: #1f1f1f;
}

ul ,li {
  list-style: none;
}

#app {
  max-width: 100vw;
  height: 100vh;
}

</style>
