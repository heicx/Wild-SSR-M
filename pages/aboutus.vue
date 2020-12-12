<template>
<div class="aboutus-wrap">
  <sub-header :list="list"></sub-header>
  <card
    class="card"
    :title="title"
  >
    <template v-slot:card-list>
      <div class="card-content">
        <div class="introduce">
          <p>vvild 小野由顶尖团队打造，研发团队由来自华为、锤子科技等多名资深技术专家组成，具备硬件领域最前沿的技术实力。vvild 小野对产品设置了极端严格的检测标准：符合欧盟电子烟 CE-RoHS 认证、符合国家香料香精《烟用香精标准》、符合多项国家食品安全标准。检测结果有据可查，让消费者的卫生安全得到可靠保障。其次，vvild 小野是行业内唯一有潮流明星做背书的电子烟品牌。邀请到拥有 CLOT 潮牌主理人、演员、歌手、rap star、AJ1 白丝绸联名设计师等多重身份的流量大 V - 陈冠希，作为 vvild 小野的特邀创意官。有他在，vvild 小野产品必定为潮流硬通货。另外，中国初代网红、脱口秀鼻祖、流量大 V、带货主播、拥有电子产品设计美学家之称的罗永浩老师是 vvild 小野品牌的创始人之一，并全程参与把控产品的设计、外观等细节，在罗老师的监督下，小野的产品颜值自然逆天。</p>
        </div>
        <h4 class="subtitle">我们的使命和愿景</h4>
        <div class="introduce">
          <p>企业使命：让生活更健康、更自由</p>
          <p>企业愿景：做深受消费者喜爱的品牌</p>
          <p>企业价值观：以用户为中心，以结果为导向</p>
          <p>品牌关键：新贵品牌、有态度也有度、不随波逐流、阳光朝气、高品质高格调</p>
          <p>品牌 slogan：不要那么野，小野一下就好</p>
        </div>
      </div>
    </template>
  </card>
</div>
</template>

<script>
import subHeader from '../components/subHeader.vue';
import card from '../components/card';

export default {
  layout: 'common',
  data() {
    return {
      title: '公司介绍',
      list: [
        {
          name: '公司介绍',
          link: '/aboutus',
          active: true
        },
        {
          name: '客服中心',
          link: '/help/service',
        }
        // {
        //   name: '加入我们',
        //   link: '/joinus'
        // }
      ]
    }
  },
  head () {
    return {
      title: `${this.title} - 小野官方网站`
    }
  },
  mounted() {
  },
  methods: {
  },
  components: {
    subHeader,
    card
  },
}
</script>

<style lang="scss" scoped>
.aboutus-wrap {
  background: #fff;
  min-height: 750px;
  text-align: center;
  padding-bottom: 1rem;
  .card-content {
    color: #7f7f7f;
    font-size: .65rem;
    text-align: left;
    padding: 1rem;
    .introduce {
      line-height: 1.6;
    }
    .subtitle {
      font-weight: bolder;
      margin: 2rem 0 .5rem;
    }
  }
}
</style>
