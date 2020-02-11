<template>
  <div class="home">
    <div class="demo-button">
      <tj-button @click="chufa">默认按钮</tj-button>
      <tj-button type="primary">主要按钮</tj-button>
      <tj-button type="success">成功按钮</tj-button>
      <tj-button type="info">信息按钮</tj-button>
      <tj-button type="warning">警告按钮</tj-button>
      <tj-button type="danger">危险按钮</tj-button>
    </div>
    <div class="demo-button">
      <tj-button plain>默认按钮</tj-button>
      <tj-button type="primary" plain>主要按钮</tj-button>
      <tj-button type="success" plain>成功按钮</tj-button>
      <tj-button type="info" plain>信息按钮</tj-button>
      <tj-button type="warning" plain>警告按钮</tj-button>
      <tj-button type="danger" plain>危险按钮</tj-button>
    </div>
    <div class="demo-button">
      <tj-button plain round>默认按钮</tj-button>
      <tj-button type="primary" plain round>主要按钮</tj-button>
      <tj-button type="success" plain round>成功按钮</tj-button>
      <tj-button type="info" plain round>信息按钮</tj-button>
      <tj-button type="warning" plain round>警告按钮</tj-button>
      <tj-button type="danger" plain round>危险按钮</tj-button>
    </div>
    <div class="demo-button">
      <tj-button plain round circle></tj-button>
      <tj-button type="primary" plain round circle></tj-button>
      <tj-button type="success" plain round circle></tj-button>
      <tj-button type="info" plain round circle></tj-button>
      <tj-button type="warning" plain round circle></tj-button>
      <tj-button type="danger" plain round circle></tj-button>
    </div>
    <div class="demo-button">
      <tj-button plain round disabled></tj-button>
      <tj-button type="primary" plain round disabled></tj-button>
      <tj-button type="success" plain round disabled></tj-button>
      <tj-button type="info" plain round disabled></tj-button>
      <tj-button type="warning" plain round disabled></tj-button>
      <tj-button type="danger" plain round disabled></tj-button>
    </div>
    <div class="demo-button">
      <tj-button type="text" disabled>文字啊</tj-button>
      <tj-button type="text">1234</tj-button>
    </div>
    <hr />
    <div class="demo-button">
      <tj-button-group>
        <tj-button type="primary">上一页</tj-button>
        <tj-button type="primary">下一页</tj-button>
        <tj-button type="primary">下一页</tj-button>
      </tj-button-group>
    </div>
    <div class="demo-button">
      <tj-button-group>
        <tj-button type="warning">上一页</tj-button>
        <tj-button type="warning">下一页</tj-button>
      </tj-button-group>
    </div>
    <div class="demo-button">
      <tj-button-group>
        <tj-button type="primary">上一页</tj-button>
      </tj-button-group>
    </div>
    <hr />
    <div class="demo-button">
      <tj-button type="primary" disabled icon="el-icon-check">文字啊</tj-button>
      <tj-button type="primary" icon="el-icon-search">1234</tj-button>
    </div>
    <div class="demo-button">
      <tj-button type="primary" disabled :loading="true">文字啊</tj-button>
      <tj-button type="primary" :loading="true">1234</tj-button>
    </div>
    <div class="demo-button">
      <tj-button>默认按钮</tj-button>
      <tj-button size="medium">中等按钮</tj-button>
      <tj-button size="small">小型按钮</tj-button>
      <tj-button size="mini">超小按钮</tj-button>
    </div>
    <hr />
    <div class="demo-button">
      <tj-button>默认按钮</tj-button>
      <tj-button size="medium" native-type="button">中等按钮</tj-button>
      <tj-button size="small" native-type="submit">小型按钮</tj-button>
      <tj-button size="mini" autofocus native-type="reset">超小按钮</tj-button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import TjButton from "@/components/tj-button.vue";
import TjButtonGroup from "@/components/tj-button-group.vue";

export default {
  name: "Home",
  components: {
    TjButton,
    TjButtonGroup
  },
  methods: {
    /**
     * 没有使用.native原生修饰符。靠子组件触发这个自定义事件
     */
    chufa(event) {
      console.log("触发l ", event);
    }
  }
};
</script>

<style scoped lang="scss">
.demo-button .tj-button + .tj-button {
  margin-left: 10px;
  margin-top: 10px;
}
.demo-button {
  margin-top: 10px;
}
</style>
