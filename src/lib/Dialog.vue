<template>
  <template v-if="visible">
    <Teleport to='body'>
      <div class="wheat-dialog-overlay" @click="onClickOverlay"></div>
      <div class="wheat-dialog-wrapper">
        <div class="wheat-dialog">
          <header>
            <slot name="title"/>
            <span @click="close" class="wheat-dialog-close"></span>
          </header>
          <main>
            <slot name="content"/>
          </main>
          <footer v-show="addButton">
            <Button level="main" @click="ok">OK</Button>
            <Button @click="cancel">Cancel</Button>
          </footer>
        </div>
      </div>
    </Teleport>
  </template>
</template>

<script lang="ts">
import Button from './Button.vue';

export default {
  props: {
    title: {
      type: String,
      default: '提示'
    },
    visible: {
      type: Boolean,
      default: false
    },
    closeOnClick: {
      type: Boolean,
      default: true
    },
    addButton: {
      type: Boolean,
      default: false
    },
    ok: {
      type: Function
    },
    cancel: {
      type: Function
    }
  },
  components: {
    Button
  },
  setup(props, context) {
    const close = () => {
      context.emit('update:visible', false);
    };
    const onClickOverlay = () => {
      if (props.closeOnClick) {
        close();
      }
    };
    const ok = () => {
      if (props.ok?.() !== false) {// props.ok && props.ok() !== false
        close();
      }
    };
    const cancel = () => {
      props.cancel?.(); // props.cancel && props.cancel()
      close();
    };
    return {
      close,
      onClickOverlay,
      ok,
      cancel
    };
  }
};
</script>

<style lang="scss">
$radius: 4px;
$border-color: #d9d9d9;
.wheat-dialog {
  background: white;
  border-radius: $radius;
  box-shadow: 0 0 3px fade_out(black, 0.5);
  min-width: 15em;
  max-width: 90%;
  &-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: fade_out(black, 0.5);
    z-index: 10;
  }
  &-wrapper {
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 11;
  }
  > header {
    padding: 12px 16px;
    border-bottom: 1px solid $border-color;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 20px;
  }
  > main {
    padding: 12px 16px;
  }
  > footer {
    border-top: 1px solid $border-color;
    padding: 12px 16px;
    text-align: right;
  }
  &-close {
    position: relative;
    display: inline-block;
    width: 24px;
    height: 24px;
    border-radius: 12px;
    cursor: pointer;
    &::before,
    &::after {
      content: '';
      position: absolute;
      width: 60%;
      height: 1px;
      background: black;
      top: 50%;
      left: 50%;
    }
    &::before {
      transform: translate(-50%, -50%) rotate(-45deg);
    }
    &::after {
      transform: translate(-50%, -50%) rotate(45deg);
    }
  }
}
.wheat-dialog-close:hover {
  background: $border-color;
}
</style>