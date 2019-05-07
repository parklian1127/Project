<template>
  <div>
    <!-- 搜索 -->

    <!-- 分类 -->
    <div class="category">
      <!-- 顶级分类 -->
      <ul class="sup">
        <li class="active">大家电</li>
        <li>大家电</li>
        <li>大家电</li>
        <li>大家电</li>
        <li>大家电</li>
        <li>大家电</li>
        <li>大家电</li>
        <li>大家电</li>
      </ul>

      <!-- 二级分类 -->

      <div class="sub">
        <scroll-view scroll-y>
          <image src="/static/uploads/category.png" class="thumb"/>
          <div class="children">
            <div class="title">家电</div>
            <div class="brands">
              <a href="">
                <image src="/static/uploads/brand_1.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_2.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_3.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_4.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_5.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>

              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>
            </div>
          </div>
          <div class="children">
            <div class="title">家电</div>
            <div class="brands">
              <a href="">
                <image src="/static/uploads/brand_1.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_2.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_3.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_4.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_5.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>

              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>
            </div>
          </div>
          <div class="children">
            <div class="title">家电</div>
            <div class="brands">
              <a href="">
                <image src="/static/uploads/brand_1.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_2.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_3.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_4.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_5.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>

              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>
              <a href="">
                <image src="/static/uploads/brand_6.jpg"/>
                <span>曲面电视</span>
              </a>
            </div>
          </div>
        </scroll-view>

      </div>

    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {}
  }
}
</script>

<style scoped lang="less">
  .category {
    width: 100%;
    position: absolute;
    top: 100rpx;
    bottom: 0;

    display: flex;

    .sup {
      width: 196rpx;
      background-color: #f4f4f4;

      display: flex;
      flex-direction: column;

      li {
        flex: 1;
        font-size: 28rpx;
        color: #333;

        display: flex;
        justify-content: center;
        align-items: center;

        &.active {
          color: #ea4451;
          background-color: #fff;
          position: relative;

          &::before {
            content: '';
            display: block;
            width: 8rpx;
            height: 60rpx;
            background-color: #ea4451;
            transform: translateY(-50%);

            position: absolute;
            left: 0;
            top: 50%;
          }
        }
      }
    }

    .sub {
      flex: 1;
      padding: 20rpx;

      scroll-view {
        height: 100%;
      }
      .thumb {
        width: 100%;
        height: 180rpx;
      }

      .children {
        text-align: center;

        .title {
          font-size: 30rpx;
          color: #333;
          padding-top: 30rpx;
          padding-bottom: 10rpx;

          &::before {
            content: '/';
            color: #999;
            margin-right: 20rpx;
          }
          &::after {
            content: '/';
            color: #999;
            margin-left: 20rpx;
          }
        }
      }

      .brands {
        display: flex;
        flex-wrap: wrap;


        a {
          width: 33.333%;
          margin-bottom: 20rpx;
        }

        image {
          width: 120rpx;
          height: 120rpx;
        }

        span {
          display: block;
          font-size: 24rpx;
          color: #333;
        }
      }
    }
  }

</style>
