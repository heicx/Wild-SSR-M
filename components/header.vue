<template>
	<div class="header-topbar-wrap">
    <div class="tips"></div>
		<header class="topbar">
      <router-link class="logo" to="/"></router-link>
      <i 
        class="menu-btn"
        @click="changeMenu()"
      >
      </i>
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
	data() {
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
					name: '产品',
					alias: {
            path: 'product'
          },
					link: '/product'
				},
				{
					name: '关于我们',
					alias: {
            path: ['aboutus', 'joinus'],
            subItems: [
              {
                name: '公司介绍',
                link: '/aboutus',
                path: 'aboutus',
              },
              {
                name: '加入我们',
                link: '/joinus',
                path: 'joinus',
              },
            ],
          },
        },
        {
					name: '招商加盟',
					alias: {
            path: ['entityshop', 'investment'],
            subItems: [
              {
                name: '招商加盟',
                link: '/investment',
                path: 'investment',
              },
              {
                name: '专卖店计划',
                link: '/entityshop',
                path: 'entityshop',
              }
            ],
          },
        },
        {
					name: '帮助与支持',
					alias: {
            path: ['help-question', 'help-service'],
            subItems: [
              {
                name: 'V0 产品答疑',
                link: '/help/question',
                path: 'help-question',
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
      if (!items) {
        this.showMenu = !this.showMenu;
      }

      if (link !== '') {
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

.tips {
  position: relative;
  width: 100%;
  height: 1.5rem;
  background-image: url(~assets/images/header/tips@3x.png);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  z-index: 20;
}

.topbar {
  position: relative;
  width: 100%;
  height: 2.6rem;
  background: #f4f6fb;
  border-bottom: 1px solid #dde0e6;
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
    right: 5%;
    transform: translate(0, -50%);
    background-image: url(~assets/images/header/menu-btn@3x.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
  }
}

.menu-list {
  position: absolute;
  width: 100%;
  transition: all .35s ease-in-out;
  transform: translate3d(0, -380px, 0);
  text-align: center;
  background: #f4f6fb;
  color: #6f7484;
  font-size: .65rem;
  border-bottom: 1px solid #dde0e6;
  box-shadow: 0px 4px 12px -6px #ccc;
  z-index: 10;
  &.active {
    transform: translate3d(0, 0, 0);
  }
  >li {
    margin: 0 2rem;
    line-height: 2rem;
    &:last-child .item-name {
      border-bottom: none;
    }
    &.curr-on .item-name {
      font-weight: bold;
    }
  }
  .item-name, .sub-item-name {
    position: relative;
    border-bottom: 1px solid #dde0e6;
    &:after {
      position: absolute;
      content: '';
      width: .42rem;
      height: .42rem;
      top: 48%;
      transform: translate(0, -50%);
      margin-left: .25rem;
      background: url(~assets/images/header/arrow@3x.png) center no-repeat;
      background-position: 0 0;
      background-size: cover;
    }
    &.active {
      &:after {
        background-position: 0 -.42rem;
      }
    }
  }
  .sub-item-list {
    height: 0px;
    opacity: 0;
    transition: all .15s ease-in-out;
    border-bottom: 1px solid #dde0e6;
    >li {
      width: 4rem;
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
      height: 4rem;
      opacity: 1;
    }
  }
}
</style>
