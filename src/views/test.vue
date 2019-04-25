<template>
  <div>
    <img class="fulfill_img" src="/static/images/pay_fulfill.png" />
    <div class="text1">支付成功</div>
    <div class="text2">
      <span class="dote">￥</span>
      <span class="money">100</span>
    </div>
    <div class="status">
      <div>
        <span>优惠金额</span>
        <span class="red">￥10</span>
      </div>
      <div>
        <span>订单编号</span>
        <span>ts032546546966796</span>
      </div>
    </div>
    <img class="lock" src="/static/images/lock_open.png" />
    <!-- <view class="goon goon1">继续购买</view> -->
    <div class="goon goon1" @click="open">继续购买</div>
    <!-- <view class="goon goon2">查看订单</view> -->
    <div class="goon goon2 m-border-gradient-1px m-border-gradient-left" open-type="switchTab" @click="openPicker">查看订单</div>
    <!-- <mt-datetime-picker
    ref="picker"
    type="time"
    v-model="pickerValue"
     @confirm="handleConfirm">
  </mt-datetime-picker> -->

  </div>
</template>

<script  type="text/ecmascript-6">
  import {Toast} from 'mint-ui';
  // import { DatetimePicker } from 'mint-ui';
  export default {
    data () {
      return {
        pickerValue:''
      }

    },
    components: {
      // DatetimePicker
    },
    created () {

    },
    methods: {
      open () {
        Toast({
          message: '提示',
          position: 'top',
          duration: 5000
        });
      },
      openPicker() {
        this.$refs.picker.open();
      },
      handleConfirm(e){
        console.log(e,this.pickerValue)
      }
    }
  }
</script>

<style scoped lang="scss">
 @import '../assets/style/variable';
  @import '../assets/style/m-1-px';
  .fulfill_img {
    display: block;
    // width: 170px;
    width: rpx(170px);
    height: rpx(150px);
    margin: rpx(50px) auto;
  }
  .text1,
  .text2 {
    text-align: center;
    color: #333;
    font-size: rpx(32px);
    // margin-bottom: 28px;
  }
  .text2 {
    .dote {
      font-weight: normal;
      margin-right: rpx(-15px);
    }
    .money {
      font-weight: bold;
    }
    font-size: rpx(80px);
    margin-bottom: rpx(30px);
  }
  .status {
    // height: 110px;
    width: rpx(648px);
    box-sizing: border-box;
    margin: rpx(30px) auto rpx(90px);
    border-top: rpx(1px) solid #ddd;
    border-bottom: rpx(1px) solid #ddd;
    color: #999;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: rpx(26px) rpx(30px);
    div {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      font-size: rpx(24px);
      .red {
        color: #fc4e5b;
      }
    }
  }
  .lock {
    width: rpx(648px);
    height: rpx(260px);
    display: block;
    margin: 0 auto rpx(64px);
  }

  .goon {
    width: rpx(648px);
    height: rpx(88px);
    box-sizing: border-box;
    color: #231816;
    text-align: center;
    line-height: rpx(88px);

    font-size: rpx(36px);
    margin: 0 auto;
    border-radius: rpx(44px);
  }
  .goon1 {
    // background-color: #ffea00;
    margin-bottom: rpx(30px);
    border: 1px solid #bbb;
  }
  .goon2 {
    color: #555;
    // border: 1px;
    // border: 1px solid #bbb;
    // @include border-b-1px(#bbb);

  }

  .upload_toast {
    position: absolute;
    z-index: 1000;
    width: 100%;
    height: 110%;
    background-color: rgba(40, 40, 40, 0.45);
    left: 0;
    top: 0;
    padding-top: rpx(200px);
    box-sizing: border-box;

    .container {
      border-radius: rpx(12px);
      width: 650px;
      margin: 0 auto;
      background: #fff;
      padding-bottom: rpx(30px);
      animation: scales 0.5s linear -0.4s;
      @keyframes scales {
        from {
          width: 0;
          height: 0;
        }
        to {
          width: 100%;
          height: 100%;
        }
      }
      img {
        width: rpx(650px);
        height: rpx(330px);
      }
      .tips1 {
        margin: rpx(50px) auto rpx(20px) auto;
        font-size: rpx(40px);
        font-weight: bolder;
        color: #231816;
        text-align: center;
      }
      .tips2 {
        margin: 0 auto rpx(50px) auto;
        font-size: rpx(28px);
        color: #aa9f9d;
        text-align: center;
      }
      .toUpload {
        width: rpx(590px);
        height: rpx(88px);
        background: #ffea00;
        border-radius: rpx(44px);
        color: #231816;
        font-size: rpx(36px);
        text-align: center;
        line-height: rpx(88px);
        margin: 0 auto;
      }
    }
    .close {
      margin: 0 auto;
      margin-top: rpx(80px);
      width: rpx(64px);
      height: rpx(64px);
      display: block;
    }
  }
</style>
