<template>
    <div class="stories-wrap">
      <div class="stories-container">
        <card
          class="card"
          :title="title"
        >
          <template v-slot:card-list>
            <ul class="card-content">
              <li v-for="(item, index) in storiesList" :key="index" :class="[item.theme]">
                <router-link :to='"/stories/" + item.id' tag='a'>
                  <span class="summary">{{item.summary}}</span>
                </router-link>
              </li>
            </ul>
          </template>
        </card>
      </div>
    </div>
</template>

<script>
import Card from '../../components/card';

export default {
  layout: 'common',
  data () {
    return {
      sidebarList: [
        {
          name: '小野店主故事',
          path: '/stories',
          active: true,
        },
      ],
      storiesList: [
        {
          id: 1001,
          theme: 'story-1',
          summary: '成都店主故事特辑'
        },
        {
          id: 1002,
          theme: 'story-2',
          summary: '转变角色，遇见更好的自己'
        },
        {
          id: 1003,
          theme: 'story-3',
          summary: '“斜杠奶爸”的创业史'
        },
        {
          id: 1004,
          theme: 'story-4',
          summary: '如何在半年内连开两家店？'
        },
        {
          id: 1005,
          theme: 'story-5',
          summary: '从 0 开始，一往无前的创业'
        },
      ],
      title: '小野店主故事',
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
  components: {
    Card,
  }
}
</script>

<style lang="scss" scoped>
.stories-wrap {
  position: relative;
  background: #fff;
  min-height: 650px;
  text-align: center;
  padding: 30px 0 0;
  width: 100%;

  .card-wrap {
    margin: 4rem .6rem 1rem;
  }

  .stories-container {
    margin: 0 auto;
    overflow: hidden;
    color: #666;
    font-size: 14px;
    text-align: left;
    .sidebar {
      float: left;
    }
    .card-content {
      background: #fafafa;
      border-radius: 6px;
      font-size: 14px;
      text-align: center;
      li {
        position: relative;
        margin: 1.8rem 0;
        &::after {
          position: absolute;
          content: '';
          width: 100%;
          left: 0;
          bottom: -1.8rem;
          border-bottom: 1px solid #c9c9c9;
        }
        &:last-child {
          &::after {
            border-bottom: none;
          }
        }
        a {
          display: block;
          width: 100%;
          height: 100%;
        }
      }
      .summary {
        visibility: hidden;
        width: 1px;
        height: 1px;
      }
      .story-1 {
        width: 16rem;
        height: 14rem;
        display: inline-block;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        background-image: url(~assets/images/stories/img-1@3x.jpg);
      }
      .story-2 {
        width: 16rem;
        height: 14rem;
        display: inline-block;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        background-image: url(~assets/images/stories/img-2@3x.jpg);
      }
      .story-3 {
        width: 16rem;
        height: 14rem;
        display: inline-block;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        background-image: url(~assets/images/stories/img-3@3x.jpg);
      }
      .story-4 {
        width: 16rem;
        height: 14rem;
        display: inline-block;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        background-image: url(~assets/images/stories/img-4@3x.jpg);
      }
      .story-5 {
        width: 16rem;
        height: 14rem;
        display: inline-block;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        background-image: url(~assets/images/stories/img-5@3x.jpg);
      }
    }
  }
}
</style>
