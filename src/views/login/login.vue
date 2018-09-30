<template>
  <div class="login-container" :style="">

  </div>
</template>

<script>

import ajax from '@utils/config';
import Cookies from 'js-cookie';
import store from '@src/store';
import baseURL from '$lib/utils/baseURL';
import handleRouter from '@src/utils/handleRouter';
export default {
  name: 'login',
  data() {
    const validateEmail = (rule, value, callback) => {
      if (!value) {
        callback(new Error('电子邮件不能为空！'));
      } else {
        callback();
      }
    };
    const validatePass = (rule, value, callback) => {
      if (value.length < 6) {
        callback(new Error('密码不能小于6位！'));
      } else {
        callback();
      }
    };
    return {
      labelPosition: 'top',
      checked: false,
      bgImg:'' ,
     
      
      loginForm: {
        username: '',
        password: '',
        randomStr: '',
        code: '',
        grant_type: 'password',
        scope: 'server'
      },
      imgUrl: '',
      loginRules: {
        email: [
          { required: true, trigger: 'blur', validator: validateEmail }
        ],
        password: [
          { required: true, trigger: 'blur', validator: validatePass }
        ]
      },
      loading: false
    }
  },
  mounted() {
  },
  created() {
    this.reLoad();
    Cookies.remove('token');
  },
  computed: {
  },
  methods: {
    handleLogin() {
      this.$refs.loginForm.validate(valid => {
        if (valid) {
          this.loading = true;
          this.login();
        } else {

          console.log('error submit!!');
          return false;
        }
      });
    },
    // 登录
    login() {
      ajax({
        url: 'auth/oauth/token' + '?grant_type=password&scope=server&username=admin&password=123456' + '&code=' + this.loginForm.code + '&randomStr=' + this.loginForm.randomStr,
        optionParams: this.loginForm
      }).post()
        .then(res => {
          if (res.code === 200) {
            this.$store.dispatch('SETTOKEN', { token: 'Bearer ' + res.access_token });
            Cookies.set('token', 'Bearer ' + res.access_token);
            Cookies.set('userName', res.userName);
            this.getMenuList();
          } else {
            this.$message({
              message: res.msg,
              type: "warning"
            });
            this.reLoad();
          }

        })
        .catch(error => {
          this.loading = false;
          console.log(error)
        })
    },
    //刷新图片
    reLoad() {
      let i = Date.parse(new Date());//目的是使图片不一样 
      this.loginForm.randomStr = i;
      this.imgUrl = baseURL() + 'admin/code/' + i;
    },
    // 菜单信息
    getMenuList() {
      this.$store.dispatch('MenuList').then(response => {
        // ;

        this.$store.dispatch('ALLROUTER', { allRouter: response });
        handleRouter(0, true).then(res => {
          this.$router.push({ path: this.$store.getters.headerRouter[0].resourceUrl });
        });
      })
    }
  }
}
</script>

<style rel="stylesheet/less" lang="less" scoped>
.el-form-item__label {
  height: 19px !important;
  line-height: 19px !important;
  font-size: 19px !important;
}

.input {
  height: 57px;
  width: 100%;
  border-bottom: 1px solid rgba(255, 255, 255, 1) !important;
  background: rgba(0, 0, 0, 1);
  color: rgba(255, 255, 255, 1);
  line-height: 57px;
  font-size: 20px;
}

.login-container {
  position: relative;
  width: 100%;
  height: 100%;

  background-repeat: no-repeat;
  background-size: 100% 100%;
  -moz-background-size: 100% 100%; // background-image: 
  // input:-webkit-autofill {
  //   -webkit-box-shadow: 0 0 0px 1000px #293444 inset !important;
  //   -webkit-text-fill-color: #fff !important;
  // }
  // input {
  //   background: transparent;
  //   border: 0px;
  //   -webkit-appearance: none;
  //   border-radius: 0px;
  //   padding: 12px 5px 12px 15px;
  //   color: #eeeeee;
  //   height: 47px;
  // }
  // .el-input {
  //   display: inline-block;
  // }
  .login-form {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    height: 694px;
    width: 723px;
    background: rgba(0, 0, 0, 1);
    opacity: 0.8;
    filter: alpha(opacity=80); //filter 过滤器   兼容IE678
    margin: auto;
    border-radius: 2px;
    .mainCon {
      width: 557px;
      margin-left: 80px;
      margin-top: 66px;
      .title {
        width: 334px;
        height: 32px;
        font-size: 32px;
        font-family: MicrosoftYaHeiLight;
        font-weight: bold;
        color: rgba(255, 255, 255, 1);
        line-height: 32px;
      }
      .enterDetail {
        margin-top: 25px;
        width: 100%;
        height: 20px;
        font-size: 18px;
        line-height: 20px;
        font-family: MicrosoftYaHei;
        font-weight: 400;
        color: rgba(255, 255, 255, 1);
        opacity: 0.6;
        filter: alpha(opacity=60); //filter 过滤器   兼容IE678
      }
      .warning {
        margin-top: 35px;
        width: 100%;
        height: 17px;
        font-size: 16px;
        text-align: center;
        font-family: MicrosoftYaHei;
        font-weight: 400;
        color: rgba(215, 0, 0, 1);
        line-height: 17px;
      }
      .loginData {
        margin-top: 38px;
        height: 152px;
        .el-form {
          height: 38px;
          .el-form-item {
            height: 57px;
            .el-form-item__label {
              height: 19px !important;
              line-height: 19px !important;
              font-size: 19px !important;
            }
          }
        }
      }
      .rememberMe {
        margin-top: 41px;
        height: 17px;
        line-height: 17px;
        font-size: 16px;
      }
      .submit {
        margin-top: 61px;
        font-size:16px;
        font-family:PingFangSC-Semibold;
        text-align: center;
        font-weight:600;
        width: 100%;
        color:rgba(254,254,254,1);
        line-height:63px;
        width:557px;
        height:63px;
        background:rgba(242,40,74,1);
        border-radius: 2px;
      }
      .forgetPW {
        margin-top: 40px;
        width:158px;
        height:20px;
        font-size:18px;
        line-height:20px;
        font-family:MicrosoftYaHei;
        font-weight:400;
        color:rgba(242,40,74,1);
      }
    }
  }
}
</style>

