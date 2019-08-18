<template>
<div class="product-wrap">
  <div class="product-list">
    <div class="item-wrap">
      <a href="https://xiaoyeyanju.m.tmall.com" target="_blank"></a>
      <img src="../assets/images/product/product-img-1@3x.jpg" />
    </div>
    <img src="../assets/images/product/product-img-2@3x.jpg" />
    <img src="../assets/images/product/product-img-3@3x.jpg" />
    <img src="../assets/images/product/product-img-4@3x.jpg" />
    <img src="../assets/images/product/product-img-5@3x.jpg" />
    <img src="../assets/images/product/product-img-6@3x.jpg" />
    <img src="../assets/images/product/product-img-7@3x.jpg" />
    <img src="../assets/images/product/product-img-8@3x.jpg" />
    <img src="../assets/images/product/product-img-9@3x.jpg" />
  </div>
</div>
</template>

<script>
export default {
  layout: 'common',
  data() {
    return {
    }
  },
  mounted() {
  },
  methods: {
  },
  components: {
  },
}
</script>

<style lang="scss" scoped>
.product-wrap .product-list {
  font-size: 0;
  img {
    width: 100%;
  }
}

.product-wrap .product-list .item-wrap {
  position: relative;
  padding-top: 4rem;
  a {
    position: absolute;
    content: '';
    cursor: pointer;
    width: 4.7rem;
    height: 1.6rem;
    left: 49%;
    bottom: 6.8%;
    transform: translateX(-50%);
  }
}
</style>
