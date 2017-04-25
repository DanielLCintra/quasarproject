<script>

	import { Dialog } from 'quasar'

	export default{

		computed:{
			list(){
				return this.$store.state.Expenses.list
			}
		},
		methods:{
			askRemove(expense){

				const VmThis = this

				Dialog.create({
				  title: 'Tem certeza?',
				  buttons: [
				    {
				      label: 'Cancelar'
				    },
				    {
				      label: 'Confirmar',
				      handler () {
				        VmThis.remove(expense)
				      }
				    }
				  ]
				})
			},
			remove(expense){
				this.$store.commit('REMOVE_EXPENSE', expense)
			}
		}
	}
</script>

<template>	
	<div>
		<div class="expense" v-for="expense in list">
			<p>{{ expense.date }} - R${{ expense.amount }}</p>
			<p>{{ expense.description }}</p>
			<a class="removeLink" href="#" @click.prevent="askRemove(expense)"> remove</a>
		</div>	
	</div>
</template>

<style>
	.expense{
		border-bottom: #999 1px solid;
		padding-top: 10px;
		position: relative;
	}
	.removeLink{
		color: #c00000;
		position: absolute;
		bottom: 10px;
		right: 0;
		font-size: 0.8em;
	}
</style>
