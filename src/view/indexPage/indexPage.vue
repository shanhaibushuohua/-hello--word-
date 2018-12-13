<template>
  <Layout class="indexMain">
    <Header class="indexTitle">
      <Menu mode="horizontal" active-name="1" class="indexicon">
        <!--XUHAO_公司icon -->
        <div class="layout-logo">
          <img src="../../components/common/img/icon/logo.png" alt="光谷云" srcset>
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
        <MenuNav></MenuNav>
      </Header>
      <Content
        class="contentbox"
        :style="{margin: '88px 20px 0', background: '#fff', minHeight: '500px'}"
      >
        <Card></Card>
        <div class="companyList">sddasdsadsadsadsadsadsadsadsadsadsadsadasd
          <!-- <router-link to="/home">进入申报</router-link> -->
          <a @click="handleInfoHome">进入申报</a>
        </div>
        <!-- <router-view></router-view>   -->
      </Content>
    </Layout>
  </Layout>
</template>
<script>
import Message from "../../components/main/components/indexPage/message";
import ServeAccounting from "../../components/main/components/indexPage/serveAccounting";
import MenuNav from "../../components/main/components/indexPage/menu-nav";
import Card from "../../components/main/components/indexPage/card";
export default {
  name: "indexPage",
  components: {
    Message,
    ServeAccounting,
    MenuNav,
    Card
  },
  data() {
    return {
      indexPage: ""
    };
  },
  methods: {
    handleCuster() {
      console.log("bbbbb", this);
    },
    handleInfoHome() {
      this.$router.push({
        name: '/home',
        tagName:'/home'
      });
    }
  }
};
</script>
<style lang="less">
.indexMain {
  .indexCenter {
    display: flex;
    align-items: center;
    .ivu-layout-header {
      padding: 0;
      z-index: 999;
      .layout-nav {
        width: 80%;
        margin: 0 auto;
        display: flex;
      }
    }
    .ivu-layout-content {
      width: 80%;
      // height: auto !important;
      display: flex;
      background: #f5f7f9;
      justify-content: space-between;
      .contentbox {
        .companyList {
          width: 500px;
        }
      }
    }
  }
}
</style>


