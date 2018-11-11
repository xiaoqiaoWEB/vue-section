<template>
 <div>
   <div class="banner-box">
      <banner :banner="banners"></banner>
    </div>  
 </div>
</template>

<script>
import banner1 from '@/assets/img/1.jpg'
import banner2 from '@/assets/img/2.jpg'
import banner3 from '@/assets/img/3.jpg'
import banner4 from '@/assets/img/4.jpg'
import banner5 from '@/assets/img/5.jpg'
import banner6 from '@/assets/img/6.jpg'

import Banner from "@/view/banner.vue";
export default {
  name: "HelloWorld",
  data() {
    return {
      banners : [banner1, banner2, banner3, banner4, banner5, banner6,banner1, banner2, banner3, banner4, banner5,]
    };
  },
  components: {
    Banner
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.banner-box{
  width: 800px;
  border: 1px solid #dedede;
  margin: 50px auto;
}
</style>

