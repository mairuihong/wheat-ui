<template>
  <div>
    <div class="title">Button示例</div>
    <div>
      <h2>
        <span>#</span>常规用法
      </h2>
      <p>
        使用<span>theme</span>属性控制<span>Button</span>的样式
      </p>
      <Demo :component="Button1Demo" />
    </div>
    <div>
      <h2>
        <span>#</span>支持控制size
      </h2>
      <p>
        使用<span>size</span>属性控制<span>Button</span>的大小
      </p>
      <Demo :component="Button2Demo" />
    </div>
    <div>
      <h2>
        <span>#</span>支持level
      </h2>
      <p>
        使用<span>level</span>属性控制<span>Button</span>的类型
      </p>
      <Demo :component="Button3Demo" />
    </div>
    <div>
      <h2>
        <span>#</span>支持level
      </h2>
      <p>
        使用<span>disabled</span>属性可<span>禁用Button</span>按钮
      </p>
      <Demo :component="Button4Demo" />
    </div>
    <div>
      <h2>
        <span>#</span>支持level
      </h2>
      <p>
        使用<span>loading</span>属性控制<span>Button</span>处于加载状态
      </p>
      <Demo :component="Button5Demo" />
    </div>
  </div>
</template>

<script lang='ts'>
import Demo from "./Demo.vue";
import Button1Demo from "./Button1.demo.vue";
import Button2Demo from "./Button2.demo.vue";
import Button3Demo from "./Button3.demo.vue";
import Button4Demo from "./Button4.demo.vue";
import Button5Demo from "./Button5.demo.vue";
export default {
  components: { Demo },
  setup() {
    return { Button1Demo, Button2Demo, Button3Demo, Button4Demo, Button5Demo };
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