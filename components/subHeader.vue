<template>
  <div class="sub-header-wrap">
      <router-link
        class="sub-header-item"
         v-for="(item, index) in list"
        :key="index"
        :to="item.link"
        :class="{'active': item.active}"
        tag="div"
      >
        {{item.name}}
      </router-link>
  </div>
</template>

<script>
export default {
  data () {
    return {}
  },
  props: {
    list: {
      type: Array,
      default: []
    }
  },
  computed: {},
  methods: {}
}
</script>

<style lang="scss" scoped>
.sub-header-wrap {
  padding-top: 4.5rem;
  border-bottom: 1px solid #e9ebf0;
  height: 2rem;
  line-height: 2rem;
  background: #f4f6fb;
  color: #626264;
}
.sub-header-item {
  display: inline;
  float: left;
  width: 50%;
  position: relative;
  text-align: center;
  font-size: .7rem;
  &.active {
    color: #ff0000;
    font-weight: bold;
  }
  &:after {
    position: absolute;
    content: '';
    width: 1px;
    height: 1rem;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
    background: #c3c5c9;
  }
  &:last-child:after {
    content: none;
  }
}
</style>

