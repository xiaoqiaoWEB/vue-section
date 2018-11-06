<template>
  <div>
    <div class="box-alert">
      <div class="title">{{title}}</div>
      <div class="footer">
        <input type="button" :value="okValue" @click="cHandel">
        <input type="button" value="取消">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  //props: ["title", "ok-value"]
  props: {
    title: {
      type: String,
      default: '这里是标题'
    },
    okValue: {
      type: String,
      default: '确定'
    },
    appShow: {
      type: Boolean,
      default: false
    },
    isRed: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    cHandel() {
      console.log('点击了OK按钮');
      this.$emit("input",false);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box-alert {
  width:200px;
  height: 200px;
  border: 2px solid rgba(255, 122, 165, 0.5);
  position: relative;
}
.box-alert .title{
  text-align: center;
  line-height: 30px;
}
.box-alert .footer{
  position: absolute;
  right: 0;
  bottom: 10px;
}
</style>
