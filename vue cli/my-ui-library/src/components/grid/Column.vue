<template>
	<div :class="colClass">
		<slot>{{ cols }}</slot>
	</div>
</template>

<script lang="ts">
	import Vue from 'vue';

	export default Vue.extend({
		props: {
			cols: String,
		},
		data(){
			return{
				colClass: null,
			}
		},
		created(){
			this.colClass = `col-${this.cols}`;
		},
	});
</script>

<style scoped lang="less">
	@cols_count: 12;
	@margin_left-right: 10px;
	@margin_top-bottom: 10px;
	@col_margin: @margin_left-right * 2; // 10 * 2

	.cols(@i) when (@i > 0) {
		.col-@{i} {
			display: flex;
			@width: calc(100% / @cols_count * @i - @col_margin);
			width: @width;
			background: hsl(@i * 10, 50%, 50%);
			line-height: 1.5;
	        margin: @margin_top-bottom @margin_left-right; /* Тут я добавил марджины (10px 10px) */
	        padding: 0 10px;
	        align-items: center;
		}
		.cols(@i - 1);
	}
	.cols(@cols_count);
</style>