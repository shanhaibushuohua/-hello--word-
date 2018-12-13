<template>
  <Layout class="indexPageMain">
    <Header class="indexTitle">
      <Menu mode="horizontal" active-name="1" class="indexicon">
        <!--XUHAO_公司icon -->
        <div class="layout-logo">
          <img src="../common/img/icon/logo.png" alt="光谷云" srcset>
        </div>
        <div class="layout-nav">
          <!-- XUHAO_信息 -->
          <Message></Message>
        </div>
        <div class="restCenter">
          <!-- XUHAO_ 会计服务-->
          <ServeAccounting></ServeAccounting>
        </div>
      </Menu>
    </Header>
    <!-- XUHAO_ 导航- -->
    <Layout class="indexCenter">
      <Header :style="{position: 'fixed', width: '100%'}">
        <Menu mode="horizontal" theme="dark" active-name="indexPage" ref="indexPage">
          <div class="layout-logo"></div>
          <div class="layout-nav">
              <Submenu name="1">
                <template slot="title">
                  <Icon type="ios-navigate"></Icon>客户管理
                </template>
                <MenuItem name="company_table_page">企业列表</MenuItem>
                <MenuItem name="disable_table_page">停用列表</MenuItem>
              </Submenu>
              <Submenu name="2">
                <template slot="title">
                  <Icon type="ios-keypad"></Icon>批量申报
                </template>
                <MenuItem name="taxDeclaration" to=''>税款申报</MenuItem>
                <MenuItem name="checkPass">检查通过</MenuItem>
                <MenuItem name="zeroDeclare">零申报</MenuItem>
              </Submenu>
              <Submenu name="3">
                <template slot="title">
                  <Icon type="ios-analytics"></Icon>汇算清缴
                </template>
                <MenuItem name="3-1">Option 1</MenuItem>
                <MenuItem name="3-2">Option 2</MenuItem>
              </Submenu>
                <Submenu name="3">
                <template slot="title">
                  <Icon type="ios-analytics"></Icon>基础设置
                </template>
                <MenuItem name="departmentManagement">部门管理</MenuItem>
                <MenuItem name="roleManagement">角色管理</MenuItem>
              </Submenu>
          </div>
        </Menu>
      </Header>
      <Content class="asdfsdfds" :style="{margin: '88px 20px 0', background: '#fff', minHeight: '500px'}">
            <!-- <router-view></router-view>   -->
      </Content>
    </Layout>
  </Layout>
</template>
<script>
import Message from "../main/components/message";
import ServeAccounting from "../main/components/serveAccounting";
export default {
  name: "indexPage",
  components: {
    Message,
    ServeAccounting
  },
  data() {
    return {
      indexPage:''
    };
  },
  methods: {
    handleCuster() {
      console.log("bbbbb", this);
    }
  }
};
</script>
<style lang="less">
.indexPageMain {
  .indexCenter {
    .ivu-layout-header {
      padding: 0;
      .layout-nav {
        width: 80%;
        margin: 0 auto;
        
      }
    }
    .ivu-layout-content {
      width: 80%;
      margin: 20px auto !important;
    }
  }
}
</style>

