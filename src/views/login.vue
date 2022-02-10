<template>
  <div class="out">
    
    <div class="box">
      <div class="head">
        <img src="../assets/logo.png" alt=""/>
      </div>
      
      <el-form
        :model="ruleForm"
        :rules="rules"
        ref="ruleForm"
        label-width="100px"
        class="demo-ruleForm"
      >
        <el-form-item label="用户名" prop="username">
          <el-input v-model="ruleForm.username"></el-input>
        </el-form-item>
        <el-form-item label="密码" prop="password">
          <el-input v-model="ruleForm.password"></el-input>
        </el-form-item>
      </el-form>
      <el-button type="success" class="login" @click="login">登录</el-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {},
  data() {
    return {
      ruleForm: {
          username: '',
          password:"",
      },
      rules: {
          username: [
            { required: true, message: '请输入用户名', trigger: 'blur' },
            { min: 1, max: 9, message: '长度在 1 到 9 个字符', trigger: 'blur' }
          ],
          password: [
            { required: true, message: '请输入密码', trigger: 'blur' },
            { min: 6, max: 18, message: '长度在 6 到 18 个字符', trigger: 'blur' }
          ],
      }
    };
  },
  methods: {
    login(){
      this.$router.push('index')
    }
  },
  components: {},
  mounted() {

  },
};
</script>

<style scoped lang="scss">
  .out{
    position: fixed;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: #B3C0D1;
    .box{
      position: relative;
      width: 500px;
      height: 350px;
      margin: 200px 0 0 50%;
      transform: translate(-50%);
      background: #fff;
      padding: 100px 30px 0 0;
      border-radius: 10px;
      ::v-deep .el-form-item__label{
        width: 80px !important;
      }
      .login{
        float: right;
      }
      >.head{
        width: 100px;
        height: 100px;
        border-radius: 50%;
        border: 5px solid #222;
        position: absolute;
        left: 50%;
        transform: translate(-50%);
        top: -50px;
        overflow: hidden;
        img{
          width: 75%;
          height: 75%;
          margin: 50% 0 0 50%;
          transform: translate(-50%,-50%);
        }
      }
    }
  }
  
</style>
