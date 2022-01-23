<script>
  import Product from './Product.svelte';
  import Modal from './Modal.svelte';

	export let appName;

  let showModal = false;

  let products = [
    {
      id: 'p1',
      title: 'A Book',
      price: '$ 9.8'
    }
  ];

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
{#each products as product}
  <Product
    {...product}
    on:add-to-cart={addToCart}
    on:delete={deleteProduct}
  />
{/each}

<button on:click="{() => showModal = true}">Show Modal</button>

{#if showModal}
  <Modal 
    on:cancel="{() => showModal = false}"
    on:close="{() => showModal = false}">
    <h1 slot="header">Hello Modal!</h1>
    <div>
      Modal content goes here.
    </div>
    <button slot="footer" on:click="{() => showModal = false}">
      Confirm
    </button>
  </Modal>
{/if}

