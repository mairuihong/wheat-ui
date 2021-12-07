<template>
  <div class="homepage">
    <div class="topnavAndBanner">
      <div class="banner">
        <div class="logo-png">
          <img src="../assets/wheat.png" alt="wheat-UI">
        </div>
        <div class="details">
          <h1>Wheat UI</h1>
          <h2>一个厉害的 UI 框架</h2>
          <p class="actions">
            <a href="https://github.com/katawaredokiha/wheat-ui.git">GitHub</a>
            <router-link to="/doc">Get Started</router-link>
          </p>
        </div>
      </div>
    </div>
    <div class="features">
      <ul>
        <li>
          <svg>
            <use xlink:href="#icon-vue"></use>
          </svg>
          <h3>基于 Vue 3</h3>
          <p>使用了 Vue 3 Composition API</p>
        </li>
        <li>
          <svg>
            <use xlink:href="#icon-ts"></use>
          </svg>
          <h3>基于 TypeScript</h3>
          <p>源代码采用 TypeScript 书写</p>
        </li>
        <li>
          <svg>
            <use xlink:href="#icon-lights"></use>
          </svg>
          <h3>代码易读</h3>
          <p>每个组件的源代码都极其简洁</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import Topnav from '../components/Topnav.vue';

export default {
  components: {Topnav},
};
</script>

<style lang="scss" scoped>
.homepage {
  width: 100%;
  height: 100%;
  background-color: #FBAB7E;
  background-image: linear-gradient(45deg, #FBAB7E 0%, #F7CE68 100%);
}
.topnavAndBanner {
  display: flex;
  justify-content: center;
  align-content: flex-start;
}
.banner {
  background: rgba(255, 255, 255, 0.6);
  color: #ff9933;
  margin: 100px 150px;
  padding: 100px 0;
  width: 70vw;
  height: 60vh;
  max-width: 1000px;
  border-radius: 30px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  h1 {
    font-weight: 700;
    font-size: 48px;
  }
  h2 {
    font-size: 20px;
  }
  h1, h2 {
    text-align: center;
  }
  > .logo-png {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 24px;
    > img {
      width: 80%;
      height: auto;
    }
  }
  .actions {
    margin-top: 80px;
    padding: 8px 0;
    a {
      margin: 4px 8px;
      background: #8dcb76;
      color: white;
      display: inline-block;
      padding: 8px 24px;
      border-radius: 4px;
      &:hover {
        text-decoration: none;
      }
    }
  }
  @media (max-width: 1000px) {
    h1 {
      font-size: 32px;
    }
    > .logo-png {
      margin-right: 0px;
      > img {
        width: 75%;
        height: auto;
      }
    }
  }
  @media (max-width: 800px) {
    margin: 100px 24px;
    width: 100vw;
    > .logo-png {
      > img {
        width: 70%;
        height: auto;
      }
    }
  }
  @media (max-width: 500px) {
    margin: 20px 16px;
    padding: 40px;
    height: auto;
    flex-direction: column;
    > .logo-png {
      margin-bottom: 12px;
      > img {
        width: 60%;
        height: auto;
      }
    }
    .actions {
      margin-top: 12px;
    }
  }
}
.features {
  margin: 64px auto;
  padding: 0 16px;
  @media (max-width: 500px) {
    margin: 12px auto;
  }
  @media (min-width: 800px) {
    width: 800px;
    > ul {
      > li {
        width: 50%;
      }
    }
  }
  @media (min-width: 1200px) {
    width: 1200px;
    > ul {
      > li {
        width: 33.3333%;
      }
    }
  }
  > ul {
    display: flex;
    flex-wrap: wrap;
    > li {
      margin: 16px 0;
      display: grid;
      justify-content: start;
      align-content: space-between;
      grid-template-areas:
        "icon title"
        "icon text";
      grid-template-columns: 80px auto;
      grid-template-rows: 1fr auto;
      > svg {
        grid-area: icon;
        width: 64px;
        height: 64px;
      }
      > h3 {
        grid-area: title;
        font-size: 28px;
      }
      > p {
        grid-area: text;
      }
    }
  }
}
.icon {
  width: 1em;
  height: 1em;
  vertical-align: -0.15em;
  fill: currentColor;
  overflow: hidden;
}
</style>