<template>
	<div class="products-container">
		<product-item v-for="product in productsList" :product-data="product" :key="product.id" />
	</div>
</template>

<script>
import ProductItem from "./ProductItem.vue"

export default {
	name: "AllProductsManager",
	components: { ProductItem },
	props: {
		productsList: {
			type: Array,
			default: () => [],
		},
	},
}
</script>

<style lang="css" scoped>
.products-container {
	display: flex;
	gap: 30px;
}
</style>
