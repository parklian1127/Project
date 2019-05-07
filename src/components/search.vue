<template>
  <!-- 搜索 -->
  <div class="search" :class="{focused: focused}">
    <!-- 搜索框 -->
    <div class="input-box">
      <input @input="qs" v-model="query" type="text" :placeholder="placeholder" @click="goSearch">
      <span @click="cancelSearch">取消</span>
    </div>

    <!-- 搜索结果 -->
    <div class="content">
      <div class="title">历史搜索 <span class="clear"></span></div>
      <div class="history">
        <a href="">小米</a>
        <a href="">小米</a>
        <a href="">小米</a>
        <a href="">小米</a>
      </div>
      <!-- 搜索推荐 -->
      <div class="result" v-show="queryList.length">
        <scroll-view scroll-y>
          <a href="" :key="list.goods_id" v-for="list in queryList">{{list.goods_name}}</a>

        </scroll-view>
      </div>
    </div>

  </div>
</template>

<script>
import request from '@/utils/request'

export default {

  data () {
    return {
      focused: false,
      placeholder: '',
      query:'',
      queryList: []
    }
  },

  methods: {
    goSearch () {
      this.focused = true
      this.placeholder = '请输入商品信息'
    },
    cancelSearch () {
      this.focused = false,
      this.placeholder = ''
    },
    async qs () {
      let { message } = await request ({
        url: '/api/public/v1/goods/search',
        data: {
          query: this.query
        }
      })
      this.queryList = message.goods
    }
  },
}
</script>

<style scoped lang="less">

  .search {
    display: flex;
    flex-direction: column;

    .input-box {
      // height: 60rpx;
      padding: 20rpx;
      background-color: #ff2d4a;
      position: relative;

      display: flex;
      justify-content: space-between;

      &::after {
        content: '搜索';
        display: block;
        height: 44rpx;
        width: 54rpx;
        line-height: 44rpx;
        padding-left: 60rpx;
        transform: translate(-50%, -50%);
        font-size: 24rpx;
        color:#bbb;
        background-image: url(https://ugo2.oss-cn-hangzhou.aliyuncs.com/images/icon_search%402x.png);
        background-repeat: no-repeat;
        background-size: 44rpx;

        position: absolute;
        top: 50%;
        left: 50%;

      }
      &::before {
        content: '';
        display: none;
        height: 44rpx;
        width: 44rpx;
        transform: translateY(-50%);
        background-image: url(https://ugo2.oss-cn-hangzhou.aliyuncs.com/images/icon_search%402x.png);
        background-repeat: no-repeat;
        background-size: 44rpx;

        position: absolute;
        top: 50%;
        left: 50rpx;
      }
      span {
        display: none;
        width: 80rpx;
        height: 60rpx;
        line-height: 60rpx;
        text-align: right;
        font-size: 27rpx;
        color: #999;
      }

      input {
        height: 60rpx;
        background-color: #fff;
        border-radius: 10rpx;
        padding-left: 90rpx;
        font-size: 24rpx;
        color: #666;

        flex: 1;

      }
    }

    &.focused {

      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
      z-index: 9;

      .input-box {
        background-color: #eee;

        &::after {
          display: none;
        }

        &::before {
          display: block;
        }

        span {
          display: block;
        }
      }
      .content {
        display: block;
      }
    }

    .content {
      display: none;
      flex: 1;
      background-color: pink;
      padding: 30rpx;
      position: relative;

      .title {
        font-size: 28rpx;
        color: #333;
      }

      .clear {
        float: right;
        width: 28rpx;
        height: 28rpx;
        background-image: url(https://ugo2.oss-cn-hangzhou.aliyuncs.com/images/clear.png);
        background-size: cover;
      }

      .history {
        padding-top: 30rpx;
        a {
          padding: 10rpx 20rpx;
          margin-right: 20rpx;
          margin-bottom: 10rpx;
          display: inline-block;
          background-color: #ddd;
          color: #333;
          font-size: 24rpx;

        }
      }

      .result {
        position: absolute;
        left: 0;
        top: 0;
        right: 0;
        bottom: 0;
        background-color: #ccc;

        scroll-view {
          height: 100%;
        }

        a {
          padding: 18rpx 20rpx;
          border-bottom: 1rpx solid #eee;
          font-size: 24rpx;
        }
      }

    }
  }

</style>
