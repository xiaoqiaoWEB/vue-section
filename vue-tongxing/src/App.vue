<template>
  <div id="app">
    <h2 :style="{background: isRed ? 'red' : ''}">改变我的颜色</h2>
    <alert title="这是第一个" ok-value="改变颜色" @change="fnfn"></alert>
    <alert title="这是第二个" ok-value="AAAAA" @clear="fnfn"></alert>
  </div>
</template>

<script>
import Alert from './components/alert.vue'

export default {
  name: 'app',
  data() {
    return {
      isRed: false
    }
  },
  components: {
    Alert
  },
  methods: {
    fnfn(v) {
      this.isRed = v;
      console.log(this.isRed)
    }
  }
}
</script>

<style>

</style>
