<template>
	<div class="row" ref="rowComponent">
		<slot></slot>
	</div>
</template>

<script lang="ts">
	
</script>

<style scoped lang="less">
	.row {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: flex-start;
		align-items: center;
	}
</style>