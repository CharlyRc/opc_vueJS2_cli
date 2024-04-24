<script>
export default {
	name: "MenuItem",
	props: ["addToShoppingCart", "image", "inStock", "name", "price", "quantity"]
}
</script>

<template>
	<div class="menu-item">
		<img class="menu-item__image" :src="image.source" :alt="image.alt" />
		<div>
			<h3>{{ name }}</h3>
			<p>Prix : {{ price }}</p>
			<p v-if="inStock">En stock</p>
			<p v-else>En rupture de stock</p>
			<div>
				<label for="add-item-quantity">Quantité : {{ quantity }}</label>
				<!-- eslint-disable-next-line -->
				<input v-model.number="quantity" id="add-item-quantity" type="number" />
				<button @click="addToShoppingCart(quantity)">
					Ajouter au panier
				</button>
			</div>
		</div>
	</div>
</template>

<style></style>