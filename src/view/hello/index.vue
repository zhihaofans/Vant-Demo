<template>
  <div class="hello">
    <van-cell-group>
      <van-cell
        is-link
        v-for="item in list.items"
        v-bind:key="item"
        v-bind:title="item.title"
        v-bind:value="item.value"
        v-bind:to="item.to"
      />
    </van-cell-group>
  </div>
</template>

<script>
import { Cell, CellGroup, Toast } from "vant";

export default {
  components: {
    [Cell.name]: Cell,
    [CellGroup.name]: CellGroup,
  },

  data() {
    return {
      list: {
        items: [
          { title: "商品", value: "点击跳转", to: "goods" },
          { title: "购物车", value: "点击跳转", to: "cart" },
          { title: "用户", value: "点击跳转", to: "user" },
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
