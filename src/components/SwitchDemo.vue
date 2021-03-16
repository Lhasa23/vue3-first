<template>
	<div>
		<Switch v-model="bool"/>
	</div>
</template>
<script lang="ts">
	import Switch from '../lib/Switch.vue'
	import { ref } from 'vue'

	export default {
	  name: 'SwitchDemo',
		components: { Switch },
		setup () {
			const bool = ref(false)
			return { bool }
		}
	}
</script>