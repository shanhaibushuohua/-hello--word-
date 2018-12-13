<style lang="less">
@import "./login.less";
</style>

<template>
  <div class="login">
    <div class="login-con">
      <Card icon="log-in" title="欢迎登录" :bordered="false">
        <div class="regstyle">
          <router-link to="/register" id="register">注册</router-link>
          <!-- <button @click="registerPage">注册</button> -->
        </div>
        <div class="form-con">
          <login-form @on-success-valid="handleSubmit"></login-form>
        </div>
      </Card>
    </div>
  </div>
</template>

<script>
import LoginForm from "_c/login-form";
import { mapActions } from "vuex";
import { getLoginUser } from "@/api/data";

export default {
  components: {
    LoginForm
  },
  methods: {
    ...mapActions(["handleLogin", "getUserInfo"]),
    handleSubmit({ userName, password }) {
      // console.log("---------- " + this);
      this.handleLogin({ userName, password }).then(res => {
        // console.log('loginasdsadds',res);
        this.getUserInfo().then(res => {
          // console.log("asdasdas", res);
          console.log ("home",this);
          this.$router.push({
            name: this.$config.homeName
          });
        });
      });
    }
  }
};
</script>

<style>
</style>
