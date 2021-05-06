<template>
  <div class="main">
    <div class="main-grid">
      <van-grid>
        <van-grid-item
          v-for="item in grid.items"
          v-bind:key="item"
          v-bind:icon="item.icon"
          v-bind:text="item.text"
          v-bind:to="item.to"
        />
      </van-grid>
    </div>
  </div>
</template>

<script>
import { Grid, GridItem, Toast } from "vant";

export default {
  components: {
    [Grid.name]: Grid,
    [GridItem.name]: GridItem,
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
  },
};
</script>
