<script setup>
import { ref } from "vue";

defineProps({});

const count = ref(0);

import { reactive } from "vue";

// do not use same name with ref
const form = reactive({
  name: "",
  region: "",
  date1: "",
  date2: "",
  delivery: false,
  type: [],
  resource: "",
  desc: "",
});

const onSubmit = () => {
  console.log("submit!");
};

const value = ref("");
const value1 = ref("");
const value2 = ref("");
const options = [
  {
    value: "Option1",
    label: "Option1",
  },
  {
    value: "Option2",
    label: "Option2",
  },
  {
    value: "Option3",
    label: "Option3",
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
    value: "Option1",
    label: "Option1",
  },
  {
    value: "Option2",
    label: "Option2",
  },
  {
    value: "Option3",
    label: "Option3",
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
          </el-row>
        </el-col>
      </el-row>
    </div>

    <div
      style="
        left: 47px;
        top: 598px;
        width: 359px;
        height: 46px;
        color: rgba(56, 56, 56, 1);
        font-size: 40px;
        position: relative;
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
        position: relative;
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
        position: relative;
      "
    >
      信息确认
    </div>

    <div class="elmain">
      <el-form ref="formRef" :model="form" label-width="120px">
        <el-form-item label="真实姓名" size="large">
          <el-input
            v-model="form.name"
            size="large"
            placeholder="请输入真实姓名"
          ></el-input>
        </el-form-item>
        <el-form-item label="基本信息" size="large">
          <el-select
            v-model="value"
            class="m-2"
            placeholder="出生年份"
            size="large"
          >
            <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            >
            </el-option>
          </el-select>
          <el-select
            v-model="value1"
            class="m-2"
            placeholder="Select"
            size="large"
          >
            <el-option
              v-for="item in options1"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            >
            </el-option>
          </el-select>
          <el-select
            v-model="value2"
            class="m-2"
            placeholder="Select"
            size="large"
          >
            <el-option
              v-for="item in options2"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            >
            </el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="身份证号" size="large">
          <el-input
            v-model="form.name"
            size="large"
            placeholder="请输入身份证号"
          ></el-input>
        </el-form-item>
        <el-form-item label="手机号码" size="large">
          <el-input
            v-model="form.name"
            size="large"
            placeholder="请输入手机号码"
          ></el-input>
        </el-form-item>
        <el-form-item label="手机验证码" size="large">
          <el-input
            v-model="form.name"
            size="large"
            placeholder="请输入手机验证码"
          ></el-input>
        </el-form-item>

        <el-form-item>
          <el-button type="primary" @click="onSubmit">立即认证</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<style scoped>
.total {
  left: 2602px;
  top: 3991px;
  width: 1440px;
  height: 1392px;
  background-color: rgba(229, 229, 229, 1);
  margin: 0 auto;
}
.elheader {
  left: 0px;
  top: 0px;
  width: 1440px;
  height: 115px;
  background-color: rgba(255, 255, 255, 1);
  padding: 0;
  position:relative
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
  left: 755px;
  top: 160px;
  width: 901px;
  height: 1168px;
  background-color: rgba(255, 255, 255, 1);
  position: absolute;
  padding: 50px;
  box-sizing: border-box;
}
</style>
