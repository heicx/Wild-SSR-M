<template>
<div class="entityshop-wrap">
  <div class="entityshop-list">
    <img src="../assets/images/entityshop/entityshop-img-1@3x.jpg" />
    <img src="../assets/images/entityshop/entityshop-img-2@3x.jpg" />
    <img src="../assets/images/entityshop/entityshop-img-3@3x.jpg" />
    <img src="../assets/images/entityshop/entityshop-img-4@3x.jpg" />
    <img src="../assets/images/entityshop/entityshop-img-5@3x.jpg" />
    <img src="../assets/images/entityshop/entityshop-img-6@3x.jpg" />
    <img src="../assets/images/entityshop/entityshop-img-7@3x.jpg" />
    <img src="../assets/images/entityshop/entityshop-img-8@3x.jpg" />
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
.entityshop-wrap .entityshop-list {
  font-size: 0;
  img {
    width: 100%;
    &:first-child {
      padding-top: 4rem;
    }
  }
}
</style>
