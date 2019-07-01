<template>
    <div class="quoteModule">
      <!--报价表-->
      <el-card class="box-card">
        <ul class="quoteHeader">
          <li class="fastQuote active">快速报价</li>
          <li class="fastSub">马上预约</li>
        </ul>
        <span class="quoteFont">装修多少钱 佳盛豪帮您预算</span>
        <el-input type="text" placeholder="面积" v-model="homeArea" maxlength="11" clearable show-word-limit ref="homeArea" class="areaInput"></el-input>
        <el-input placeholder="称呼"clearable v-model="userName " class="areaInput"></el-input>
        <el-input placeholder="手机号" v-model="phoneNum" clearable class="areaInput" ref="phoneNum"></el-input>

        <div class="quoteCost"><span><i class="el-icon-s-platform"></i>设计费 {{designCost}} CNY</span></div>
        <div class="quoteCost"><span><i class="el-icon-s-home"></i>装修费 {{fitmentCost}} CNY</span></div>
        <el-button type="warning" @click="fastQuote()" class="quoteBut" v-bind:disabled="allInput" ref="quoteBut">马上报价</el-button>
        <div class="succeedQuote"><span>已有 <b>{{succeedQuote}}</b> 位业主成功获取报价</span></div>
        <div class="mattersNeedAttention"><span>*实际具体价格以现场测量为准</span></div>
      </el-card>
    </div>
</template>

<script>
    export default {
      name: "puote",
      data() {
        return {
          homeArea: null,
          userName:null,
          phoneNum: null,
          allInput:true,
          designCost:'0',
          fitmentCost:'0',
          succeedQuote:'2091',

        }
      },
      watch:{
        phoneNum:function () {
          if (this.homeArea!='' && this.phoneNum!=''){
            this.allInput = false;
          }
        }
      },
      methods:{
        fastQuote(){
          // 用cleadLound存储信息后再报价
         if (!this.phoneNum){
           let phoneNumber = this.$refs.phoneNum
           console.log(phoneNumber)
           console.log(phoneNumber.$el.style)
         }else if (!this.homeArea){
           let homeArea = this.$refs.homeArea
           console.log(homeArea)
           console.log(homeArea.$el.style)
         } else {
           this.designCost = this.homeArea * 50;
           this.fitmentCost = this.homeArea * 650;
         }
        }
      }
    }
</script>

<style scoped>
  ul,li{
    list-style: none;
  }
  /*输入框标红*/
  .areaInput.active >>>.el-input__inner:focus{
    border-color:red !important;
  }

  .quoteModule>.box-card{
    width: 302px;
    background: rgba(0,0,0,0.6);
  }
  .quoteHeader{
    display: flex;
    font-size: 18px;
    justify-content: space-around;
  }
  .quoteHeader>.fastQuote,.fastSub{
    color:rgba(255,255,255,0.8);
    cursor: pointer;
  }
  .fastQuote.active,.fastSub.active{
    cursor: pointer;
    font-size: 20px;
    color: #fff;
    font-weight: bold;
  }
  .quoteFont{
    font-size: 12px;
    color: rgba(255,255,255,0.6);
    text-align: center;
    margin: 0 56px;
  }
  .areaInput{
    margin-top: 10px;
    outline-color: red;
  }
  .quoteCost{
    margin: 15px 0;
    text-align: center;
  }
  .quoteCost span{
    font-size: 18px;
    color:rgba(255,255,255,0.8);
  }
  .quoteBut{
    width: 100%;
  }
  .succeedQuote{
    color:rgba(255,255,255,0.8);
    margin-top: 14px;
    text-align: center;
  }
  .mattersNeedAttention{
    color:rgba(255,255,255,0.8);
    font-size: 12px;
    text-align: center;
    margin-top: 5px;
  }
</style>
