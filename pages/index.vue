<template>
<div class="home-wrap">
  <div class="home-list">
    <div class="item-wrap">
      <a href="https://xiaoyeyanju.m.tmall.com" target="_blank"></a>
      <img src="../assets/images/home/home-img-1@3x.jpg" alt="vvild 小野雾化电子烟 V0，“不要那么野，小野一下就好”，替代传统香烟的利器，无异味、无烟灰、无明火，雾量澎湃、口感细腻、强力防漏油……这也许是你替烟的最佳选择" />
    </div>
    <img src="../assets/images/home/home-img-2@3x.png" alt="强效减害、雾量澎湃、多种口味、真烟口感、严防漏油、长效续航"/>
    <img src="../assets/images/home/home-img-3@3x.jpg" alt="去除了上百种你看不到的危害，烟油成分包含丙二醇、植物甘油、尼古丁盐、香料。消灭了传统香烟中大量因燃烧产生的包括焦油和一氧化碳在内的上百种有害、有毒物质" />
    <img src="../assets/images/home/home-img-4@3x.jpg" alt="也去除了许多你看得到的危害，小野电子烟在减少身体伤害的同时，也避免了香烟带来的口臭、牙黄等问题" />
    <img src="../assets/images/home/home-img-5@3x.jpg" alt="vvild 小野雾化电子烟 V0 已经过严格的检测工序，符合欧盟电子烟设备要求 CE-RoHS 认证，符合国家标准家用和类似用途电器安全要求，符合国家香料香精《烟用香精标准》，符合国家食品安全标准 “急性毒性试验”，符合国家食品安全标准的 “食品添加剂中重金属试验”，符合国家食品安全标准 “食品中邻苯二甲酸酯的测定”，符合国家食品安全标准 “食品微生物学检验 菌落总数测定”，符合国家食品安全标准 “食品微生物学检验 霉菌和酵母计数”，符合国家食品安全标准 “食品卫生微生物学检验 大肠菌群测定”，符合国家食品安全标准 “食品中总砷及无机砷试验”" />
    <img src="../assets/images/home/home-img-6@3x.png" alt="未成年人禁用提醒，成都小野未来科技坚持遵守国家市场监督管理总局、国家烟草专卖局发布的《关于禁止向未成年人出售电子烟的通告》，不会向未成年人出售电子烟产品。特别提醒：电子烟属于尼古丁制品，未成年人禁止使用，非吸烟者请勿尝试。孕妇及哺乳期妇女、心血管及呼吸道相关疾病患者禁止使用；请根据自身情况合理使用，若出现不适反应，请立即停止使用；请遵循国家法律法规，请勿在公共场合及明确标明禁止吸烟的场所使用电子烟及相关产品。" />
  </div>
</div>
</template>

<script>
export default {
  layout: 'common',
  data() {
    return {
    }
  },
  head () {
    return {
      title: 'vvild 小野雾化电子烟 - 小野官方网站'
    }
  },
  mounted() {
  },
  methods: {
  },
  components: {
  },
}
</script>

<style lang="scss" scoped>
.home-wrap .home-list {
  font-size: 0;
  img {
    width: 100%;
  }
}

.home-wrap .home-list .item-wrap {
  position: relative;
  img {
    padding-top: 4rem;
  }
  a {
    position: absolute;
    content: '';
    cursor: pointer;
    width: 4.7rem;
    height: 1.6rem;
    left: 49%;
    bottom: 7%;
    transform: translateX(-50%);
  }
}
</style>
