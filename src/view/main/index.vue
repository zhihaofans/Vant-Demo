<template>
  <div class="main">
    <van-nav-bar title="首页" />
    <div class="main-grid">
      <van-grid>
        <van-grid-item
          v-for="item in grid.items"
          v-bind:key="item.key"
          v-bind:icon="item.icon"
          v-bind:text="item.text"
          v-bind:to="item.to"
          @click="loading"
        />
      </van-grid>
    </div>
  </div>
</template>

<script>
import { Grid, GridItem, Toast, NavBar } from "vant";

export default {
  components: {
    [Grid.name]: Grid,
    [GridItem.name]: GridItem,
    [NavBar.name]: NavBar,
  },

  data() {
    return {
      grid: {
        items: [
          { icon: "gem-o", text: "商品", to: "goods" },
          { icon: "cart-o", text: "购物车", to: "cart" },
          { icon: "contact", text: "会员中心", to: "user" },
        ],
      },
    };
  },

  methods: {
    sorry() {
      Toast("暂无后续逻辑~");
    },
    loading() {
      Toast.loading({
        message: "加载中...",
        forbidClick: true,
        duration: 500,
      });
    },
  },
};
</script>
