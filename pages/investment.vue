<template>
<div class="investment-wrap">
  <div class="investment-list">
    <img src="../assets/images/investment/investment-img-1@3x.jpg" />
    <img src="../assets/images/investment/investment-img-2@3x.jpg" />
    <img src="../assets/images/investment/investment-img-3@3x.jpg" />
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
.investment-wrap .investment-list {
  font-size: 0;
  img {
    width: 100%;
    &:first-child {
      padding-top: 4rem;
    }
  }
}
</style>
