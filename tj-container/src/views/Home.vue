<template>
  <div class="home">
    <tj-container>
      <tj-header>Header</tj-header>
      <tj-main>Main</tj-main>
    </tj-container>
    <hr />
    <tj-container>
      <tj-header>Header</tj-header>
      <tj-main>Main</tj-main>
      <tj-footer>Footer</tj-footer>
    </tj-container>
    <hr />
    <tj-container>
      <tj-aside width="200px">Aside</tj-aside>
      <tj-main>Main</tj-main>
    </tj-container>
    <hr />
    <tj-container>
      <tj-header>header</tj-header>
      <tj-container>
        <tj-aside>Aside</tj-aside>
        <tj-main>main</tj-main>
      </tj-container>
    </tj-container>
  </div>
</template>

<script>
import TjContainer from "../components/tj-container";
import TjAside from "../components/tj-aside";
import TjFooter from "../components/tj-footer";
import TjHeader from "../components/tj-header";
import TjMain from "../components/tj-main";
export default {
  name: "Home",
  components: {
    TjContainer,
    TjAside,
    TjFooter,
    TjHeader,
    TjMain
  }
};
</script>
<style lang="scss">
.tj-header,
.tj-footer {
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
  line-height: 60px;
}

.tj-aside {
  background-color: #d3dce6;
  color: #333;
  text-align: center;
  line-height: 200px;
}

.tj-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 160px;
}

body > .tj-container {
  margin-bottom: 40px;
}

// .tj-container:nth-child(5) .tj-aside,
// .tj-container:nth-child(6) .tj-aside {
//   line-height: 260px;
// }

// .tj-container:nth-child(7) .tj-aside {
//   line-height: 320px;
// }
</style>
