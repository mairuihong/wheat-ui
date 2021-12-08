<template>
  <div>
    <div class="title">Dialog示例</div>
    <div>
      <h2>
        <span>#</span>常规用法
      </h2>
      <p>
        使用 <span>v-model</span> 绑定 <span>Boolean</span> 打开和关闭对话框
      </p>
      <p>
        使用 <span>slot</span>（ <span>title</span> 和 <span>content</span> ）可自定义对话框中的标题和内容的样式
      </p>
      <Demo :component="Dialog1Demo"/>
    </div>
    <div>
      <h2>
        <span>#</span>支持点击遮罩层关闭
      </h2>
      <p>
        通过传入 <span>closeOnClick</span> 属性（不传入默认为 false），使对话框可以<span>点击遮罩层</span>关闭
      </p>
      <Demo :component="Dialog2Demo"/>
    </div>
    <div>
      <h2>
        <span>#</span>支持按钮
      </h2>
      <p>
        添加 <span>addButton</span> 属性，对话框底部增加 <span>OK</span> 和 <span>Cancel</span> 按钮
      </p>
      <p>
        同时可以传入 <span>ok</span> 和 <span>cancel</span> 函数，控制按钮的点击事件
      </p>
      <Demo :component="Dialog3Demo"/>
    </div>
    <div>
      <h2>
        <span>#</span>使用TS一次传入属性
      </h2>
      <p>
        使用<span> openDialog </span>一次性将对话框的属性传入
      </p>
      <Demo :component="Dialog4Demo"/>
    </div>
  </div>
</template>

<script lang='ts'>
import Demo from './Demo.vue';
import Dialog1Demo from './Dialog1.demo.vue';
import Dialog2Demo from './Dialog2.demo.vue';
import Dialog3Demo from './Dialog3.demo.vue';
import Dialog4Demo from './Dialog4.demo.vue';

export default {
  components: {
    Demo,
  },
  setup() {
    return {Dialog1Demo, Dialog2Demo, Dialog3Demo, Dialog4Demo};
  },
};
</script>
