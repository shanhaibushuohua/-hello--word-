<template>
  <div class="statisticalbox">
    <!-- XUHAO_下载 -->
    <div class="buttonbox">
      <Button type="primary" class="download">下载</Button>
      <Button type="primary" class="print">打印</Button>
    </div>
    <!-- XUHAO_日期 -->
    <div class="timeLine">
      <div class="countDate">
        <label for class="datacount">账期：</label>
        <Row>
          <Col span="12">
            <DatePicker
              type="month"
              :value="startDate"
              placeholder="Select month"
              style="width: 200px"
            ></DatePicker>
          </Col>
        </Row>
      </div>
      <div class="steps">
        <Badge text="2018年" type="primary" class="getyears"></Badge>
        <ul id="v-for-object" class="monthist">
          <li v-for="item in monthsCount">
            {{ item }}
            <Radio :name="item" class="monthradio"></Radio>
          </li>
        </ul>
      </div>
    </div>
    <!-- XUHAO_表格 -->
    <div class="statisticalTable">
      <Table highlight-row ref="currentRowTable" :columns="columns3" :data="data1" class="default"></Table>
    </div>
  </div>
</template>
<script>
export default {
  name: "statistical_table_page",
  data() {
    return {
      startDate: "2018-6",
      monthsCount: [
        "9月",
        "10月",
        "11月",
        "12月",
        "1月",
        "2月",
        "3月",
        "4月",
        "5月",
        "6月",
        "7月",
        "8月",
        "9月",
        "10月"
      ],
      columns3: [
        {
          type: "index",
          title: "序号",
          width: 100,
          align: "center",
          background: "red"
        },
        {
          title: "项目",
          width: 400,
          key: "name",
          align: "center"
        },
        {
          title: "行次",
          width: 85,
          key: "linecount",
          align: "center"
        },
        {
          title: "本年累计金额",
          width: 500,
          key: "cumulativeMoneyYear",
          align: "center",
          children: [
            {
              title: "金额",
              key: "moneyYear",
              align: "center",
              width: 250
            },
            {
              title: "同比增长率",
              key: "growthRateYear",
              align: "center",
              width: 250
            }
          ]
        },
        {
          title: "本月金额",
          width: 500,
          key: "monthMoney",
          align: "center",
          children: [
            {
              title: "金额",
              key: "moneyMonth",
              align: "center",
              width: 250
            },
            {
              title: "同比增长率",
              key: "growthRateMonth",
              align: "center",
              width: 250
            }
          ]
        }
      ],
      data1: [
        {
          name: "增值税",
          linecount: 1,
          moneyYear: 5000,
          growthRateYear: 1.1,
          moneyMonth: 5000,
          growthRateMonth: 1.2
        },
        {
          name: "1.应交增值税",
          linecount: 2
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        },
        {
          name: "（1）起初未抵扣款（以“-”号填列）",
          linecount: 3
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        },
        {
          name: "（2）销项税额",
          linecount: 4
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        },
        {
          name: "出口退税",
          linecount: 5
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        },
        {
          name: "进项税额转出",
          linecount: 6
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        },
        {
          name: "转出多交增值税",
          linecount: 7
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        },
        {
          name: "（3）进项税额",
          linecount: 8
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        },
        {
          name: "已交税金",
          linecount: 9
          // moneyYear: 5000,
          // growthRateYear: 1.1,
          // moneyMonth: 5000,
          // growthRateMonth: 1.2
        }
      ]
    };
  },
  methods: {}
};
</script>
<style lang="less" scoped>
.statisticalbox {
  display: flex;
  flex-flow: column;
  padding: 0 20px;
  .buttonbox {
    text-align: end;
    margin-right: 50px;
    overflow: hidden;
    margin-bottom: 40px;
    .download {
      background-color: rgb(48, 47, 47);
      color: white;
      margin-right: 30px;
      border: none;
    }
    .download:hover {
      background-color: rgb(61, 59, 59);
      color: gray;
    }
    .print {
      background-color: rgb(48, 47, 47);
      color: white;
      border: none;
    }
    .print:hover {
      background-color: rgb(61, 59, 59);
      color: gray;
    }
  }
  .timeLine {
    //   margin-top: 60px;;
    display: flex;
    align-items: center;
    .countDate {
      display: flex;
      align-items: center;
      .datacount {
        white-space: nowrap;
      }
    }
    .steps {
      display: flex;
      position: relative;
      flex-flow: column;
      width: 100%;
      .getyears {
        position: absolute;
        top: -30px;
        left: 440px;
      }
      .monthist {
        width: 95%;
        flex: 1;
        margin-left: 2%;
        list-style: none;
        display: flex;
        text-align: center;
        justify-content: space-around;
      }
      .monthradio {
        position: absolute;
        margin-left: -5px;
        transform: rotate(45deg);
        // right: 1px;
        // .ivu-radio-inner{
        //   border-radius: 0;
        // }
        // .ivu-radio-input{
        //    border-radius: 0;
        // }
      }
    }
  }
  .statisticalTable {
    margin-top: 20px;
    text-align: center;
    .default .ivu-table-header th{
      background-color:black; 
    }
  
  }
}
</style>
 