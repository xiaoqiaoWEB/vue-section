<template>
    <div class="banner-container">
        <div class="banner-top">
             <ul :style="{width: bigUlWidth}" ref="bigImg">
                <li v-for="(item,index) in banner" :key="index">
                    <img :src="item" alt="">
                </li>
            </ul>
        </div>
        <div class="banner-list">
            <ul :style="{width: samllUlWidth}" ref="samllImg">
                <li v-for="(item,index) in banner" :key="index" :class="{active: index == current}" @click="changeIndex(index)">
                    <img :src="item" alt="">
                </li>
            </ul>
        </div>
        <a href="javascript:;" class="banner-btn-prv banner-btn" @click="changeBanerPrv(1)">上一个</a>
        <a href="javascript:;" class="banner-btn-next banner-btn" @click="changeBanerNext(1)">下一个</a>
    </div>
</template>
<script>
export default {
  props: ["banner"],
  data() {
    return {
      samllUlWidth: "",
      bigUlWidth: "",
      current: 0,
      active: 0,
      step: 0
    };
  },
  methods: {
    getSamllUlWidth() {
      this.samllUlWidth = this.banner.length * 120 + "px";
    },
    getBigUlWidth() {
      this.bigUlWidth = this.banner.length * 460 + "px";
    },
    changeBanerNext(v) {
      this.current = this.current + v;
      if (this.current >= this.banner.length) {
        this.current = 0;
        this.$refs.bigImg.style.left = 0;
        this.step = 0;
        this.$refs.samllImg.style.left = 0;
      } else {
        this.$refs.bigImg.style.left = -460 * this.current + "px";
        if (this.current % 3 === 0) {
          this.step = this.step + 1;
          this.$refs.samllImg.style.left = -360 * this.step + "px";
        }
      }
    },
    changeBanerPrv(v) {
      this.current = this.current - v;
      if (this.current < 0) {
        this.current = 0;
        return;
      }
      console.log(this.current);
      this.$refs.bigImg.style.left = -460 * this.current + "px";
      if (this.current % 3 === 0) {
        console.log(this.step);
        this.step = this.step - 1;
        this.$refs.samllImg.style.left = -360 * this.step + "px";
      }
    },
    changeIndex(index) {
      if (index == this.current) {
        return;
      }
      if (index > this.current) {
        this.current = index;
        this.$refs.bigImg.style.left = -460 * this.current + "px";
        if (this.current % 3 === 0) {
          this.step = this.step + 1;
          this.$refs.samllImg.style.left = -360 * this.step + "px";
        }
      }
      if (index < this.current) {
        this.current = index;
        this.$refs.bigImg.style.left = -460 * this.current + "px";
        if (this.current % 3 === 0) {
          if (this.current) {
            console.log("A");
            this.step = this.step - 1;
            this.$refs.samllImg.style.left = -360 * this.step + "px";
          }
        }
      }
    }
  },
  created() {
    this.getSamllUlWidth();
    this.getBigUlWidth();
  }
};
</script>
<style lang="less" scoped>
* {
  padding: 0;
  margin: 0;
}
li {
  list-style: none;
}
@w : 100px;
@w2: 460px;
.banner-container {
  position: relative;
  .banner-top {
    width: @w2;
    height: @w2;
    margin: 0 auto;
    overflow: hidden;
    position: relative;
    ul {
      height: @w2;
      clear: both;
      position: absolute;
      left: 0;
      top: 0;
      transition: 0.5s;
      &::after {
        content: "";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
        position: absolute;
        left: 0;
        top: 0;
      }
    }
    li {
      width: @w2;
      height: @w2;
      background: #efefef;
      text-align: center;
      line-height: @w2;
      float: left;
    }
    img {
      display: inline-block;
      max-width: @w2;
      vertical-align: middle;
    }
  }
  .banner-list {
    width: 460px;
    margin: 0 auto;
    overflow: hidden;
    position: relative;
    height: 120px;
    ul {
      height: @w;
      clear: both;
      position: absolute;
      left: 0;
      top: 0;
      transition: 1s all;
      &::after {
        content: "";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
        position: absolute;
        left: 0;
        top: 0;
      }
      li {
        float: left;
        width: @w;
        height: @w;
        padding-right: 20px;
        &.active {
          img {
            border: 2px solid red;
          }
        }
      }
    }
    img {
      display: block;
      width: 96px;
      height: 96px;
    }
  }
  .banner-btn {
    display: block;
    width: 35px;
    height: 70px;
    background: red;
    position: absolute;
    bottom: 15px;
  }
  .banner-btn.banner-btn-next {
    right: 0;
  }
}
</style>


