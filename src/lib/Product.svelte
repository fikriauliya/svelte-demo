<script>
  import Price from "./Price.svelte";
  import { createEventDispatcher } from "svelte";

  export let imageUrl = "";
  export let name = "";
  export let price;
  export let discount = 0;

  const dispatch = createEventDispatcher();
  function addToCart() {
    dispatch("addToCart", {
      product: {
        imageUrl,
        name,
        price,
        discount,
      },
      quantity: 1,
    });
  }
</script>

<div style="border:1px;border-style:dotted">
  <div>
    <img src={imageUrl} height="100px" alt="Gambar produk" />
  </div>
  <div>
    <b>{name}</b>
    <Price {price} {discount} />
  </div>
  <button on:click={addToCart}>Add to Cart</button>
</div>
