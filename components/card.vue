<template>
  <div class="card-wrap">
    <div class="card-title">{{title}}</div>
    <slot name='card-list'></slot>
  </div>
</template>

<script>
export default {
	data() {
    return {
    }
  },
  props: {
    title: String
  },
  computed: {
  },
  methods: {
  }
}
</script>

<style lang="scss" scoped>
.card-wrap {
  margin: 1rem 1rem 0;
  border: 1px solid #dcdcdc;
  border-radius: 6px;
  .card-title {
    font-size: .7rem;
    font-weight: bold;
    color: #7e7e7e;
    text-align: left;
    padding-left: 1rem;
    box-shadow: 0 3px 8px -6px rgba(0,0,0,.1);
    border-bottom: 1px solid #dcdcdc;
    border-radius: 6px 6px 0 0;
    background: #f3f3f3;
    background: linear-gradient(#fff, #fbfbfb);
    line-height: 1.7rem;
    height: 1.7rem;
    box-sizing: border-box;
  }
  .card .card-list {
    overflow: hidden;
    padding: 1rem;
  }
}
</style>

