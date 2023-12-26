<template>
	<div>
		<all-products-manager :products-list="raspberryList" />
	</div>
</template>

<script>
import AllProductsManager from "./components/AllProductsManager.vue"
import { raspberryList } from "./constants/dataAboutRaspberries"
export default {
	name: "App",
	components: { AllProductsManager },
	data() {
		return {
			raspberryList,
		}
	},
}
</script>
<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
