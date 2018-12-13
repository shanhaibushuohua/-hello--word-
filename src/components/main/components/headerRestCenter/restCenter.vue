<template>
  <div class="restCenter">
    <Badge :count="4" class-name="demo-badge-alone" type="primary">
      <Icon type="ios-notifications-outline" size="30"></Icon>
    </Badge>
    <div class="user">
      <img src="../../../common/img/icon/userheader.jpg" alt="用户头像" class="userheader">
    </div>
    <span class="message">小东快递</span>
    <div class="outindex">
      <a @click="logout">退出</a>
      <!-- <router-link to="/logout">退出</router-link> -->
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  props: {},
  methods: {
    ...mapActions(["handleLogOut"]),
    logout() {
      this.handleLogOut().then(() => {
        this.$router.push({
          name: "login"
        });
      });
    },
  }
};
</script>
<style lang="less" scoped>
@import "./restCenter.less";
</style>
