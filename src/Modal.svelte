<script>
  import { createEventDispatcher, onMount, onDestroy, beforeUpdate, afterUpdate } from 'svelte';

  const dispatch = createEventDispatcher();
  let agreed = false;
  let autoScroll = false;

  onMount(() => console.log('Mounted'));

  onDestroy(() => console.log('Destroyed'));

  beforeUpdate(() => {
    console.log('Before Update');
    autoScroll = agreed;
  });

  afterUpdate(() => {
    console.log('After update');
    if(autoScroll) {
      const modal = document.querySelector('.modal');
      modal.scrollTo(0, modal.scrollHeight);
    }
  });

  console.log('Scripts executed!');
</script>

<div class="backdrop" on:click="{() => dispatch('cancel')}"></div>
<div class="modal">
  <header>
    <slot name="header"/>
  </header>
  <div class="content">
    <slot/>
  </div>
  <div>
    <p>Before you close, you must agree to our terms and conditions!</p>
    <button on:click="{() => agreed = true}">Agree</button>
  </div>
  <footer>
    <slot name="footer" didAgree={agreed}>
      <button on:click="{() => dispatch('close')}" disabled={!agreed}>Close</button>
    </slot>
  </footer>
</div>

<style>
  .backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.75);
    z-index: 10;
  }

  .modal {
    padding: 1rem;
    position: fixed;
    top: 10vh;
    left: 10%;
    width: 80%;
    max-height: 15vh;
    background: white;
    border-radius: 5px;
    z-index: 100;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    overflow: auto;
  }

  header {
    border-bottom: 1px solid #ccc;
  }
</style>