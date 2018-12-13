<template>
  <div class="cardMain">
    <Card class="title">
      <div class="cardbc">
        <p class="titlestyle">上午好，小林！</p>
        <p>工作再忙也不要忘记喝水！</p>
      </div>
    </Card>
    <div class="content">
      <div class="contentHead">
        <div class="dateTime">
          <div>
            <h5 class="titleDate">报税倒计时</h5>
            <p class="overDate">本月报税截止</p>
          </div>
          <p>
            <img src="../../../../common/img/one_card.jpg" alt="日期">
            <img src="../../../../common/img/five_card.jpg" alt="日期">
          </p>
        </div>
        <p class="messagetext">本月已向36家客户推送扣款需求，共56家需报税！</p>
      </div>
      <div class="progressDate">
        <span>进度统计</span>
        <Select v-model="model1" style="width:200px" class="dataSelect">
          <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>
      </div>
      <!-- 百分比饼图 -->
      <div class="percentage">
        <div class="pointBox">
          <i-circle :percent="80">
            <span class="demo-Circle-inner" style="font-size:24px">80%</span>
          </i-circle>
          <span>未初始化</span>
        </div>
           <div class="pointBox">
          <i-circle :percent="80">
            <span class="demo-Circle-inner" style="font-size:24px">80%</span>
          </i-circle>
          <span>未初始化</span>
        </div>
           <div class="pointBox">
          <i-circle :percent="80">
            <span class="demo-Circle-inner" style="font-size:24px">80%</span>
          </i-circle>
          <span>未初始化</span>
        </div>
           <div class="pointBox">
          <i-circle :percent="80">
            <span class="demo-Circle-inner" style="font-size:24px">80%</span>
          </i-circle>
          <span>未初始化</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      model1: "2018年9期",
      cityList: [
        {
          value: "2018年9期",
          label: "2018年9期"
        },
        {
          value: "2018年10期",
          label: "2018年10期"
        },
        { value: "2018年11期", label: "2018年11期" }
      ]
    };
  }
};
</script>
<style lang="less" slot-scoped>
@import "./card.less";
</style>


