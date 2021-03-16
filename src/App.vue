<template>
	<router-view/>
</template>
<script lang="ts">
	import { defineComponent, ref, provide } from 'vue'
	import Home from './views/Home.vue'
	import router from './routers'

	export default defineComponent({
		name: 'App',
		components: { Home },
		setup () {
			const width = document.documentElement.clientWidth
			const menuVisible = ref(width <= 500 ? false : true)
			provide('menuVisible', menuVisible) // set
			router.afterEach(() => {
				if (width <= 500) {
					menuVisible.value = false
				}
			})
		}
	})
</script>

<style>
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>
