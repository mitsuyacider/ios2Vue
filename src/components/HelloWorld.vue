<template>
  <div class="hello">
    <img src="../assets/logo.png">
    <!-- <router-view/> -->
    <p>message from native:{{getMessageFromNative}}</p>
    <p>message to native:{{message}}</p>
  </div>
</template>

<script>
import NativeCommunicator from '@/js/NativeCommunicator.js'
import { mapGetters } from 'vuex'

export default {
  name: 'HelloWorld',
  computed: {
    ...mapGetters([
      'getMessageFromNative'
    ])
  },
  data() {
    return {
      message:""
    }
  },
  watch: {
    getMessageFromNative: function (oldVal, newVal) {
      if (oldVal != newVal) {
        this.message = new Date().toString()
        NativeCommunicator.helloNative(this.message)
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
