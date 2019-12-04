<template>
  <div class="login" v-if="!isLogin">
    <div v-if="loginType === 'username'">
      <label>用户名</label>
      <input placeholder="请输入用户名" key="username-input" v-model="userName" />
    </div>
    <div v-else>
      <label>邮箱</label>
      <input placeholder="请输入邮箱地址" key="email-input" v-model="userName" />
    </div>
    <button v-on:click="changeLoginType">{{buttonText}}</button>
    <button v-on:click="loginIn">登录</button>
  </div>
  <div class="login" v-else>
    <h1>hi {{userName}}</h1>
    <button v-on:click="loginOut">注销</button>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      loginType: "username",
      buttonText: "使用邮箱登录",
      isLogin: false,
      userName: ""
    };
  },
  methods: {
    changeLoginType: function() {
      this.loginType = this.loginType === "username" ? "email" : "username";
      this.buttonText =
        this.buttonText === "使用邮箱登录" ? "使用用户名登录" : "使用邮箱登录";
      this.userName = "";
    },
    loginIn: function() {
      this.isLogin = true;
    },
    loginOut: function() {
      this.isLogin = false;
      this.userName = "";
    }
  },
  computed: {}
};
</script>

<style>
.login {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.login label {
  margin-right: 5px;
  width: 50px;
  display: inline-block;
}
.login input {
  width: 120px;
}
.login button {
  margin-top: 10px;
  width: 175px;
}
</style>