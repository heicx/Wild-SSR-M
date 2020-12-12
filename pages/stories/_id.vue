<template>
    <div class="service-wrap">
      <div class="service-container">
        <side-bar
          class="sidebar"
          :title="'小野店主故事'"
          :supportList="sidebarList"
        ></side-bar>
        <card
          class="card"
          :title="title"
          :width="984"
        >
          <template v-slot:card-list>
            <div class="card-content">
              <ul>
                <li
                  v-for="(item, index) in stories.detail"
                  :key="index"
                  class="stories-item"
                >
                  <template v-if="item.indexOf('IMG_') > -1 || item.indexOf('IMG_SUB_TITLE_') > -1">
                    <template v-if="item.indexOf('IMG_') > -1">
                      <img :src="item.split('IMG_')[1]" alt="">
                    </template>
                    <template v-if="item.indexOf('IMG_SUB_TITLE_') > -1">
                      <span class="sub-title">
                        {{item.split('IMG_SUB_TITLE_')[1]}}
                      </span>
                    </template>
                  </template>
                  
                  <template v-else>
                    {{item}}
                  </template>
                </li>
              </ul>
            </div>
          </template>
        </card>
      </div>
    </div>
</template>

<script>
import Card from '../../components/card';
import STORIES from '../../static/stories.js';

export default {
  layout: 'common',
  data () {
    return {
      sidebarList: [
        {
          name: '小野店主故事',
          path: '/stories'
        },
      ],
      title: '',
    }
  },
  head () {
    return {
      title: `${this.title} - 小野官方网站`
    }
  },
  methods: {
    openMore (item, status) {
      item.status = !status;
    }
  },
  computed: {
    stories () {
      let title = '';
      let detail = '';
      const { id } = this.$route.params;

      for (let item of STORIES.list) {
        if (item.id == id) {
          title = item.title;
          this.title = title;
          detail = item.detail;
          break;
        }
      }

      return {
        title,
        detail
      }
    }
  },
  components: {
    Card,
  }
}
</script>

<style lang="scss" scoped>
.service-wrap {
  position: relative;
  background: #fff;
  min-height: 650px;
  text-align: center;
  padding: 20px 0 0;
  width: 100%;

  .card-wrap {
    margin: 4rem .6rem 1rem;
  }

  .service-container {
    margin: 0 auto;
    overflow: hidden;
    color: #666;
    text-align: left;
    .card-content {
      background: #fafafa;
      border-radius: 6px;
      padding: 1rem 0;
      .stories-item {
        font-size: 14px;
        line-height: 1.8;
        word-break: break-all;
        text-align: left;
        color: #666;
        margin-top: .5rem;
        padding: 0 1rem;
        word-break: break-word;
        img {
          display: block;
          margin: .8rem auto;
          width: 100%;
        }
        .sub-title {
          display: block;
          font-size: 12px;
          margin-top: -1rem;
          text-align: center;
        }
        &:first-child {
          margin-top: 0;
        }
      }
    }
  }
}
</style>
