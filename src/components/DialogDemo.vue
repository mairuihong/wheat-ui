<template>
  <div>
    Dialog 示例
  </div>
  <h1>示例1</h1>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="visible"  :closeOnClickOverlay="false" :ok="f1" :cancel="f2">
    <template v-slot:title>
      <strong>加粗的标题</strong>
    </template>
    <template v-slot:content>
      <div>hi</div>
      <div>hi2</div>
    </template>
  </Dialog>
  <h1>示例2</h1>
  <Button @click="showDialog">show</Button>
</template>

<script lang='ts'>
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue'
import {ref} from 'vue'
import {openDialog} from '../lib/openDialog'
export default {
  components: {
    Dialog,
    Button
  },
  setup() {
    const visible = ref(false)
    const toggle = (()=>{
      visible.value = !visible.value
    })
    const f1 = () => {
      return false
    }
    const f2 = () => {
    }
    const showDialog = ()=>{
      openDialog({
        title: '标题',
        content: '你好',
        ok() {
          console.log('ok')
        },
        cancel() {
          console.log('cancel')
        }
      })
    }
    return {visible, toggle, f1, f2, showDialog}
  }
}
</script>