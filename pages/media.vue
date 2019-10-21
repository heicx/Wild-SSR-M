<template>
<div class="media-wrap">
  <div class="media-list">
    <img class="banner" src="../assets/images/media/media-img-1@3x.jpg" alt="强效减害、雾量澎湃、多种口味、真烟口感、严防漏油、长效续航。一击即入魂，烟油采用有机尼古丁盐，强效解瘾，直逼真烟每种口味的尼古丁含量为 3% 或 5%，与真烟相当体验酷似传统香烟，让你找到熟悉的感觉" />
  </div>
  <div class="media-content-wrap">
    <ul class="media-content">
      <li class="media-1" @click="playVideo('media-1')">
        <img src="../assets/images/media/media-cover-1.jpg" alt="">
      </li>
      <li class="media-2" @click="playVideo('media-2')">
        <img src="../assets/images/media/media-cover-2.jpg" alt="">
      </li>
      <li class="media-3" @click="playVideo('media-3')">
        <img src="../assets/images/media/media-cover-3.jpg" alt="">
      </li>
      <li class="media-4" @click="playVideo('media-4')">
        <img src="../assets/images/media/media-cover-4.jpg" alt="">
      </li>
      <li class="media-5" @click="playVideo('media-5')">
        <img src="../assets/images/media/media-cover-5.jpg" alt="">
      </li>
      <li class="media-6" @click="playVideo('media-6')">
        <img src="../assets/images/media/media-cover-6.jpg" alt="">
      </li>
      <li class="media-7" @click="playVideo('media-7')">
        <img src="../assets/images/media/media-cover-7.jpg" alt="">
      </li>
      <li class="media-8" @click="playVideo('media-8')">
        <img src="../assets/images/media/media-cover-8.jpg" alt="">
      </li>
      <li class="media-9" @click="playVideo('media-9')">
        <img src="../assets/images/media/media-cover-9.jpg" alt="">
      </li>
    </ul>
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
        'media-1': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-60.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMTk3NzQ4OA=='
        },
        'media-2': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-15D.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMTk2NjY0MA=='
        },
        'media-3': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-15F.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMjAxNTEyMA=='
        },
        'media-4': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-5B.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMTk0NjQ1Mg=='
        },
        'media-5': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-5A.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMTk0NDM0OA=='
        },
        'media-6': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-5C.mov',
          youkuUrl: 'hhttp://player.youku.com/embed/XNDMzMTk0OTk3Mg=='
        },
        'media-7': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-5D.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMTk1MDg4MA=='
        },
        'media-8': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-30.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMTk2OTg2NA=='
        },
        'media-9': {
          cdnUrl: 'https://static.vvild.cn/resources/media/vvild-15B.mov',
          youkuUrl: 'http://player.youku.com/embed/XNDMzMjAxMzg5Mg=='
        }
      },
      videoShowStatus: false
    }
  },
  head () {
    return {
      title: '视频中心 - 小野官方网站'
    }
  },
  methods: {
    playVideo (name) {
      // 1566878399000
      const timestamp = (new Date()).valueOf();

      if (timestamp > 1566878399000) {
        this.isCDN = true;
        this.videoUrl = this.videos[name].cdnUrl || this.videos['media-4'].cdnUrl;
      } else {
        this.isCDN = false;
        this.videoUrl = this.videos[name].youkuUrl || this.videos['media-4'].cdnUrl;
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
.media-wrap .media-list {
  font-size: 0;
  img {
    width: 100%;
  }
}

.media-wrap .media-list .banner {
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

.media-content-wrap {
  background: #05070a;
}
.media-content {
  margin: 0 1rem;
  padding-top: .5rem;
  overflow: hidden;
  li {
    img {
      width: 100%;
      height: 100%;
    }
    float: left;
    width: 48.5%;
    height: 100%;
    margin-bottom: .35rem;
    cursor: pointer;
    &:nth-child(2n) {
      margin-left: .4rem;
    }
  }
}

</style>
