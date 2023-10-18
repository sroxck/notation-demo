<!--
 * @Author: sroxck
 * @Date: 2023-10-18 14:25:44
 * @LastEditors: sroxck
 * @LastEditTime: 2023-10-18 14:45:14
 * @Description: 
-->
<script setup lang="ts">
import { annotate } from 'rough-notation';
import { onMounted, ref } from 'vue';
const annotation = ref()
const annotation1 = ref()
const annotation2 = ref()
const annotation3 = ref()

onMounted(() => {
  const e = document.querySelector<HTMLElement>('#myElement')!
  annotation.value = annotate(e, { type: 'underline',color:'green' });
  const e1 = document.querySelector('#myElement1') as HTMLElement
  annotation1.value = annotate(e1, { type: 'circle' ,color:'blue'});
  const e2 = document.querySelector('#myElement2')  as HTMLElement
  annotation2.value = annotate(e2, { type: 'box',color:'yellow' });
  const e3 = document.querySelector('#myElement3')as HTMLElement
  annotation3.value = annotate(e3, { type: 'crossed-off',color:'red' });
})
const show = () => {
  annotation.value.show();
}
const show1 = () => {
  annotation1.value.show();
}
const show2 = () => {
  annotation2.value.show();
}
const show3 = () => {
  annotation3.value.show();
}
const reset = ()=>{
  annotation3.value.hide()
  annotation2.value.hide()
  annotation1.value.hide()
  annotation.value.hide()
}
</script>

<template>
  <div id="myElement">
    this is a test text  > underline effect
  </div>
  <button style="margin:30px" @click="show">show notation</button>
  <div id="myElement1">
    this is a test text > circle effect
  </div>
  <button style="margin:30px" @click="show1">show notation</button>
  <div id="myElement2">
    this is a test text > box effect
  </div>
  <button style="margin:30px" @click="show2">show notation</button>
  <div id="myElement3">
    this is a test text > crossed-off effect
  </div>
  <button style="margin:30px" @click="show3">show notation</button>
  <div>RESET ALL EFFECT </div>
  <button style="margin:30px" @click="reset">RESET</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
