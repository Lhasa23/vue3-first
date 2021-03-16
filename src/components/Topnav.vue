<template>
	<section class="topnav">
		<div class="logo">
			<div class="toggleAside" @click="toggleMenu"></div>
			LOGO
		</div>
		<ul class="menu">
			<li>菜单1</li>
			<li>菜单2</li>
		</ul>
	</section>
</template>

<script lang="ts">
	import { inject, Ref } from 'vue'

	export default {
		name: 'Topnav',
		setup () {
			const menuVisible = inject<Ref<Boolean>>('menuVisible')
			const toggleMenu = () => {
				menuVisible.value = !menuVisible.value;
			};
			return { toggleMenu };
		}
	}
</script>

<style lang="scss" scoped>
	.topnav {
		background: pink;
		display: flex;
		padding: 16px 20px;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		z-index: 10;
		justify-content: space-between;
		align-items: center;

		.logo {
			display: flex;
			align-items: center;
			max-width: 6em;
			.toggleAside {
				display: inline-block;
				width: 24px;
				height: 24px;
				background: red;
			}
		}

		.menu {
			display: flex;
			white-space: nowrap;
			flex-wrap: nowrap;

			li {
				margin: 0 1em;
			}
		}

		@media (max-width: 500px) {
			.menu {
				display: none;
			}
			.logo {
				min-width: 100%;
				margin: 0 auto;
				justify-content: space-between;
			}
		}
	}
</style>