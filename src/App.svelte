<script>
  import Product from "./lib/Product.svelte";

  let products = [
    {
      imageUrl:
        "https://www.static-src.com/wcsstore/Indraprastha/images/catalog/full//96/MTA-8820482/khan_boyfriend_jeans_tebal_celana_wanita_hitam_navy_blue_full04_g8ftpyo0.jpg",
      name: "Celana",
      price: 20000,
      discount: 10000,
    },
    {
      imageUrl: "https://cf.shopee.co.id/file/a90a3b529518f33f4695ff695ddf49a4",
      name: "iPhone",
      price: 40000,
    },
    {
      imageUrl: "https://cf.shopee.co.id/file/a90a3b529518f33f4695ff695ddf49a4",
      name: "iPhone",
      price: 40000,
    },
    {
      imageUrl: "https://cf.shopee.co.id/file/a90a3b529518f33f4695ff695ddf49a4",
      name: "iPhone",
      price: 40000,
    },
    {
      imageUrl: "https://cf.shopee.co.id/file/a90a3b529518f33f4695ff695ddf49a4",
      name: "iPhone",
      price: 40000,
    },
  ];

  let cartItems = [];

  function addToCart(e) {
    // console.log("add to cart", e.detail);
    cartItems = [...cartItems, e.detail];
  }
</script>

<h1>TokoKeren</h1>
<h2>Cart Items</h2>
{#each cartItems as cartItem}
  <div>
    <span>
      <img alt="image" height="20px" src={cartItem.product.imageUrl} />
      {cartItem.product.name}
      {cartItem.quantity}
    </span>
  </div>
{/each}

<h2>Products</h2>
{#each products as product}
  <Product
    imageUrl={product.imageUrl}
    name={product.name}
    price={product.price}
    discount={product.discount}
    on:addToCart={addToCart}
  />
{/each}
