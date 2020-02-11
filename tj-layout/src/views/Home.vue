<template>
  <div class="home">
    <tj-row>
      <tj-col :span="12">A</tj-col>
      <tj-col :span="12">B</tj-col>
    </tj-row>
    <tj-row>
      <tj-col :span="8">A</tj-col>
      <tj-col :span="8">B</tj-col>
      <tj-col :span="8">C</tj-col>
    </tj-row>
    <tj-row>
      <tj-col :span="6">A</tj-col>
      <tj-col :span="6">A</tj-col>
      <tj-col :span="6">A</tj-col>
      <tj-col :span="6">A</tj-col>
    </tj-row>
  </div>
</template>

<script>
import TjRow from "../components/tj-row";
import TjCol from "../components/tj-col";
export default {
  name: "Home",
  components: {
    TjRow,
    TjCol
  }
};
</script>

<style lang="scss">
.tj-row + .tj-row {
  margin-top: 10px;
}
</style>
