<template>
  <div class="content">
    <ProductList :clothes="clothes" />
  </div>
</template>

<script>
import ProductList from "@/components/ProductList";
export default {
  components: {
    ProductList,
  },
  data() {
    return {
      clothes: {},
    };
  },
  methods: {
    async getClothes() {
      fetch("https://vlad-cloth-api.herokuapp.com/api/cloth/")
        .then((response) => response.json())
        .then((data) => (this.clothes = data));
    },
  },
  mounted() {
    this.getClothes();
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: url("https://images5.alphacoders.com/116/1168050.png") no-repeat center
    center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #020816;
  font-family: "Press Start 2P", cursive;
  color: #cb769b;
}
.content {
  width: 649px;
  margin: 10px auto;
}
</style>
