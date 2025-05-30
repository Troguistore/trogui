<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TROGUI - Tienda Online</title>
<style>
  body { font-family: Arial, sans-serif; margin: 0; padding: 0; }
  header { background: orange; color: #fff; text-align: center; padding: 1rem 0; font-size: 1.8rem; font-weight: bold; }
  .container { padding: 1rem; max-width: 1200px; margin: auto; }
  .search-bar { width: 100%; padding: 0.5rem; margin-bottom: 1rem; border: 1px solid #ccc; border-radius: 5px; }
  .cart-info { display: flex; justify-content: space-between; margin-bottom: 1rem; }
  .cart-info span { font-weight: bold; }
  .products { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 1rem; }
  .product { border: 1px solid #eee; border-radius: 8px; padding: 0.5rem; text-align: center; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
  .product img { width: 100%; max-height: 150px; object-fit: contain; }
  .product-name { font-weight: bold; margin: 0.5rem 0; }
  .product-price { color: green; font-weight: bold; }
  .btn { display: block; width: 100%; margin: 0.3rem 0; padding: 0.5rem; border: none; border-radius: 5px; font-weight: bold; cursor: pointer; }
  .add-btn { background: #000; color: #fff; }
  .whatsapp-btn { background: orange; color: #fff; }
  @media (max-width: 600px) {
    .product img { max-height: 120px; }
  }
</style>
</head>
<body>

<header>TROGUI</header>

<div class="container">
  <p>Descubre nuestros productos más populares</p>
  <input type="text" id="search" class="search-bar" placeholder="Buscar productos..." oninput="searchProducts()">

  <div class="cart-info">
    <span>Productos en el carrito: <span id="cart-count">0</span></span>
    <span>Total: $<span id="cart-total">0</span></span>
  </div>

  <div class="products" id="product-list">
    <!-- Productos (ejemplo) -->
    <div class="product" data-name="Afeitadora 3 en 1" data-price="59000">
      <img src="https://via.placeholder.com/150" alt="Afeitadora">
      <div class="product-name">Afeitadora 3 en 1</div>
      <div class="product-price">$59.000</div>
      <button class="btn add-btn" onclick="addToCart('Afeitadora 3 en 1', 59000)">Añadir al carrito</button>
      <button class="btn whatsapp-btn" onclick="buyNow('Afeitadora 3 en 1', 59000)">Comprar por WhatsApp</button>
    </div>

    <div class="product" data-name="Organizador para baño" data-price="75000">
      <img src="https://via.placeholder.com/150" alt="Organizador para baño">
      <div class="product-name">Organizador para baño</div>
      <div class="product-price">$75.000</div>
      <button class="btn add-btn" onclick="addToCart('Organizador para baño', 75000)">Añadir al carrito</button>
      <button class="btn whatsapp-btn" onclick="buyNow('Organizador para baño', 75000)">Comprar por WhatsApp</button>
    </div>

    <div class="product" data-name="Mini impresora portátil" data-price="65000">
      <img src="https://via.placeholder.com/150" alt="Mini impresora">
      <div class="product-name">Mini impresora portátil</div>
      <div class="product-price">$65.000</div>
      <button class="btn add-btn" onclick="addToCart('Mini impresora portátil', 65000)">Añadir al carrito</button>
      <button class="btn whatsapp-btn" onclick="buyNow('Mini impresora portátil', 65000)">Comprar por WhatsApp</button>
    </div>

    <div class="product" data-name="Hidrolavadora inalámbrica" data-price="95000">
      <img src="https://via.placeholder.com/150" alt="Hidrolavadora">
      <div class="product-name">Hidrolavadora inalámbrica</div>
      <div class="product-price">$95.000</div>
      <button class="btn add-btn" onclick="addToCart('Hidrolavadora inalámbrica', 95000)">Añadir al carrito</button>
      <button class="btn whatsapp-btn" onclick="buyNow('Hidrolavadora inalámbrica', 95000)">Comprar por WhatsApp</button>
    </div>

    <div class="product" data-name="Escurridor de platos" data-price="135000">
      <img src="https://via.placeholder.com/150" alt="Escurridor">
      <div class="product-name">Escurridor de platos</div>
      <div class="product-price">$135.000</div>
      <button class="btn add-btn" onclick="addToCart('Escurridor de platos', 135000)">Añadir al carrito</button>
      <button class="btn whatsapp-btn" onclick="buyNow('Escurridor de platos', 135000)">Comprar por WhatsApp</button>
    </div>
  </div>
</div>

<script>
  let cart = [];

  function addToCart(name, price) {
    cart.push({ name, price });
    updateCartInfo();
  }

  function updateCartInfo() {
    document.getElementById('cart-count').innerText = cart.length;
    let total = cart.reduce((sum, item) => sum + item.price, 0);
    document.getElementById('cart-total').innerText = total.toLocaleString();
  }

  function buyNow(name, price) {
    let message = `Hola, quiero comprar este producto:\n\nProducto: ${name}\nPrecio: $${price.toLocaleString()}`;
    window.open(`https://wa.me/?text=${encodeURIComponent(message)}`, '_blank');
  }

  function searchProducts() {
    let query = document.getElementById('search').value.toLowerCase();
    let products = document.querySelectorAll('.product');
    products.forEach(p => {
      let name = p.getAttribute('data-name').toLowerCase();
      p.style.display = name.includes(query) ? 'block' : 'none';
    });
  }
</script>

</body>
</html>
