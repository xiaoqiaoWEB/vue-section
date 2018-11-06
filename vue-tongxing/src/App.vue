<template>
  <div id="app">
    <h2 :style="{background: isRed ? 'red' : ''}">改变我的颜色</h2>
    <input type="button" value="buttonA" @click="isShow">
    <input type="button" value="buttonB" @click="isShowB">
    <!-- <alert title="这是第一个" ok-value="改变颜色" @change="fnfn"></alert> -->
    <alert 
      title="这是第二个" 
      ok-value="AAAAA" 
      v-show="show"
      :app-show.sync="show"
      :isRed.sync="isRed"
    >
    </alert>
    <alertB 
      v-show="showB"
      v-model="showB"
    ></alertB>

    <!-- 兄弟组件通信  event bus -->
    <headera></headera>
  </div>
</template>

<script>
import Alert from './components/alert.vue'
import AlertB from './components/alertB.vue'
import Headera from './components/headera.vue'

export default {
  name: 'app',
  data() {
    return {
      isRed: false,
      show: false,
      showB : false
    }
  },
  components: {
    Alert,
    AlertB,
    Headera
  },
  methods: {
    fnfn() {
      this.isRed = true;
    },
    isShow() {
      this.show = true;
    },
    isShowB() {
      this.showB = true;
    }
  }
}
</script>

<style>

</style>
