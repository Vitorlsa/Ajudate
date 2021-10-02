<template>
  <LandingPage v-if="started == null" @startApp="StartedApp($event)" />
  <Questions v-if="started" />
</template>

<script>
import LandingPage from './components/LandingPage.vue'
import Questions from './components/Questions.vue'

export default {
  name: 'App',
  components: { LandingPage, Questions },
  data() {
    return{
      started: null
    }
  },
  methods: {
    StartedApp(started) {
      this.started = started
    }
  }
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
  height: 80vh;
  width: 100%;
}
</style>
