<template>
  <div class="home">
    <tj-row>
      <tj-col :span="12">
        <div class="bgc">A</div>
      </tj-col>
      <tj-col :span="12">
        <div class="bgc">B</div>
      </tj-col>
    </tj-row>
    <tj-row>
      <tj-col :span="8">A</tj-col>
      <tj-col :span="8">B</tj-col>
      <tj-col :span="8">C</tj-col>
    </tj-row>
    <tj-row :gutter="100">
      <tj-col :span="24">C</tj-col>
    </tj-row>
    <tj-row>
      <tj-col :span="6">A</tj-col>
      <tj-col :span="6">A</tj-col>
      <tj-col :span="6">A</tj-col>
      <tj-col :span="6">A</tj-col>
    </tj-row>
    <hr />
    <tj-row :gutter="50">
      <tj-col :span="12">
        <div class="bgc">B</div>
      </tj-col>
      <tj-col :span="12">
        <div class="bgc">A</div>
      </tj-col>
    </tj-row>
    <tj-row :gutter="100">
      <tj-col :span="8">
        <div class="bgc">A</div>
      </tj-col>
      <tj-col :span="8">
        <div class="bgc">B</div>
      </tj-col>
      <tj-col :span="8">
        <div class="bgc">C</div>
      </tj-col>
    </tj-row>
    <tj-row :gutter="100">
      <tj-col :span="6">
        <div class="bgc">A</div>
      </tj-col>
      <tj-col :span="6">
        <div class="bgc">B</div>
      </tj-col>
      <tj-col :span="6">
        <div class="bgc">C</div>
      </tj-col>
      <tj-col :span="6">
        <div class="bgc">C</div>
      </tj-col>
    </tj-row>
    <hr />
    <tj-row :gutter="100">
      <tj-col :span="6" :offset="6">
        <div class="bgc">A</div>
      </tj-col>

      <tj-col :span="6" :offset="6">
        <div class="bgc">C</div>
      </tj-col>
    </tj-row>
    <hr />
    <tj-row>
      <tj-col :span="6" :offset="6">
        <div class="bgc">A</div>
      </tj-col>
      <tj-col :span="6" :offset="6">
        <div class="bgc">C</div>
      </tj-col>
    </tj-row>
    <hr />
    <tj-row type="flex" justify="flex-end" :gutter="20">
      <tj-col :span="8">
        <div class="bgc">A</div>
      </tj-col>
      <tj-col :span="8">
        <div class="bgc">C</div>
      </tj-col>
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
.bgc {
  background-color: #ccc;
}
.home {
  width: 500px;
}
</style>
