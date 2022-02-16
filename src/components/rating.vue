<script setup>
import { ref } from "vue";

defineProps({});

const count = ref(0);

import { reactive } from "vue";

// do not use same name with ref
const form = reactive({
  name: "",
  phone: "",
  identityNumber: "",
  verificationCode: "",
  date2: "",
  delivery: false,
  type: [],
  resource: "",
  desc: "",
});

const onSubmit = () => {
  console.log("submit!");
};

const onVerify = () => {
  console.log("Verify!");
};

const value = ref("");
const value1 = ref("");
const value2 = ref("");
const options = [
  {
    value: "1990",
    label: "1990",
  },
  {
    value: "1991",
    label: "1991",
  },
  {
    value: "1992",
    label: "1992",
  },
];
const options1 = [
  {
    value: "男",
    label: "男",
  },
  {
    value: "女",
    label: "女",
  },
];
const options2 = [
  {
    value: "山东省",
    label: "山东省",
  },
  {
    value: "江苏省",
    label: "江苏省",
  },
  {
    value: "河北省",
    label: "河北省",
  },
];
</script>

<template>
  <div class="total">
    <div class="elheader">
      <el-row>
        <el-col :span="24" class="htop"></el-col>
      </el-row>
      <el-row>
        <el-col :span="24" class="hmain">
          <el-row :gutter="1" justify="left">
            <el-col :span="2">创作灵感</el-col>
            <el-col :span="2">咖薄设计师</el-col>
            <el-col :span="2">资质认证</el-col>
            <el-col :span="2">作品鉴权</el-col>
            <el-col :span="4"></el-col>
            <el-col :span="4"></el-col>
            <el-col :span="4"></el-col>
            <el-col :span="2"></el-col>
            <el-col :span="2">王羲之</el-col>
          </el-row>
        </el-col>
      </el-row>
    </div>

    <div
      style="
        left: 147px;
        top: 598px;
        width: 160px;
        height: 46px;
        color: rgba(56, 56, 56, 1);
        font-size: 40px;
        font-family: 'siyuan';
        font-weight: bold;
        border-bottom: 2px solid #000;
        padding-bottom: 5px;
        position: absolute;
      "
    >
      实名认证
    </div>
    <div
      style="
        left: 147px;
        top: 672px;
        width: 85px;
        height: 30px;
        color: rgba(128, 128, 128, 1);
        font-size: 20px;
        font-family: 'siyuan';
        position: absolute;
      "
    >
      资质认证
    </div>
    <div
      style="
        left: 147px;
        top: 716px;
        width: 80px;
        height: 30px;
        color: rgba(128, 128, 128, 1);
        font-size: 20px;
        font-family: 'siyuan';
        position: absolute;
      "
    >
      信息确认
    </div>
    <div class="elmain">
      <el-form ref="formRef" :model="form" label-width="0px">
        <el-form-item class="inp">
          <div class="ftext">真实姓名</div>
          <el-input
            v-model="form.name"
            size="large"
            placeholder="请输入真实姓名"
            style="height: 66px; font-size: 24px"
          ></el-input>
        </el-form-item>
        <div class="ftext">基本信息</div>
        <el-form-item>
          <!-- <el-row :gutter="20">
            <el-col :span="6" -->
              <el-form-item>
                <el-select v-model="value" class="m-2" placeholder="出生年份">
                  <el-option
                    v-for="item in options"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value"
                    style="height: 66px; font-size: 24px; line-height: 66px"
                  ></el-option>
                </el-select> </el-form-item
            >
            <!-- </el-col> -->
            <!-- <el-col :span="6"> -->
              <el-form-item>
                <el-select v-model="value1" class="m-2" placeholder="性别">
                  <el-option
                    v-for="item in options1"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value"
                    style="height: 66px; font-size: 24px; line-height: 66px"
                  ></el-option>
                </el-select>
              </el-form-item>
            <!-- </el-col> -->
            <!-- <el-col :span="12"> -->
              <el-form-item class="diqu">
                <el-select v-model="value2" class="m-2" placeholder="地区">
                  <el-option
                    v-for="item in options2"
                    :key="item.value"
                    :label="item.label"
                    :value="item.value"
                    style="height: 66px; font-size: 24px; line-height: 66px"
                  ></el-option>
                </el-select>
              </el-form-item>
            <!-- </el-col>
          </el-row> -->
        </el-form-item>
        <el-form-item size="large" class="inp">
          <div class="ftext">身份证号</div>
          <el-input
            v-model="form.identityNumber"
            size="large"
            placeholder="请输入身份证号"
            style="height: 66px; font-size: 24px"
          ></el-input>
        </el-form-item>
        <el-form-item size="large" class="inp">
          <div class="ftext">手机号码</div>
          <el-input
            v-model="form.phone"
            size="large"
            placeholder="请输入手机号码"
            style="height: 66px; font-size: 24px"
          ></el-input>
        </el-form-item>
        <el-form-item size="large" class="inp">
          <div class="ftext">手机验证码</div>
          <el-input
            v-model="form.verificationCode"
            size="large"
            placeholder="请输入手机验证码"
            style="height: 66px; font-size: 24px"
          >
          </el-input>
        </el-form-item>

        <el-form-item class="but">
          <el-button type="certification" @click="onSubmit">立即认证</el-button>
        </el-form-item>
        <el-form-item class="but ver">
          <el-button type="ver" @click="onVerify">获取验证码</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<style lang=scss scoped>
