<script>

	import CcForm from './expenses/form.vue'
	import CcList from './expenses/list.vue'
	
	export default{
		components: {
			CcForm,
			CcList
		}

	}
</script>

<template>
	<q-layout>
		<div slot="header" class="toolbar">
			<q-toolbar-title :padding="0">
				Despesas em dinheiro vivo
			</q-toolbar-title>
		</div>
		<div class="container">
			<cc-form></cc-form>
			<cc-list></cc-list>
		</div>
	</q-layout>
</template>

<style scoped>
	.container{
		padding: 20px;
	}
</style>

