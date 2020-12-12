<template>
  <div id="app" class="app-wrap">
    <app-header></app-header>
    <nuxt />
    <app-footer></app-footer>
	</div>
</template>

<script>
import appHeader from '../components/header.vue';
import appFooter from '../components/footer.vue';

export default {
  data () {
    return {}
  },
  computed: {
  },
  created () {
  },
  components: {
    appHeader,
    appFooter,
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
