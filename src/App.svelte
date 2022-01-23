<script>
  import Product from './Product.svelte';

	export let appName;
</script>

<style>
  .capitalize-it {
    text-transform: capitalize;
  }	
</style>

<h1 class="capitalize-it">{appName}</h1>
<Product productTitle="A book" 
  on:add-to-cart={() => alert('Add to cart')}
  on:delete={() => alert('Delete')}
/>