.total {
  /* left: 2602px;
  top: 3991px; */
  width: 1440px;
  height: 1392px;
  background-color: rgba(229, 229, 229, 1);
  margin: 0 auto;
  position: relative;
}
.elheader {
  left: 0px;
  top: 0px;
  width: 1440px;
  height: 115px;
  background-color: rgba(255, 255, 255, 1);
  padding: 0;
}
.htop {
  left: 0px;
  top: 0px;
  width: 1440px;
  height: 35px;
  background-color: rgba(0, 0, 0, 1);
}
.hmain {
  left: 0px;
  top: 35px;
  width: 1440px;
  height: 80px;
  background-color: rgba(33, 33, 33, 1);
  text-align: center;
  line-height: 80px;
  color: white;
}
.elmain {
  left: 455px;
  top: 160px;
  width: 901px;
  height: 1168px;
  background-color: rgba(255, 255, 255, 1);
  position: absolute;
  padding: 50px;
  box-sizing: border-box;
}
.ftext {
  font-weight: bold;
  margin: 25px 25px 25px 0px;
  text-align: left;
  width: 230px;
  height: 35px;
  color: rgba(51, 51, 51, 1);
  font-size: 24px;
}

.inp ::v-deep .el-input__inner {
  border: 0;
  width: 780px;
  height: 66px;
  background-color: rgba(255, 255, 255, 1);
  border: 2px solid rgba(240, 240, 240, 1);
  border-radius: 7px;
  &::placeholder {
    width: 420px;
    height: 36px;
    color: rgba(192, 196, 204, 1);
    font-size: 24px;
    /* font-weight: 500; */
  }
}
.elmain ::v-deep .el-select{
  margin-right:11px ;
}
.elmain ::v-deep .el-select .el-input__inner {
  /* border:0; */
  width: 152px;
  height: 66px;
  background-color: rgba(255, 255, 255, 1);
  border: 2px solid rgba(240, 240, 240, 1);
  border-radius: 7px;
  font-size: 24px;
   &::placeholder {
    width: 420px;
    height: 36px;
    color: rgba(192, 196, 204, 1);
    font-size: 24px;}
}
.elmain ::v-deep .diqu .el-select .el-input__inner {
  /* border:0; */
  width: 455px;
}
.but ::v-deep .el-button--certification {
  width: 135px;
  height: 46px;
  background-color: rgba(128, 128, 128, 1);
  border-radius: 1.94px;
  color: rgba(255, 255, 255, 1);
  font-size: 24px;
  line-height: 46px;
  margin-top: 60px;
  position: relative;
}
.but ::v-deep .el-button--ver {
  width: 135px;
  height: 46px;
  background-color: rgba(128, 128, 128, 1);
  border-radius: 1.94px;
  color: rgba(255, 255, 255, 1);
  font-size: 24px;
  line-height: 46px;
  position: absolute;
  left: 631px;
  bottom: 155px;
}
</style>
