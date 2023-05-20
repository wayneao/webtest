<script setup>
import { RouterView } from 'vue-router'
import Menu from './components/Menu.vue'
import { darkTheme, lightTheme } from 'naive-ui'
</script>

<template>
  <n-config-provider :theme="lightTheme">
    <n-global-style />
    <n-message-provider>
      <content />
    </n-message-provider>
    <n-layout>
      <n-layout-header id="header" bordered>
        <Menu />
      </n-layout-header>
      <n-layout-content class="content">
        <RouterView />
      </n-layout-content>
    </n-layout>
    <n-watermark
      content="仅供测试用途@neko"
      cross
      fullscreen
      :font-size="16"
      :line-height="18"
      :width="384"
      :height="384"
      :x-offset="12"
      :y-offset="128"
      :rotate="-15"
    />
  </n-config-provider>
</template>

<style scoped>
#header {
  display: flex;
  justify-content: center;
}

.content {
  padding: 2rem;
}

.fullscreen-layout {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.fullscreen-items {
  flex: 1 0 auto;
}
</style>
