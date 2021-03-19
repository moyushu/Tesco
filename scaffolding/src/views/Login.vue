<template>
  <div class="login">
    <!-- 登录信息 -->
    <div class="container">
      <h3 class="title">LOGIN | 用户登录</h3>
      <input
        v-model="user"
        class="user"
        type="text"
        placeholder="请输入你的用户名"
      />
      <input
        v-model="upwd"
        class="upwd"
        type="password"
        placeholder="请输入你的密码"
      />
      <input
        type="text"
        class="check"
        v-model="incode"
        placeholder="请输入验证码"
      />
      <button @click="getcode" class="code" v-text="code"></button>
      <div class="forget">
        <el-link href="https://element.eleme.io" target="_self"
          >忘记密码</el-link
        >
      </div>
      <div><button @click="open" class="record">登录</button></div>
    </div>
  </div>
</template>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.login {
  background-image: url(../../public/images/login/bg.jpg);
  background-repeat: no-repeat;
  position: absolute;
  background-size: cover;
  background-position: center;
  height: 100%;
  width: 100%;
}
.login .container {
  margin: 10rem 34rem;
  position: absolute;
  width: 500px;
  height: 450px;
  background-color: #1fe98b;
  border-radius: 10%;
}
.login .container .title {
  margin-top: 30px;
  text-align: center;
  color: #6d04c2;
  font-size: 45px;
  background: -webkit-linear-gradient(
    50deg,
    #eb0f1a,
    #400ee6,
    #eb0e6a,
    #1f11e6,
    #076eb3
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.login .container input {
  color: rgb(231, 217, 15);
  font-size: 16px;
  margin: 0 auto;
  display: block;
  width: 200px;
  height: 40px;
  margin-top: 20px;
  padding-left: 40px;
  border-radius: 10px;
  background-color: #241022;
  border: none;
  outline: none;
}
.login .container .user {
  background-image: url(../../public/images/login/user.png);
  background-repeat: no-repeat;
  background-size: 20px;
  background-position: 10px center;
}
.login .container .upwd {
  background-image: url(../../public/images/login/upwd.png);
  background-repeat: no-repeat;
  background-size: 20px;
  background-position: 10px center;
}
.login .container .check {
  display: inline-block;
  width: 100px;
  margin: 20px 0 0px 150px;
  padding: 6px;
}
.login .container .code {
  display: inline-block;
  cursor: pointer;
  margin: 10px;
  width: 90px;
  height: 40px;
  text-align: center;
  font-size: 16px;
}
.login .container ::placeholder {
  font-size: 14px;
}
.login .container .forget {
  margin-left: 290px;
}
.login .container .record {
  margin: 20px 175px;
  width: 150px;
  height: 35px;
  border-radius: 75px;
  border: none;
  outline: none;
}
.login .container .record:hover {
  cursor: pointer;
  background-color: rgb(63, 216, 236);
}
</style>
<script>
export default {
  data() {
    return {
      user: "",
      upwd: "",
      incode: "",
      code: "",
    };
  },
  methods: {
    getcode() {
      var str = "";
      for (var a = 0; a <= 3; a++) {
        str += Math.floor(Math.random() * 10);
      }
      this.code = str;
    },
    open() {
      if (this.incode == "") {
        this.$alert("验证码不能为空", {
          confirmButtonText: "确定",
        });
      } else if (this.incode != this.code) {
        this.$alert("验证码错误", {
          confirmButtonText: "确定",
        });
      }
    },
  },
  mounted() {
    this.getcode();
  },
};
</script>