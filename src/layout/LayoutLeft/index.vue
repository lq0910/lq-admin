<!-- 左侧菜单模式:left -->
<template>
	<el-container class="le-layout-wrap--left">
		<el-aside class="le-layout-aside">
			<div class="aside-box" :style="{ width: isCollapse ? '65px' : '210px' }">
				<div class="logo">
					<!--          <SvgIcon class="logo-img sidebar-logo" icon-class="logo" />-->
					<img class="logo-img" src="/logo.png" alt="logo" />
					<span v-show="!isCollapse" class="text-overflow_ellipsis logo-text" :title="title">{{ title }}</span>
				</div>
				<el-scrollbar>
					<el-menu
						class="layout-menu-wrap"
						:router="false"
						:default-active="activeMenu"
						:collapse="isCollapse"
						:unique-opened="accordion"
						:collapse-transition="false"
					>
						<SubMenu :menu-list="menuList" />
					</el-menu>
				</el-scrollbar>
			</div>
		</el-aside>
		<el-container>
			<el-header class="le-layout-header">
				<ToolBarLeft />
				<ToolBarRight />
			</el-header>
			<AppMain />
		</el-container>
	</el-container>
</template>

<script setup lang="ts" name="layoutLeft">
import { computed } from 'vue'
import { useRoute } from 'vue-router'
import ToolBarLeft from '@/layout/components/Header/ToolBarLeft.vue'
import ToolBarRight from '@/layout/components/Header/ToolBarRight.vue'
import SubMenu from '@/layout/components/Menu/SubMenu.vue'
import AppMain from '@/layout/components/AppMain.vue'
import useStore from '@/store'

const title = import.meta.env.VITE_APP_TITLE

const route = useRoute()
const { permission, setting } = useStore()
const accordion = computed(() => setting.accordion)
const isCollapse = computed(() => setting.isCollapse)

const menuList = computed(() => permission.showMenuList)
const activeMenu = computed(() => (route.meta.activeMenu ? route.meta.activeMenu : route.path) as string)
</script>

<style lang="scss">
@import './index.scss';
</style>
