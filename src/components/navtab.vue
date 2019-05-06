<template>
  <div class="Navtab">
    <div v-for="(item,index) of data " :key="index" :data="item">
      <router-link :to="item.url" class="navtab-item" tag="div" :class="{active:cur==index}">
        <i class="iconfont" :class="item.img"></i>
        <div>{{item.title}}</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navtab",
  data() {
    return {
      data: [
        {
          url: "/",
          img: "icon-yemian-copy-copy",
          title: "首页"
        },
        {
          url: "/about",
          img: "icon-quanbuchanpin",
          title: "全部商品"
        },
        {
          url: "/about",
          img: "icon-liwu",
          title: "定制有礼"
        },
        {
          url: "/about",
          img: "icon-gouwuche1",
          title: "购物车"
        },
        {
          url: "/about",
          img: "icon-ren",
          title: "个人中心"
        }
      ]
    };
  },
  props: {
    cur: Number
  }
};
</script>

<style lang="scss" scoped>
.Navtab {
  position: fixed;
  bottom: 0;
  width: 100%;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  background: #000;
  font-size: 20px;
  .navtab-item {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    color: #fff;
    height: 100px;
  }
  .iconfont {
    font-size: 40px;
  }
  .active {
    color: rgb(255, 0, 0);
  }
}
</style>