<template>
  <div>
    <!-- 搜索 -->
    <div class="search">

    </div>

    <!-- 焦点图 -->
    <swiper class="banner" indicator-dots indicator-color="rgba(255, 255, 255, 0.6)" indicator-active-color="#fff">
      <swiper-item>
        <navigator>
          <image src="/static/uploads/banner1.png"></image>
        </navigator>
      </swiper-item>
      <swiper-item>
        <navigator>
          <image src="/static/uploads/banner2.png"></image>
        </navigator>
      </swiper-item>
      <swiper-item>
        <navigator>
          <image src="/static/uploads/banner3.png"></image>
        </navigator>
      </swiper-item>
    </swiper>

    <!-- 导航条 -->
    <div class="navs">
      <navigator>
        <image src="/static/uploads/icon_index_nav_1@2x.png"></image>
      </navigator>
      <navigator>
        <image src="/static/uploads/icon_index_nav_2@2x.png"></image>
      </navigator>
      <navigator>
        <image src="/static/uploads/icon_index_nav_3@2x.png"></image>
      </navigator>
      <navigator>
        <image src="/static/uploads/icon_index_nav_4@2x.png"></image>
      </navigator>
    </div>

    <!-- 楼层 -->
    <div class="floors">
      <div class="floor">
        <div class="title">
          <image src="/static/uploads/pic_floor01_title.png"></image>
        </div>
        <div class="items">
          <div class="item_left">
            <navigator>
              <image src="/static/uploads/pic_floor02_1@2x.png"></image>
            </navigator>
          </div>
          <div class="item_right">
            <navigator>
              <image src="/static/uploads/pic_floor02_2@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_3@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_4@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_5@2x.png"></image>
            </navigator>
          </div>
        </div>
      </div>
      <div class="floor">
        <div class="title">
          <image src="/static/uploads/pic_floor01_title.png"></image>
        </div>
        <div class="items">
          <div class="item_left">
            <navigator>
              <image src="/static/uploads/pic_floor02_1@2x.png"></image>
            </navigator>
          </div>
          <div class="item_right">
            <navigator>
              <image src="/static/uploads/pic_floor02_2@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_3@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_4@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_5@2x.png"></image>
            </navigator>
          </div>
        </div>
      </div>
      <div class="floor">
        <div class="title">
          <image src="/static/uploads/pic_floor01_title.png"></image>
        </div>
        <div class="items">
          <div class="item_left">
            <navigator>
              <image src="/static/uploads/pic_floor02_1@2x.png"></image>
            </navigator>
          </div>
          <div class="item_right">
            <navigator>
              <image src="/static/uploads/pic_floor02_2@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_3@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_4@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_5@2x.png"></image>
            </navigator>
          </div>
        </div>
      </div>
      <div class="floor">
        <div class="title">
          <image src="/static/uploads/pic_floor01_title.png"></image>
        </div>
        <div class="items">
          <div class="item_left">
            <navigator>
              <image src="/static/uploads/pic_floor02_1@2x.png"></image>
            </navigator>
          </div>
          <div class="item_right">
            <navigator>
              <image src="/static/uploads/pic_floor02_2@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_3@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_4@2x.png"></image>
            </navigator>
            <navigator>
              <image src="/static/uploads/pic_floor02_5@2x.png"></image>
            </navigator>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

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
    navigator {
      height: 128rpx;
      width: 128rpx;
      float: left;
      margin: 24rpx 20rpx;
      padding-left: 20rpx;

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
</style>
