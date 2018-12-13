<template>
  <div class="headerbox">
    <Row class="row">
      <Col span="12" class="companySearch">
        <!-- <Badge :count="5" type="primary" class=""> -->
          <Select v-model="model11.value" filterable class="companyStyle">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
          </Select>
          <i class="companycounts">3</i>
        <!-- </Badge> -->
      </Col>
      <Col span="10" class="countSearch">
        <Select v-model="model12.value" filterable class="countStyle">
          <Option v-for="item in count" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>
      </Col>
    </Row>
  </div>
</template>
<script>
export default {
  data() {
    return {
      cityList: [
        {
          value: "成都佳韵天成企业管理咨询有限公司",
          label: "成都佳韵天成企业管理咨询有限公司"
        },
        {
          value: "London",
          label: "London"
        },
        {
          value: "Sydney",
          label: "Sydney"
        },
        {
          value: "Ottawa",
          label: "Ottawa"
        },
        {
          value: "Paris",
          label: "Paris"
        },
        {
          value: "Canberra",
          label: "Canberra"
        }
      ],
      count: [
        { value: "2018年第6期", label: "2018年第6期" },
        { value: "2018年第7期", label: "2018年第7期" },
        { value: "2018年第8期", label: "2018年第8期" }
      ],
      model11: {
        value: "成都佳韵天成企业管理咨询有限公司"
      },
      model12: {
        value: "2018年第6期",
        label: "2018年第6期"
      }
    };
  }
};
</script>


<style lang="less">
@import "./headerSearch.less";
</style>