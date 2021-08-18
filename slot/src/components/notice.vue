<template>
	<div>
		<button :flag = "flag" @click = "render">可自动消失</button>
		<button :remo = "flag" @click = "del">不可自动消失</button>
		<div class = "p"
		v-if = "flag == true && remo1 == false"
		>
			<p>可自动消失</p>
			<span @click = "remove1">X</span>
		</div>
		<div class = "p"
		v-if = "remo == true"
		>
			<p>不可自动消失</p>
			<span @click = "remove">X</span>
		</div>
	</div>
</template>

<script>
export default {
	data(){
		return {
			flag:false,
			remo:false,
			remo1:false,
		}
	},
	Timeout:"",
	methods:{
		render(){
			this.flag = true
			this.remo1 = false
			this.Timeout = setTimeout(()=>{
				this.flag = false
			},5000)
		},
		del(){
			this.remo = true
		},
		remove(){
			this.remo = false
		},
		remove1(){
			this.remo1 = true,
			clearTimeout(this.Timeout)
		}
	}
};
</script>

<style lang="scss" scoped>
	*{
		margin: 0;
		padding: 0;
		list-style: none;
	}
	div{
		button{
			// margin-top: 50px;
			margin-left: 10px;
		}
		span{
			cursor: pointer;
		}
		.p{
			margin-top: 10px;
			display: flex;
			align-items: center;
			span{
				margin-left: 20px;
			}
		}
	}
</style>