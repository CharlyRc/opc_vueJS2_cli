<template>
	<div class="menu-item">
		<img class="menu-item__image" :src="item.image.source" :alt="item.image.alt" />
		<div>
			<h3>{{ item.name }}</h3>
			<p>
				Prix: {{ generatedPrice }}
				<span v-if="onSale">(10% de réduction !)</span>
			</p>
			<p v-if="item.inStock">En stock</p>
			<p v-else>En rupture de stock</p>
			<div>
				<label for="add-item-quantity">Quantité :</label>
				<input v-on:input="updateQuantity($event.target.value)" id="add-item-quantity" type="number"
					:value="item.quantity" />
				<BaseButton @click="updateShoppingCart">
					Ajouter au panier
				</BaseButton>
			</div>
		</div>
	</div>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
	name: "MenuItem",
	components: {
		BaseButton,
	},
	props: {
		item: {
			type: Object,
			required: true,
		},
	},
	data() {
		return {
			onSale: false,
		};
	},
	computed: {
		generatedPrice() {
			return this.onSale ? (this.item.price * 0.9).toFixed(2) : this.item.price;
		},
	},
	methods: {
		updateQuantity(value) {
			this.$emit('update:quantity', { item: this.item, quantity: value });
		},
		updateShoppingCart() {
			this.$emit("add-items-to-cart", this.item.quantity);
		},
		beforeMount() {
			const today = new Date().getDate();
			if (today % 2 === 0) {
				this.onSale = true;
			}
		},
	},
};
</script>

<style lang="scss">
.menu-item {
	display: flex;
	width: 500px;
	justify-content: space-between;
	margin-bottom: 30px;

	&__image {
		max-width: 300px;
	}
}
</style>