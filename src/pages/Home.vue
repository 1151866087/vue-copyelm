<template>
  <div class="home">
    <p>hello world</p>
    <button @click="handleClick">detail</button>
    <!-- 4.使用组件 -->
    <navtab :cur="0"></navtab>
  </div>
</template>

<script>
/* 2.引入组件 */
import axios from "axios-jsonp-pro"
import Navtab from "../components/navtab"
export default {
  name: "Home",
  methods: {
    handleClick(){
      /* 传id */
      this.$router.push({path:'/about'});
      console.log(11)
    }
  },
  /* 3.注册组件 */
  components:{
    Navtab
  },
  created(){
    var url = "https://mybeautybox.widiazine.cn/app/arvato_shop_api.php?i=4";
    axios.jsonp(url).then(res=>{
      console.log(res)
    }) 
    // axios.get(url).then(res=>{
    //   console.log(res)
    // })
  }
};
</script>  

<style lang="scss" scoped>
// scoped自动隔离
.home{
  text-align: center;
  color: red;
  font-size: 30px;
}
</style>

