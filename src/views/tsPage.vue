<!--
 @Author: zhuangyu
 @Date: **** 年 ** 月 ** 日 ** : ** : **
 @Desc: ****
-->
<template>
  <div>{{ num }}</div>
</template>

<script setup lang="ts">
import {prop} from "vue-class-component";

let num: number;
num = 10
interface Obj {
  name?: string,
  age?: number,
}
const obj:Obj  = {
  name: '222',
  age: 222
}

let obj1 : {
  name: string,
  age?: number
}
obj1 = {
  name: '1'
}
let obj2 : {
  name: string,
  [propName: string]: any
}
obj2 = {
  name: '2',
  age: 2
}

let fn : (val: string, val1: string) => string
fn = (val = '1', val1 = '3') => {
  return '123'
}
</script>

<style scoped></style>