<template>
  <div class="fu">
    <button class="button">你好啊</button>
    <TestA></TestA>
    <TestC></TestC>
  </div>
  <!-- 
    1.如果所有的父子组件都没有scoped作用域。也就是不会打上data-v唯一作用域标签
        那么所有的css样式都是全局的。会出现样式的覆盖.父元素盖住子元素的
    2.如果父scoped 。子没有scoped 。 父组件的样式将独立唯一，不会影响子组件
      会在当前加入scoped的组件中的所有css打上作用域标签。 子组件的根节点也会打上唯一作用域
      但是子组件中的其它标签没有关系。所以隶属于同一个父组件的两个子组件仍然会出现样式冲突。
    3. 子组件的scoped并不能阻止父组件的修改
   -->
</template>

<script>
import TestC from "../components/TestC";
import TestA from "../components/TestA";
export default {
  created() {
    console.log("触发");
  },
  components: {
    TestC,
    TestA
  }
};
</script>

<style lang="scss">
// 如何解除组件中某个css样式的scoped
// >>> /deep/ vue-cli3.0不能使用/deep/  所以你必须使用 ::v-deep
.fu {
  .button {
    width: 800px;
    height: 800px;
  }
}
</style>
