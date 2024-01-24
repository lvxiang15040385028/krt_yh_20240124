<template>
  <div class="main-box">
    <div class="main-menu">
      <el-scrollbar>
        <MainMenu />
      </el-scrollbar>
    </div>
    <div class="main-top"></div>
    <div class="main-page">
      <router-view />
      <Page1 />
    </div>
  </div>
</template>
<script>
import MainMenu from './components/MainMenu.vue'
import Page1 from './views/Page1.vue'
export default {
  components: {
    MainMenu,
    Page1
  }
}
</script>

<style lang="scss">
.main-box {
  width: 100%;
  height: 30%;
  position: relative;
}
.main-menu {
  width: 201px;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgb(200, 200, 200);
}
.main-menu .el-scrollbar {
  width: 100%;
  height: 100%;
}
.main-menu .el-scrollbar__wrap {
  overflow-x: hidden;
}
.main-top {
  width: calc(100% - 201px);
  height: 56px;
  position: absolute;
  top: 0;
  right: 0;
  background-color: rgb(190, 255, 255);
}
.main-page {
  width: calc(100% - 201px);
  height: calc(100% - 56px);
  position: absolute;
  bottom: 0;
  right: 0;
  background-color: rgb(255, 190, 255);
  overflow: hidden;
}
</style>
