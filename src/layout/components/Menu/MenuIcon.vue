<script setup lang="ts" name="MenuIcon">
import { computed } from 'vue'
const props = defineProps({
	iconClass: {
		type: String,
		required: false
	},
	color: {
		type: String,
		default: ''
	}
})
const icon = computed(() => {
	const iconClass = props.iconClass || ''
	let type = {
		// 来自于 src/assets/icons 的svg: 'icon-[dir]-[name]'
		icon: 'icon',
		// 来自于 iconfont svg 链接: 'le-[name]'
		le: 'iconfont'
		// // 来自于 element svg 链接: 'el-[name]' => 实际icon name为： [name] el-仅用于标记
		// el: 'element'
	}[iconClass.split('-')[0]]
	// 匹配不到icon- & le- 默认element
	if (!type) type = 'element'
	let component = iconClass
	// if (type === 'element') {
	// 	component = iconClass.replace('el-', '')
	// }
	// console.error(component, 'components.....')
	return {
		type,
		component
	}
})
const colorStyle = computed(() => {
	return props.color ? `color: ${props.color}` : ''
})
</script>

<template>
	<template v-if="icon.type === 'element'">
		<component :is="icon.component" class="menu-icon" :style="colorStyle" />
	</template>
	<LeIcon v-else :icon-class="icon.component" class="menu-icon" :color="color" />
</template>

<style scoped lang="scss">
.le-pick-icon {
	width: 1em;
	height: 1em;
	vertical-align: -0.15em;
	fill: currentColor;
	overflow: hidden;
	&:focus {
		outline: unset;
	}
}
</style>
