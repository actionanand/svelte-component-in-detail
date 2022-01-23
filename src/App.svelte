<script>
  import Product from './Product.svelte';

	export let appName;

  function addToCart(event) {
    console.log(event.detail.id); // we passed the data'{id: 'p1'}'
  }

  function deleteProduct(event) {
    console.log(event.detail);  // we passed the data'p1'
  }
</script>

<style>
  .capitalize-it {
    text-transform: capitalize;
  }	
</style>

<h1 class="capitalize-it">{appName}</h1>
<Product productTitle="A book" 
  on:add-to-cart={addToCart}
  on:delete={deleteProduct}
/>
