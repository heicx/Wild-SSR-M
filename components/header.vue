<template>
	<div class="header-topbar-wrap">
    <!-- <div class="tips"></div> -->
    <div class="tips-wrap">
      <p class="tips">特别提醒：本产品含有尼古丁，未成年人禁止使用，非吸烟者请勿尝试</p>
    </div>
		<header class="topbar">
      <router-link class="logo" to="/"></router-link>
      <i 
        class="menu-btn"
        @click="changeMenu()"
      >
      </i>
      <!-- <a href="https://xiaoyeyanju.tmall.com" class="buy-btn"></a> -->
		</header>
    
    <ul
      class="menu-list"
      :class="{'active': showMenu}"
    >
      <li
        v-for="(item, index) in list"
        :key="index"
        :class='{"curr-on": item.alias.path.indexOf($route.name) > -1 }'
        @click="changeMenu(item.alias.subItems, item.link)"
      >
        <div class="item-name" v-if="!item.alias.subItems">
          {{item.name}}
        </div>
        <div v-else>
          <div
            class="item-name"
            :class="{'active': item.alias.subItems.indexOf(subItemName) > -1}"
            @click="changeSubMenu(item.alias.subItems)"
          >
            {{item.name}}
          </div>
          <ul
            class="sub-item-list"
            :class="{'active': item.alias.subItems.indexOf(subItemName) > -1}"
          >
            <li
              v-for="(subItem, index) in item.alias.subItems"
              :key="index"
              class="sub-item-name"
              :class='{"curr-on": subItem.path.indexOf($route.name) > -1 }'
              @click="changeMenu(false, subItem.link)"
            >
              {{subItem.name}}
            </li>
          </ul>
        </div>
      </li>
    </ul>
	</div>
</template>

<script>
export default {
	data () {
		return {
      subItemName: '',
      showMenu: false,
			list: [
				{
					name: '首页',
					alias: {
            path: 'index',
          },
					link: '/'
        },
        {
          name: '专卖店计划',
          alias: {
            path: 'entityshop',
          },
					link: '/entityshop'
        },
        {
          name: '招商加盟',
          alias: {
            path: 'investment',
          },
					link: '/investment'
        },
        {
          name: '用户口碑',
          alias: {
            path: 'praises',
          },
					link: '/praises'
        },
        {
          name: '小野店主故事',
          alias: {
            path: 'stories',
          },
					link: '/stories'
        },
				// {
				// 	name: '产品',
				// 	alias: {
        //     path: ['product-v1', 'product-v0'],
        //     subItems: [
        //       {
        //         name: '雾化电子烟 V1',
        //         link: '/product-v1',
        //         path: 'product-v1',
        //       },
        //       {
        //         name: '雾化电子烟 V0',
        //         link: '/product-v0',
        //         path: 'product-v0',
        //       },
        //     ],
        //   },
        // },
        // {
				// 	name: '视频中心',
				// 	alias: {
        //     path: 'media',
        //   },
				// 	link: '/media'
				// },
				// {
				// 	name: '关于我们',
				// 	alias: {
        //     path: ['aboutus', 'joinus'],
        //     subItems: [
        //       {
        //         name: '公司介绍',
        //         link: '/aboutus',
        //         path: 'aboutus',
        //       },
        //       {
        //         name: '加入我们',
        //         link: '/joinus',
        //         path: 'joinus',
        //       },
        //     ],
        //   },
        // },
        // {
				// 	name: '招商加盟',
				// 	alias: {
        //     path: ['entityshop', 'investment'],
        //     subItems: [
        //       {
        //         name: '招商加盟',
        //         link: '/investment',
        //         path: 'investment',
        //       },
        //       {
        //         name: '专卖店计划',
        //         link: '/entityshop',
        //         path: 'entityshop',
        //       }
        //     ],
        //   },
        // },
        {
					name: '关于我们',
					alias: {
            path: ['aboutus', 'help-service'],
            subItems: [
              // {
              //   name: 'V0 产品答疑',
              //   link: '/help/question',
              //   path: 'help-question',
              // },
              {
                name: '公司介绍',
                link: '/aboutus',
                path: 'aboutus'
              },
              {
                name: '客服中心',
                link: '/help/service',
                path: 'help-service'
              }
            ],
          },
				},
			]
		}
  },
  methods: {
    changeSubMenu: function(items) {
      const name = items[0];
      if (name !== this.subItemName) {
        this.subItemName = items[0];
      } else {
        this.subItemName = '';
      }
    },
    changeMenu: function(items, link) {
      console.log(link)
      if (!items) {
        this.showMenu = !this.showMenu;
      }

      if (!!link) {
        this.$router.push({ path: link });
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.header-topbar-wrap {
  position: fixed;
  width: 100%;
  max-width: 540px;
  z-index: 30;
}

.tips-wrap {
  position: relative;
  background: #000;
  z-index: 5;
  .tips {
    color: #fff;
    font-size: 10px;
    padding: 8px 0;
    transform: scale(0.9);
  }
}

.topbar {
  position: relative;
  width: 100%;
  height: 2.6rem;
  background: #000;
  border-bottom: 1px solid #000;
  z-index: 20;
  .logo {
    position: absolute;
    content: '';
    width: 5.2rem;
    height: .8rem;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-image: url(~assets/images/header/logo@3x.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
  }
  .menu-btn {
    position: absolute;
    content: '';
    width: .85rem;
    height: .55rem;
    top: 50%;
    left: 1rem;
    transform: translate(0, -50%);
    background-image: url(~assets/images/header/menu-btn@3x.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
  }
  .buy-btn {
    position: absolute;
    content: '';
    width: 3.38rem;
    height: 1.26rem;
    top: 50%;
    right: 1rem;
    transform: translateY(-50%);
    background-image: url(~assets/images/common/buy-btn@3x.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
  }
}

.menu-list {
  position: absolute;
  width: 100%;
  transition: all .35s ease-in-out;
  transform: translate3d(0, -420px, 0);
  text-align: center;
  background: #000;
  color: #b3b3b3;
  font-size: .65rem;
  z-index: 1;
  &.active {
    transform: translate3d(0, 0, 0);
  }
  >li {
    margin: 0 12%;
    &:last-child .item-name {
      border-bottom: none;
    }
    &.curr-on .item-name {
      font-weight: bold;
    }
  }
  .item-name, .sub-item-name {
    position: relative;
    color: #b3b3b3;
    height: 2.4rem;
    line-height: 2.4rem;
    text-align: left;
    border-bottom: 1px solid rgba(77, 77, 77, .7);
    &:after {
      position: absolute;
      content: '';
      width: .4rem;
      height: .4rem;
      top: 50%;
      transform: translate(0, -50%);
      right: 0;
      background: url(~assets/images/header/arrow@3x.png) center no-repeat;
      background-position: 0 0;
      background-size: cover;
    }
    &.active {
      &:after {
        background-position: 0 -.4rem;
      }
    }
  }
  .sub-item-list {
    height: 0px;
    opacity: 0;
    transition: all .15s ease-in-out;
    border-bottom: 1px solid rgba(77, 77, 77, .7);
    >li {
      width: 10rem;
      margin: 0 auto;
      // border-bottom: 1px solid #dde0e6;
      &:last-child {
        border-bottom: none;
      }
      &.curr-on {
        font-weight: bold;
      }
    }
    &.active {
      height: 4.8rem;
      opacity: 1;
    }
  }
}
</style>
