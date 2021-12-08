<template>
  <div class="title">Tabs示例</div>
  <div>
    <h2>
      <span>#</span>常规用法
    </h2>
    <p>
      使用 <span>v-model</span> 绑定属性控制 <span>selected</span> 属性，展示选中的导航栏内容
    </p>
    <p>
      使用 <span>title</span> 属性自定义导航栏标题，导航栏内容直接写于 <span>Tab</span> 标签内
    </p>
    <Demo :component="Tabs1Demo" />
  </div>
</template>

<script lang="ts">
import Demo from "./Demo.vue";
import Tabs1Demo from "./Tabs1.demo.vue";
export default {
  components: {
    Demo,
  },
  setup() {
    return {
      Tabs1Demo,
    };
  },
};
</script>

<style lang="scss" scoped>
.title {
  font-size: 28px;
  margin-bottom: 12px;
}
h2 {
  font-size: 20px;
}
p {
  margin-left: 12px;
}
span {
  color: #ff9933;
  font-weight: 700;
}
</style>