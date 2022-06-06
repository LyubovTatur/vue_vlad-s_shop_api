<template>
  <div class="product_list">
    <div class="product_item" v-for="product_item in clothes">
      <img class="product_item_img" src="" alt="item image" />
      <h2 @mouseenter='testMethos()'>${{ product_item.price }}</h2>
      <h3>{{ product_item.name }}</h3>
      <div>{{ product_item.brand }}</div>
    </div>
  </div>
  {{ clothes }}
</template>

<script>
export default {
  props: {
    clothes: {
      type: Array,
      required: true,
    },
  },
  methods:{
      testMethos(){
          console.log('mlem!')
      }
  }
};
</script>
<style lang="scss">
.product_list {
  background: rgba(145, 5, 4, 0.2);
    padding:3px;
  .product_item {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    display: inline-block;
    margin: 3px;
    border: 3px solid #020816;
    width: 208px;
    height: 300px;
    h2,
    h3,
    div {
      margin: 4px 4px;
    }
    h2{
        // color: #e68ab3;
        color: #020816;
          -webkit-text-stroke-color: #cb769b;
          -webkit-text-stroke-width: .1px;

    }

    .product_item_img {
      margin: 1px;
      min-width: 200px;
      min-height: 200px;
        border: 3px solid #020816;
    }
  }
}
</style>
