<demo>
支持 OK 和 Cancel 按钮
</demo>

<template>
  <div>
    <Button level="main" @click="toggle">打开对话框</Button>
    <Dialog
        v-model:visible="showDialog"
        add-button
        :ok="f1"
        :cancel="f2"
    >
      <template v-slot:title>
        可自定义标题
      </template>
      <template v-slot:content>
        <p>可自定义内容</p>
        <strong>可自定义内容</strong>
      </template>
    </Dialog>
  </div>
</template>

<script lang="ts">
import Dialog from '../lib/Dialog.vue';
import Button from '../lib/Button.vue';
import {ref} from 'vue';

export default {
  components: {
    Dialog,
    Button,
  },
  setup() {
    const showDialog = ref(false);
    const toggle = () => {
      showDialog.value = !showDialog.value;
    };
    const f1 = () => {console.log('ok')};
    const f2 = () => {console.log('cancel')};
    return {
      showDialog,
      toggle,
      f1,
      f2,
    };
  },
};
</script>