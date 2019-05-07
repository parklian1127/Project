<template>
  <div>
    <!-- 搜索 -->
    <div class="search">

    </div>

    <!-- 焦点图 -->
    <swiper class="banner" indicator-dots indicator-color="rgba(255, 255, 255, 0.6)" indicator-active-color="#fff">
      <swiper-item :key="index" v-for="(list,index) in bannerList">
        <navigator :url="list.navigator_url">
          <image :src="list.image_src"/>
        </navigator>
      </swiper-item>
    </swiper>

    <!-- 导航条 -->
    <div class="navs">
      <navigator :url="item.navigator_url" :key="index" v-for="(item,index) in navList">
        <image :src="item.image_src"/>
      </navigator>
    </div>

    <!-- 楼层 -->
    <div class="floors">
      <div class="floor" :key="key" v-for="(list, key) in floorList">
        <div class="title">
          <image :src="list.floor_title.image_src"/>
        </div>
        <div class="items">
          <div class="item_left">
            <navigator>
              <image :src="list.product_list[0].image_src"/>
            </navigator>
          </div>
          <div class="item_right">
            <navigator>
              <image :src="list.product_list[1].image_src"/>
            </navigator>
            <navigator>
              <image :src="list.product_list[2].image_src"/>
            </navigator>
            <navigator>
              <image :src="list.product_list[3].image_src"/>
            </navigator>
            <navigator>
              <image :src="list.product_list[4].image_src"/>
            </navigator>
          </div>
        </div>
      </div>

    </div>

    <span class="gotop" @click="goTop" v-show="!isTop"></span>
  </div>
</template>

<script>

  import request from '@/utils/request'

  export default {
    data () {
      return {
        bannerList: [],
        navList: [],
        floorList: [],
        isTop: true
      }
    },
    methods: {
      async getBanner () {
        // let _this = this
        // mpvue.request({
        //   url: 'https://www.zhengzhicheng.cn/api/public/v1/home/swiperdata',
        //   method: 'get',
        //   success: function(info) {
        //     _this.bannerList = info.data.message
        //   }
        // })
        let {message} = await request({
          url: '/api/public/v1/home/swiperdata'
        })
        this.bannerList = message
      },

      async getNavs () {
        // let _this = this
        // mpvue.request({
        //   url:'https://www.zhengzhicheng.cn/api/public/v1/home/catitems',
        //   success: function (info) {
        //     _this.navList = info.data.message
        //   }
        // })
        let {message} = await request({
          url: '/api/public/v1/home/catitems'
        })
        this.navList = message
      },

      async getFloors () {
        let {message} = await request({
          url: '/api/public/v1/home/floordata'
        })
        this.floorList = message
      },

      goTop () {
        //可以将页面滚动到指定位置
        mpvue.pageScrollTo({
          scrollTop: 0
        })
      }
    },
    mounted () {

      //正常Promise
      // request('https://www.zhengzhicheng.cn/api/public/v1/home/swiperdata').then(function (info) {
      //   console.log(info)
      // })

      //利用async await 异步逻辑，变成同步语法
      // let info = await request('https://www.zhengzhicheng.cn/api/public/v1/home/swiperdata')
      // console.log(info)

      this.getBanner()
      this.getNavs()
      this.getFloors ()

    },
    //下拉刷新
    onPullDownRefresh () {
      this.getBanner()
      this.getNavs()
      this.getFloors ()
      mpvue.stopPullDownRefresh()
    },
    //上拉加载
    onReachBottom(){

    },
    //页面滚动
    onPageScroll(ev) {
      this.isTop = ev.scrollTop < 100
    }
  }

</script>

<style scoped lang="less">
  .banner {
    height: 340rpx;
    navigator {
      height: 100%;
      width: 100%;
    }
  }
  .navs {
    overflow: hidden;
    padding: 24rpx 30rpx;
    display: flex;
    justify-content: space-between;

    navigator {
      height: 128rpx;
      width: 128rpx;
     }
  }

  .floors {
    .floor {
      .title {
        height: 80rpx;
        background-color: rgb(243, 242, 242);
        padding: 30rpx 0 10rpx;
      }
      .items{
        padding: 20rpx 16rpx;
        display: flex;
        .item_left {
          width: 232rpx;
          height: 386rpx;
          padding-right: 16rpx;
           navigator {
             width: 100%;
             height: 100%;
           }
        }
        .item_right {
          flex: 1;
          display: flex;
          justify-content: space-between;
          align-content: space-between;
          flex-wrap: wrap;
          navigator {
            width: 234rpx;
            height: 188rpx;
          }
        }


      }
    }
  }
  .gotop {
    position: fixed;
    bottom: 70rpx;
    right: 30rpx;

    width: 88rpx;
    height: 88rpx;
    background-color: rgba(255, 255, 255, 0.6);
    border-radius: 50%;

  }
</style>
