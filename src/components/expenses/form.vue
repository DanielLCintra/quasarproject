<script>
	export default{
		data(){
			return {
				expense:{
					amount: '',
					description: '',
					date: ''
				}
			}
		},
		methods:{
			submit () {
				this.$store.commit('ADD_EXPENSE',this.expenses)
			}
		}
	}
</script>

<template>	
	<form @submit.prevent="submit">
		<input class="my-input" type="number" v-model="expense.amount" placeholder="R$">
		<input class="my-input" type="text" v-model="expense.description" placeholder="Descrição">
		<input class="my-input" type="text" v-model="expense.date" placeholder="Data">

		<button class="primary my-button">Salvar</button>
	</form>
</template>

<style scoped>
	.my-input{
		width: 100%;
		margin-bottom: 20px; 
	}
	.my-button{
		width: 100%;
	}
</style>
