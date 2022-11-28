<script>
  export let price;
  export let discount;
</script>

{#if discount > 0}
  <strike>{price}</strike>
  <span style="color:red">{discount}</span>
{:else}
  {price}
{/if}
