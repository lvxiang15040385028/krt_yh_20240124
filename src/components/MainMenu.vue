<template>
  <el-menu
    :default-active="defaultActive"
    class="el-menu-vertical-demo"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b"
    @select="handleSelect"
  >
    <el-menu-item index="Home">
      <i class="el-icon-menu"></i>
      <span slot="title">导航一</span>
    </el-menu-item>
    <el-submenu index="2">
      <template slot="title">
        <i class="el-icon-location"></i>
        <span>导航二</span>
      </template>
      <el-menu-item index="Page1">选项1-1</el-menu-item>
      <el-menu-item index="Page2">选项1-2</el-menu-item>
      <el-menu-item index="1-3">选项1-3</el-menu-item>
      <el-submenu index="1-4">
        <template slot="title">选项1-4</template>
        <el-menu-item index="1-4-1">选项1-4-1</el-menu-item>
      </el-submenu>
    </el-submenu>
    <el-menu-item index="3" disabled>
      <i class="el-icon-document"></i>
      <span slot="title">导航三</span>
    </el-menu-item>
    <el-menu-item index="4">
      <i class="el-icon-setting"></i>
      <span slot="title">导航四</span>
    </el-menu-item>
  </el-menu>
</template>
<script>
export default {
  data() {
    return {
      defaultActive: ''
    }
  },
  methods: {
    handleSelect(key) {
      if (this.$route.name != key) {
        console.log(key)
        this.$router.replace({ name: key })
      } else {
        console.log('就是当前页面刷新还是干啥')
      }
    }
  },
  mounted() {
    //console.log('---加载完成')
    const defaultActive = 'Page1'
    if (this.$route.name != defaultActive) {
      this.defaultActive = 'Page1'
      this.$router.replace({ name: this.defaultActive })
    }
  }
}
</script>
<style lang="scss"></style>
