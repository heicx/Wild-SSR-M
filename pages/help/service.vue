<template>
    <div class="service-wrap">
      <div class="service-container">
        <sub-header :list="list"></sub-header>
        <card
          class="card"
          :title="title"
        >
          <template v-slot:card-list>
            <div class="card-content">
              <h3 class="title">如果您在选购、使用小野电子烟过程中，遇到任何问题，欢迎您通过以下方式联系我们：</h3>
              <ul class="text">
                <li>客服电话：400-028-8560</li>
                <li>工作时间：周一至周日 9：00 ~ 18：00</li>
              </ul>
              <ul class="qrcode">
                <li class="weibo">
                  <span>官方微博：@vvild 小野</span>
                </li>
                <li class="wechat">
                  <span>官方微信：vvild 小野（微信号 vvildtech）</span>
                </li>
              </ul>
            </div>
          </template>
        </card>
      </div>
    </div>
</template>

<script>
import subHeader from '../../components/subHeader.vue';
import card from '../../components/card';

export default {
  layout: 'common',
  data () {
    return {
      list: [
        {
          name: '公司介绍',
          link: '/aboutus',
        },
        {
          name: '客服中心',
          link: '/help/service',
          active: true
        }
      ],
      title: '客服中心',
    }
  },
  head () {
    return {
      title: `${this.title} - 小野官方网站`
    }
  },
  components: {
    card,
    subHeader
  }
}
</script>

<style lang="scss" scoped>
.service-wrap {
  position: relative;
  background: #fff;
  min-height: 750px;
  text-align: center;
  width: 100%;
  padding-bottom: 1rem;
  .service-container {
    margin: 0 auto;
    overflow: hidden;
    color: #666;
    font-size: .65rem;
    text-align: left;
    .sidebar {
      float: left;
    }
    .card {
      float: right;
    }
    .card-content {
      padding: 1rem;
      font-size: .65rem;
      .title {
        font-weight: bold;
        line-height: 1.5;
        padding-bottom: .65rem;
      }
      .text {
        color: #7f7f7f;
        line-height: 1.5;
      }
      .qrcode {
        padding: 1.5rem;
        overflow: hidden;
        font-size: .65rem;
        color: #7f7f7f;
      }
      .qrcode li {
        position: relative;
        margin: 0 auto 3rem;
      }
      .weibo {
        position: absolute;
        content: '';
        width: 6rem;
        height: 6rem;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        background-color: #fff;
        background-image: url(~assets/images/help/weibo-qrcode.png);
        background-image: -webkit-image-set(url(~assets/images/help/weibo-qrcode.png) 1x,url(~assets/images/help/weibo-qrcode@2x.png) 2x);
        span {
          position: absolute;
          content: '';
          text-align: center;
          left: -.5rem;
          bottom: -1.5rem;
          width: 7rem;;
        }
      }
      .wechat {
        position: absolute;
        content: '';
        width: 6rem;
        height: 6rem;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        background-color: #fff;
        background-image: url(~assets/images/help/wechat-qrcode.png);
        background-image: -webkit-image-set(url(~assets/images/help/wechat-qrcode.png) 1x,url(~assets/images/help/wechat-qrcode@2x.png) 2x);
        span {
          position: absolute;
          content: '';
          text-align: center;
          left: -3.5rem;
          bottom: -1.5rem;
          width: 14rem;
        }
      }
    }
  }
}
</style>
