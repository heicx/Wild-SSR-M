<template>
  <div id="app" class="app-wrap">
    <app-header></app-header>
    <nuxt />
	</div>
</template>

<script>
import appHeader from '../components/header.vue';

export default {
  data() {
    return {}
  },
  computed: {
  },
  created() {
  },
  components: {
    appHeader,
  },
}
</script>

<style src='../assets/style/scss/common.scss' lang='scss'></style>
<style lang='scss' scoped>
.app-wrap {
  width: 100%;
  margin: 0 auto;
  max-width: 540px;
}
</style>
