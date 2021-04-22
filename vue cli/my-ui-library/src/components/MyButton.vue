<template>
	<button class="button" :class="stylesArray" @click="$emit('btn-click')">
		<slot>Person</slot>
	</button>
</template>

<script lang="ts">
	import Vue from 'vue';

	export default Vue.extend({
		name: 'MyButton',
		props: {
		    size: {
				type: String,
				default: 'medium',
			},
			color: {
				type: String,
				required: true,
			},
			textColor: {
				type: String,
				default: 'white',
			},
		},
		data() {
			return{
				stylesArray: [this.size, this.color, this.textColor],
			}
		},
	});
</script>

<style scoped lang="less">
	.button{
		display: block;
	    align-items: center;
	    
	    padding: 15px 30px;
	    margin: 10px 5px;
	    font-size: 16px;
	    font-weight: 700;

	    cursor: pointer; 
	    letter-spacing: 1px;

		text-decoration: none;
		border: none;
		background: none;
		background-color: #fff;

		transition: all .15s ease-in;
	}

	.small{
		padding: 10px 25px;
		font-size: 12px;

		transition: all .12s ease-in;
	}
	.medium{
		padding: 15px 30px;
	    font-size: 16px;

	    transition: all .12s ease-in;
	}
	.large{
		padding: 20px 35px;
	    font-size: 20px;

	    transition: all .15s ease-in;
	}

	.btnColorStyle (@color){
		outline: 2px solid lighten(@color, 20%);

		box-shadow: inset 0 0 0 50px @color, 1px 2px 10px #A3A3A3;
		&:hover{
			box-shadow: inset 0 0 0 0 @color, 1px 2px 10px #A3A3A3;
			color: @color;
		}
		&:focus{
			box-shadow: inset 0 0 0 0 @color, 1px 2px 10px #A3A3A3;	
			outline-color: darken(@color, 10%);
			color: darken(@color, 10%);
		}
	}
	.success{
		.btnColorStyle(#2FE167);
	}
	.danger{
		.btnColorStyle(#FF232E);
	}
	.warning{
		.btnColorStyle(#FCAF00);
	}
	.info{
		.btnColorStyle(#0AA7FC);
	}

	.white{
		color: #fff;
	}
	.black{
		color: #000;
	}
</style>