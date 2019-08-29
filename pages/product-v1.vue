<template>
<div class="product-v1-wrap">
  <div class="product-v1-list">
    <img class="v1-banner" src="../assets/images/product-v1/product-v1-img-1@3x.jpg" alt="强效减害、雾量澎湃、多种口味、真烟口感、严防漏油、长效续航。一击即入魂，烟油采用有机尼古丁盐，强效解瘾，直逼真烟每种口味的尼古丁含量为 3% 或 5%，与真烟相当体验酷似传统香烟，让你找到熟悉的感觉" />
    <img src="../assets/images/product-v1/product-v1-img-2@3x.jpg" alt="口感细腻，观感澎湃。新一代蜂窝陶瓷雾化器，充分雾化烟油，带来绵柔口感，电容感应器精准感应气压变化，带来畅快的吸入体验，6.5W 大功率雾化输出，只需轻抿一口，即可感受澎湃雾量" />
    <img src="../assets/images/product-v1/product-v1-img-3@3x.jpg" @click="playVideo()" />
    <img src="../assets/images/product-v1/product-v1-img-4@3x.jpg" alt="你熟悉的口味，逐一呈现。原味烤烟，冰爽薄荷，热带芒果，绿豆冰沙，清甜荔枝，能量牛，冰甜西柚，蜂蜜绿茶" />
    <img src="../assets/images/product-v1/product-v1-img-4-1@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-5@3x.jpg" alt="严防死守，拒绝漏油。油气分离设计，三重硅胶密封，冷凝槽独立防漏技术，五合一强力防漏，更大程度降低漏油风险" />
    <img src="../assets/images/product-v1/product-v1-img-6@3x.jpg" alt="充电一次，享受一天，350mAh 锂电池，Type-C 充电口，面对四种常见问题，均有安全保护机制，续航更持久，使用更安全" />
    <img src="../assets/images/product-v1/product-v1-img-7@3x.jpg" alt="vvild 小野雾化电子烟 V0 已经过严格的检测工序，符合欧盟电子烟设备要求 CE-RoHS 认证，符合国家标准家用和类似用途电器安全要求，符合国家香料香精《烟用香精标准》，符合国家食品安全标准 “急性毒性试验”，符合国家食品安全标准的 “食品添加剂中重金属试验”，符合国家食品安全标准 “食品中邻苯二甲酸酯的测定”，符合国家食品安全标准 “食品微生物学检验 菌落总数测定”，符合国家食品安全标准 “食品微生物学检验 霉菌和酵母计数”，符合国家食品安全标准 “食品卫生微生物学检验 大肠菌群测定”，符合国家食品安全标准 “食品中总砷及无机砷试验”" />
    <img src="../assets/images/product-v1/product-v1-img-8@3x.jpg" alt="未成年人禁用提醒，深圳小野科技坚持遵守国家市场监督管理总局、国家烟草专卖局发布的《关于禁止向未成年人出售电子烟的通告》，不会向未成年人出售电子烟产品。特别提醒：电子烟属于尼古丁制品，未成年人禁止使用，非吸烟者请勿尝试。孕妇及哺乳期妇女、心血管及呼吸道相关疾病患者禁止使用；请根据自身情况合理使用，若出现不适反应，请立即停止使用；请遵循国家法律法规，请勿在公共场合及明确标明禁止吸烟的场所使用电子烟及相关产品。" />
    <img src="../assets/images/product-v1/product-v1-img-9@3x.jpg" alt="拿起即吸，比 ”傻瓜“ 更 ”傻瓜“ 的操作，无需点火、无需熄灭、无明火、无烟灰，不必注油，一秒换弹，即插即用，拿起即吸，使用更便捷，用后更干净" />
    <img src="../assets/images/product-v1/product-v1-img-10@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-11@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-12@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-13@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-14@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-15@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-16@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-17@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-18@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-19@3x.jpg" />
    <img src="../assets/images/product-v1/product-v1-img-20@3x.jpg" />
  </div>
  <div class="video-wrap" :class="{'active': videoShowStatus}">
    <div class="video-content">
      <video
        v-if="isCDN && videoShowStatus"
        :src="videoUrl"
        controls
        ref="videoEle"
        poster="https://static.vvild.cn/resources/img/cover.png"
      ></video>
      <iframe v-if="!isCDN" width='100%' :src='videoUrl' frameborder='0 allowfullscreen'></iframe>
    </div>
    <div class="btn-close" @click="closeVideo()"></div>
    <div class="video-cover"></div>
  </div>
</div>
</template>

<script>
export default {
  layout: 'common',
  data() {
    return {
      isCDN: false,
      videoUrl: '',
      videos: {
        cdnUrl: 'https://static.vvild.cn/resources/media/vvild-60.mov',
        youkuUrl: 'http://player.youku.com/embed/XNDI4NDIyMDYzMg=='
      },
      videoShowStatus: false
    }
  },
  head () {
    return {
      title: '雾化电子烟 V1 - 小野官方网站'
    }
  },
  mounted() {
  },
  methods: {
    playVideo () {
      // 1566878399000
      const timestamp = (new Date()).valueOf();

      if (timestamp > 1566878399000) {
        this.isCDN = true;
        this.videoUrl = this.videos.cdnUrl;
      } else {
        this.isCDN = false;
        this.videoUrl = this.videos.youkuUrl;
      }

      setTimeout(_ => {
        this.$refs.videoEle.play();
      });
      
      this.videoShowStatus = !this.videoShowStatus;
    },
    closeVideo () {
      this.videoUrl = '';
      this.videoShowStatus = !this.videoShowStatus;
    },
  },
  components: {
  },
}
</script>

<style lang="scss" scoped>
.product-v1-wrap .product-v1-list {
  font-size: 0;
  img {
    width: 100%;
  }
}

.product-v1-wrap .product-v1-list .v1-banner {
  padding-top: 2.6rem;
}

.video-wrap {
  position: fixed;
  opacity: 0;
  transition: all .3s ease-out;
  z-index: -1;
  &.active {
    opacity: 1;
    z-index: 50;
  }
  .video-content {
    position: fixed;
    width: 90%;
    height: 95%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 4px;
    z-index: 60;
    iframe {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
  }
  .video-cover {
    background: #000;
    opacity: .8;
    position: fixed;
    width: 100%;
    top: 0;
    height: 100%;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 35;
  }
  .btn-close {
    position: fixed;
    top: 50px;
    right: 20px;
    width: 1.2rem;
    height: 1.2rem;
    z-index: 60;
    cursor: pointer;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    background-image: url(~assets/images/common/close_btn@2x.png);
    background-image: -webkit-image-set(url(~assets/images/common/close_btn.png) 1x,url(~assets/images/common/close_btn@2x.png) 2x);
  }
  video {
    position: absolute;
    width: 100%;
    top: 48%;
    transform: translateY(-50%);
  }
}
</style>
