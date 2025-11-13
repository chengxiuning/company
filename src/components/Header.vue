<template>
  <el-header class="header">
    <div class="header-container">
      <div class="logo">
        <h1>企业品牌</h1>
      </div>
      <el-menu
        :default-active="activeIndex"
        class="nav-menu"
        mode="horizontal"
        :ellipsis="false"
        @select="handleSelect"
      >
        <el-menu-item index="home">首页</el-menu-item>
        <el-menu-item index="about">关于我们</el-menu-item>
        <el-menu-item index="products">产品服务</el-menu-item>
        <el-menu-item index="contact">联系我们</el-menu-item>
      </el-menu>
    </div>
  </el-header>
</template>

<script setup>
import { ref, watch } from 'vue'
import { useRouter, useRoute } from 'vue-router'

const router = useRouter()
const route = useRoute()
const activeIndex = ref('home')

watch(() => route.name, (newName) => {
  if (newName) {
    activeIndex.value = newName.toLowerCase()
  }
}, { immediate: true })

const handleSelect = (key) => {
  router.push(`/${key === 'home' ? '' : key}`)
}
</script>

<style scoped>
.header {
  background: #fff;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
  padding: 0;
  height: 70px;
  position: sticky;
  top: 0;
  z-index: 1000;
}

.header-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100%;
  padding: 0 20px;
}

.logo h1 {
  font-size: 24px;
  color: #409eff;
  font-weight: 600;
  margin: 0;
}

.nav-menu {
  border-bottom: none;
  flex: 1;
  justify-content: flex-end;
}

:deep(.el-menu-item) {
  font-size: 16px;
  font-weight: 500;
}

:deep(.el-menu-item.is-active) {
  color: #409eff;
  border-bottom-color: #409eff;
}
</style>

