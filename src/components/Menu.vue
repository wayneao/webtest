<script>
import { RouterLink, RouterView } from 'vue-router'
import { defineComponent, h } from 'vue'
import { NIcon } from 'naive-ui'
import {
  Home as IconHome,
  BarChart as IconChart,
  InformationCircle as IconAbout
} from '@vicons/ionicons5'

function renderIcon(icon) {
  return () => h(NIcon, null, { default: () => h(icon) })
}

function renderLable(path, label) {
  return () => h(RouterLink, { to: { path: path } }, { default: () => label })
}

const menuOptions = [
  {
    label: renderLable('/', '主页'),
    key: 'home',
    icon: renderIcon(IconHome)
  },
  {
    label: renderLable('/charts', '图表'),
    key: 'chart',
    icon: renderIcon(IconChart)
  },
  {
    label: renderLable('/about', '关于'),
    key: 'about',
    icon: renderIcon(IconAbout)
  }
]

export default defineComponent({
  setup() {
    return {
      menuOptions
    }
  }
})
</script>

<template>
  <n-menu mode="horizontal" :options="menuOptions" />
</template>
