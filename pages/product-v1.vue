<template>
<div class="product-v1-wrap">
  <div class="product-v1-list">
    <!-- <img class="v1-banner" src="../assets/images/product-v1/product-v1-img-1@3x.jpg" alt="强效减害、雾量澎湃、多种口味、真烟口感、严防漏油、长效续航。一击即入魂，烟油采用有机尼古丁盐，强效解瘾，直逼真烟每种口味的尼古丁含量为 3% 或 5%，与真烟相当体验酷似传统香烟，让你找到熟悉的感觉" />
    <img src="../assets/images/product-v1/product-v1-img-2@3x.jpg" alt="口感细腻，观感澎湃。新一代蜂窝陶瓷雾化器，充分雾化烟油，带来绵柔口感，电容感应器精准感应气压变化，带来畅快的吸入体验，6.5W 大功率雾化输出，只需轻抿一口，即可感受澎湃雾量" /> -->
    <img class="video-banner" src="../assets/images/product-v1/product-v1-img-0@3x.jpg" @click="playVideo()" />
    <router-link to="/entityshop">
      <img src="../assets/images/product-v1/home-img-1@3x.jpg" />
    </router-link>
    <router-link to="/praises">
      <img src="../assets/images/product-v1/home-img-2@3x.jpg" />
    </router-link>
    <router-link to="/stories">
      <img src="../assets/images/product-v1/home-img-3@3x.jpg" />
    </router-link>
    <img src="../assets/images/product-v1/home-img-4@3x.jpg" />
    <client-only>
      <div class="swiper-wraper">
        <swiper class="swiper" :options="swiperOption">
          <swiper-slide>
            <img src="../assets/images/product-v1/home-img-yandan-1@3x.jpg" />
          </swiper-slide>
          <swiper-slide>
            <img src="../assets/images/product-v1/home-img-yandan-2@3x.jpg" />
          </swiper-slide>
          <swiper-slide>
            <img src="../assets/images/product-v1/home-img-yandan-3@3x.jpg" />
          </swiper-slide>
          <swiper-slide>
            <img src="../assets/images/product-v1/home-img-yandan-4@3x.jpg" />
          </swiper-slide>
          <swiper-slide>
            <img src="../assets/images/product-v1/home-img-yandan-5@3x.jpg" />
          </swiper-slide>
          <swiper-slide>
            <img src="../assets/images/product-v1/home-img-yandan-6@3x.jpg" />
          </swiper-slide>
        </swiper>
      </div>
    </client-only>
    <img src="../assets/images/product-v1/home-img-5@3x.jpg" />
    <img src="../assets/images/product-v1/home-img-6@3x.jpg" />
    <img src="../assets/images/product-v1/home-img-7@3x.jpg" />
    <img src="../assets/images/product-v1/home-img-8@3x.jpg" />
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

<style src='../assets/style/scss/swiper.scss' lang='scss'></style>
<style lang="scss" scoped>
.product-v1-wrap .product-v1-list {
  font-size: 0;
  img {
    width: 100%;
  }
}

.product-v1-wrap .product-v1-list .video-banner {
  margin-top: 4rem;
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

.swiper-wraper {
  padding: 0 1.5rem;
  background: #fff;
}
</style>
