<template>
  <el-row class="tac">
    <el-col>
      <el-menu
        default-active="2"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
      >
        <el-sub-menu index="1">
          <template #title>
            <el-icon><location /></el-icon>
            <span>Navigator One</span>
          </template>
          <el-menu-item index="1-1">item one</el-menu-item>
          <el-menu-item index="1-2">item two</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="1">
          <template #title>
            <el-icon><setting /></el-icon>
            <span>Navigator Two</span>
          </template>
          <el-menu-item index="1-1">item one</el-menu-item>
          <el-menu-item index="1-2">item two</el-menu-item>
        </el-sub-menu>
      </el-menu>
    </el-col>
  </el-row>
</template>

<script>
import { Location, Setting } from "@element-plus/icons-vue";
import { reactive, toRefs } from "vue";

export default {
  name: "SideMenu",
  components: { Location, Setting },
  setup() {
    const state = reactive({
      menuItem: [
        {
          label: "코로나 현황 요약",
          index: "corona-briefing",
          icon: "location",
          submenus: [
            {
              label: "국가별 요약",
              index: "InternationalCases",
              path: "corona",
            },
            { label: "국내 요약", index: "DomesticCases", path: "corona" },
          ],
        },
        {
          label: "코로나 분석",
          index: "corona-analysis",
          icon: "setting",
          submenus: [
            {
              label: "샘플메뉴1",
              index: "InternationalCases",
              path: "corona",
            },
            { label: "샘플메뉴2", index: "DomesticCases", path: "corona" },
          ],
        },
      ],
    });
    return {
      ...toRefs(state),
    };
  },
};
</script>

<style>
.tac {
  height: 100%;
}

.el-menu {
  height: 100%;
}

.el-menu-item {
  height: 100%;
}
</style>
