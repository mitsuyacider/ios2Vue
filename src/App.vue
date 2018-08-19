<template>
  <div id="app">
    <hello-world />
  </div>
</template>

<script>
import NativeCommunicator from '@/js/NativeCommunicator.js'
import HelloWorld from '@/components/HelloWorld'
import { mapGetters } from 'vuex'

export default {
  name: 'App',
  mounted() {
    console.log('mounted');
  },
  components: {
    HelloWorld
  },
  methods: {}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
