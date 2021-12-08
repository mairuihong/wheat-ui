<template>
  <div>
    <div class="title">Switch组件示例</div>
    <div>
      <h2>
        <span>#</span>常规用法
      </h2>
      <p>
        使用<span>v-model</span>绑定<span>Boolean</span>控制开关的开合
      </p>
      <Demo :component="Switch1Demo" />
    </div>
    <div>
      <h2>
        <span>#</span>disabled用法
      </h2>
      <p>
        在组件中添加<span>disabled</span>属性，可<span>禁用Switch</span>组件
      </p>
      <Demo :component="Switch2Demo" />
    </div>
  </div>
</template>

<script lang="ts">
import Switch1Demo from "./Switch1.demo.vue";
import Switch2Demo from "./Switch2.demo.vue";
import Demo from "./Demo.vue";
export default {
  components: { Demo },
  setup() {
    return { Switch1Demo, Switch2Demo };
  },
};
</script>