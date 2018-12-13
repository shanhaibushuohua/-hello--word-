<template>
  <div class="servebox">
    <img src="../../../../common/img/icon/serve.jpg" alt="会计服务" class="serve">
    <Badge :count="4" type="info">
      <p class="servetext">会计小林</p>
    </Badge>
    <a class="servetext" @click="logout">退出</a>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  data() {
    return {};
  },
  methods: {
    ...mapActions(["handleLogOut"]),
    logout() {
      this.handleLogOut().then(() => {
        this.$router.push({
          name: "login"
        });
      });
    }
  }
};
</script>

<style lang="less" scoped>
@import "./serveAccounting.less";
</style>