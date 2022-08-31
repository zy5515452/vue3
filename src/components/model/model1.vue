<!--
 @Author: zhuangyu
 @Date: **** 年 ** 月 ** 日 ** : ** : **
 @Desc: ****
-->
<template>
  <div>
    <el-row>
      <el-form :model="form" ref="Form" label-width="120px">
        <el-form-item label="姓名：">
          <el-input v-model="form.name" />
        </el-form-item>
        <el-form-item label="电话：">
          <el-input v-model="form.phone" />
        </el-form-item>
        <el-form-item label="内容：">
          <el-input v-model="form.content" />
        </el-form-item>
        <el-form-item label="文字：">
          <el-input v-model="form.text" />
        </el-form-item>
      </el-form>
    </el-row>
    <el-table :data="tableData" border style="width: 100%">
      <el-table-column prop="date" label="Date" width="180" />
      <el-table-column prop="name" label="Name" width="180" />
      <el-table-column prop="address" label="Address" />
    </el-table>
    <h2>{{list}}</h2>
    <h2>{{id}}</h2>
    <el-button type="primary" @click="add">Primary</el-button>
    <el-button type="primary" @click="del">del按钮</el-button>
  </div>
</template>

<script setup>
import { ElRow, ElForm, ElFormItem, ElInput, ElButton, ElTable, ElTableColumn} from "element-plus";
import { reactive, defineExpose, defineProps, toRefs, defineEmits } from 'vue'
const props = defineProps({
  list: {
    type: String,
    default: ''
  },
  id: {
    type: [String, Number],
    default: ''
  }
})
const emit = defineEmits()
const { list, id } = toRefs(props)
const tableData = [
  {
    date: '2016-05-03',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-02',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-04',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
  {
    date: '2016-05-01',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  },
]
const form = reactive({
  name: '',
  phone: '',
  content: '',
  text: '',
})
const changeData = () => {
  console.log(form);
  return form
}
console.log(list.value);
console.log(id.value);
const del = () => {
  emit('del', form)
}
const add = () => {
  emit('addForm', form)
}
defineExpose({
  changeData
})

</script>

<style scoped></style>