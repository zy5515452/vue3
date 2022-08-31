<!--
 @Author: zhuangyu
 @Date: **** 年 ** 月 ** 日 ** : ** : **
 @Desc: ****
-->
<template>
  <div>
    <el-row class="mb-4">
      <el-button>Default</el-button>
      <el-button type="primary" @click="changeData">Primary</el-button>
      <el-button type="success" @click="goA">Success</el-button>
      <el-button type="info">Info</el-button>
      <el-button type="warning">Warning</el-button>
      <el-button type="danger">Danger</el-button>
      <el-button>中文</el-button>
    </el-row>
    <model ref="model1" :list="str" :id="123" @addForm="addForm" @del="del"></model>
  </div>
</template>

<script setup>
  import { ElButton, ElRow, ElForm, ElFormItem, ElInput, } from "element-plus";
  import model from "../components/model/model1"
  import { ref, onMounted } from 'vue'
  import {useRouter} from 'vue-router'
  // function infoData()  {
  //   console.log('执行');
  //   initData()
  // }
  const model1 = ref()
  const str = '哈哈哈哈'
  const router = useRouter()
  onMounted(() => {
    initData()
  })
  const initData = () => {
    console.log('获取数据');
  }
  const changeData = () => {
    let from = null
    from = model1.value.changeData()
    console.log(from);
  }
  const addForm = (form) => {
    console.log(form);
  }
  const del = (form) => {
    console.log(form);
  }
  const goA = () => {
    router.push({path: '/about'})
  }

  // infoData()

</script>

<style scoped></style>