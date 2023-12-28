<template>
  <el-container class="main">
    <el-header><BasicHeader /></el-header>
    <el-container>
      <el-aside width="200px"><SideMenu /></el-aside>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
import BasicHeader from "./BasicHeader.vue";
import SideMenu from "./SideMenu.vue";

export default {
  name: "basicLayout",
  components: { BasicHeader, SideMenu },
};
</script>
<style>
.el-header {
  background: #409eff;
  color: #fff;
  display: flex;
  align-items: center;
}
.main {
  height: 100%;
}
</style>
