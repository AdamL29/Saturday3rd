<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <CompBinding/>
  </div>
</template>

<script>
import CompBinding from '@/components/CompBinding.vue';

export default {
  name: 'App',
    components: {
      CompBinding,
    },
      methods: {
        darkMode() {
          console.log("Dark mode toggled in app.vue");
        }
      },
      mounted () {
        this.$root.$on(`toggleDark`, this.darkMode);
      },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
