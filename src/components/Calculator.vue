<template>
	<div id="appCalc">
		<div class="base">
			<section class="inputs">
				<input class="input" type="text" v-model.number="valor1">
				<input class="input" type="text" v-model.number="valor2">
				<h1 class="input resultado">={{ resultado }}</h1>
			</section>
			<section class="buttons">
				<button class="button1" @click="calc('soma')">+</button>
				<button class="button1" @click="calc('subtracao')">-</button>
				<button class="button1" @click="calc('multiplicacao')">x</button>
				<button class="button1" @click="calc('divisao')">÷</button>
			</section>	
		</div>		
	</div>
</template>
<script>
	export default{
		name: 'Calculator',
		data () {
			return {
				valor1:0,
				valor2:0,
				resultado:''
			}
		},
		methods:{
			calc(value){
				if(value === 'soma'){
					this.resultado = this.valor1 + this.valor2
				}else if(value === 'subtracao'){
					this.resultado = this.valor1 - this.valor2
				}else if(value === 'multiplicacao'){
					this.resultado = this.valor1 * this.valor2
				}else {
					this.resultado = this.valor1 / this.valor2
				}
			}
		}
	}
</script>
<style>
	#appCalc{
		display: flex;
		flex-flow: row nowrap;
		justify-content: center;
		align-items: center;
		background-color: #1E90FF;
		height: 100vh;

	}
	.base{
		display: flex;
		flex-flow: column nowrap;
		justify-content: center;
		align-items: center;
		border: 1px solid #000;
		width: 260px;
		margin-top: -120px;
		background-color: #5F9EA0;
	}
	.inputs{
		display: flex;
		flex-flow: row wrap;
		justify-content: center;
		align-items: center;
		width: 250px;
	}
	.input{
		border: 1px solid #999;
		background-color: #CD853F;
		height: 35px;
		width: 230px;
		margin-top: 10px;
	}
	.resultado{
		background-color: #DEB887;
		height: 42px;
		margin-bottom: 30px;
		margin-top: 18px;
	}
	.buttons{
		width: 200px;
		display: flex;
		flex-flow: row wrap;
		justify-content: center;
	}
	.button1{
		width: 80px;
		height: 50px;
		font-size: 22px;
		margin: 4px;
		margin-bottom: 20px;
		border: 1px solid #777;
		color: #333;
		background-color: #87CEFA; 
	}
</style>