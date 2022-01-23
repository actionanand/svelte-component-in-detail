<script>
  import { tick } from 'svelte';

  import Product from './Product.svelte';
  import Modal from './Modal.svelte';

	export let appName;

  let showModal = false;
  let closable = false;
  let text = 'After selecting the text, please press "enter" to change the text to uppercase!';

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

  function transformText(event) {
    if(event.which !== 13) {
      return;
    }
    event.preventDefault();
    const selectionStart = event.target.selectionStart;
    const selectionEnd = event.target.selectionEnd;
    const value = event.target.value;
    text = value.slice(0, selectionStart) + 
            value.slice(selectionStart, selectionEnd).toUpperCase() + 
            value.slice(selectionEnd);
    
    tick().then(() => {
      event.target.selectionStart = selectionStart;
      event.target.selectionEnd = selectionEnd;
    });
    // Code won't work as it'll run before dom update
    // event.target.selectionStart = selectionStart;
    // event.target.selectionEnd = selectionEnd;
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
    on:close="{() => showModal = false}"
    let:didAgree={closable}>
    <h1 slot="header">Hello Modal!</h1>
    <div>
      Modal content goes here.
    </div>
    <button slot="footer" on:click="{() => showModal = false}" disabled={!closable}>
      Confirm
    </button>
  </Modal>
{/if}

<textarea rows="5" value={text} on:keypress="{transformText}"></textarea>

