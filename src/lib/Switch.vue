<template>
	<button
		class="md-switch"
		@click="toggle"
		:class="{'md-checked':modelValue}"
	>
		<span></span>
	</button>
</template>
<script lang="ts">
	export default {
		name: 'Switch',
		props: {
			modelValue: Boolean,
		},
		setup(props: { modelValue: boolean; }, context: { emit: (arg0: string, arg1: boolean) => void; }) {
			const toggle = () => {
				context.emit("update:modelValue", !props.modelValue);
			};
			return { toggle };
		}
	}
</script>

<style lang="scss">
	$h: 24px;
	$h2: $h - 4px;
	.md-switch {
		height: $h;
		width: $h * 2;
		border: none;
		background: #bfbfbf;
		border-radius: $h/2;
		position: relative;

		span {
			position: absolute;
			top: 2px;
			left: 2px;
			height: $h2;
			width: $h2;
			background: white;
			border-radius: $h2 / 2;
			transition: all 250ms;
		}

		&.md-checked {
			background: #1890ff;

			span {
				left: calc(100% - #{$h2} - 2px);
			}
		}

		&:focus {
			outline: none;
		}

		&:active {
			span {
				width: $h2 + 4px;
			}
		}

		&.md-checked:active {
			span {
				width: $h2 + 4px;
				margin-left: -4px;
			}
		}
	}
</style>