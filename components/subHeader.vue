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
  data() {
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
  display: flex;
  padding-top: 4.2rem;
  border-bottom: 1px solid #e9ebf0;
  height: 1.8rem;
  line-height: 1.8rem;
  background: #f4f6fb;
  color: #626264;
  text-align: center;
}
.sub-header-item {
  position: relative;
  flex: 1;
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

