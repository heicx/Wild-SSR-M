<template>
<div class="home-wrap">
  <div class="home-list">
    <div class="item-wrap">
      <a href="https://xiaoyeyanju.m.tmall.com" target="_blank"></a>
      <img src="../assets/images/home/home-img-1@3x.jpg" />
    </div>
    <img src="../assets/images/home/home-img-2@3x.png" />
    <img src="../assets/images/home/home-img-3@3x.jpg" />
    <img src="../assets/images/home/home-img-4@3x.jpg" />
    <img src="../assets/images/home/home-img-5@3x.jpg" />
    <img src="../assets/images/home/home-img-6@3x.png" />
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
.home-wrap .home-list {
  font-size: 0;
  img {
    width: 100%;
  }
}

.home-wrap .home-list .item-wrap {
  position: relative;
  img {
    padding-top: 4rem;
  }
  a {
    position: absolute;
    content: '';
    cursor: pointer;
    width: 4.7rem;
    height: 1.6rem;
    left: 49%;
    bottom: 7%;
    transform: translateX(-50%);
  }
}
</style>
