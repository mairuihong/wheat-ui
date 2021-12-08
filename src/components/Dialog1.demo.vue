<demo>
常规使用
</demo>

<template>
  <div>
    <Button level="main" @click="toggle">打开对话框</Button>
    <Dialog v-model:visible="showDialog">
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
    return {
      showDialog,
      toggle,
    };
  },
};
</script>