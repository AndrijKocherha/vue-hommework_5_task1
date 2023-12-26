<template>
	<a href="#" class="prod-card">
		<div class="prod-card__image"><img :src="productData.imgSrc" alt="" /></div>
		<div class="prod-card__content">
			<div class="prod-card__head">
				<div class="prod-card__shop-title">
					<div><img :src="productData.log" alt="" /></div>
					<div>{{ productData.companyTitle }}</div>
				</div>
				<div v-if="isAmount" class="prod-card__is-product">
					<span v-if="isProduct" class="is-product">В наявності</span>
					<span v-else class="no-product">не в наявномті</span>
				</div>
			</div>
			<div class="prod-card__description">{{ productData.description }}</div>
		</div>
	</a>
</template>

<script>
export default {
	name: "ProductItem",
	props: {
		productData: {
			type: Object,
			default: () => ({}),
		},
	},
	computed: {
		isProduct() {
			return this.productData.amount > 0
		},
		isAmount() {
			return "amount" in this.productData
		},
	},
}
</script>

<style lang="css" scoped>
.prod-card {
	color: #000;
	text-decoration: none;
	padding: 10px;
	background-color: #aca1a1;
	flex: 0 1 33.333%;
}
.prod-card__image {
	/*max-width: 340px;*/
	position: relative;
	width: 100%;
	padding-bottom: 66%;
	margin-bottom: 20px;
}
.prod-card__image img {
	/*max-width: 100%;*/
	position: absolute;
	width: 100%;
	height: 100%;
	top: 0;
	left: 0;
	object-fit: cover;
}
.prod-card__content {
	display: grid;
	gap: 10px;
	justify-content: start;
}
.prod-card__head {
	display: flex;
	align-items: center;
	gap: 20px;
}
.prod-card__shop-title {
	display: flex;
	align-items: center;
	gap: 10px;
}
.prod-card__is-product {
}
.prod-card__description {
}
.is-product {
	color: green;
}
.no-product {
	color: red;
}
</style>
