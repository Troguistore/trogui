<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>TROGUI - Tienda Online</title>
<style>
  * {
    box-sizing: border-box;
  }
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #fff;
    color: #000;
  }
  header {
    background-color: #ff6000; /* naranja más vivo */
    color: #000;
    padding: 1rem;
    text-align: center;
    position: sticky;
    top: 0;
    z-index: 100;
    user-select: none;
  }
  header h1 {
    margin: 0;
    font-size: 2rem;
    font-weight: 900;
    letter-spacing: 2px;
  }
  .header-info {
    margin-top: 0.3rem;
    color: #fff;
    font-weight: 600;
    font-size: 1rem;
  }
  .cart-info {
    margin-top: 0.5rem;
    color: #fff;
    font-weight: 700;
    font-size: 1.1rem;
    user-select: text;
  }
  main {
    padding: 1rem;
    max-width: 1100px;
    margin: auto;
  }
  #productsGrid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1rem;
  }
  .product-card {
    border: 1px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    background: #fff;
    box-shadow: 0 2px 6px rgb(0 0 0 / 0.1);
    transition: box-shadow 0.3s ease;
  }
  .product-card:hover {
    box-shadow: 0 6px 12px rgb(0 0 0 / 0.15);
  }
  .product-img {
    width: 100%;
    height: 180px;
    object-fit: contain; /* para que se vea toda la imagen completa */
    background: #eee;
  }
  .product-content {
    padding: 1rem;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .product-title {
    font-size: 1.1rem;
    font-weight: 700;
    margin: 0 0 0.5rem 0;
    color: #333;
    text-align: center;
  }
  .product-price {
    font-weight: 700;
    color: #ff6000;
    font-size: 1.2rem;
    margin-bottom: 0.5rem;
    text-align: center;
  }
  .product-desc {
    font-size: 0.9rem;
    color: #555;
    margin-bottom: 1rem;
    text-align: center;
    min-height: 44px;
  }
  .buttons {
    display: flex;
    gap: 0.7rem;
    justify-content: center;
  }
  .btn-add {
    flex: 1;
    background-color: #000;
    color: #fff;
    border: none;
    padding: 0.6rem;
    font-weight: 700;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .btn-add:hover,
  .btn-add:focus {
    background-color: #333;
    outline: none;
  }
  .btn-buy {
    flex: 1;
    background-color: #25d366;
    color: #fff;
    border: none;
    padding: 0.6rem;
    font-weight: 700;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .btn-buy:hover,
  .btn-buy:focus {
    background-color: #1ebe56;
    outline: none;
  }
  #sendCartBtn {
    margin-top: 1rem;
    background-color: #25d366;
    color: #fff;
    font-weight: 700;
    border: none;
    padding: 0.8rem 1.5rem;
    border-radius: 8px;
    cursor: pointer;
    font-size: 1rem;
    display: block;
    margin-left: auto;
    margin-right: auto;
    transition: background-color 0.3s ease;
  }
  #sendCartBtn:disabled {
    background-color: #a5d6a7;
    cursor: not-allowed;
  }
  footer {
    text-align: center;
    padding: 1rem;
    font-size: 0.85rem;
    color: #666;
    margin-top: 2rem;
    user-select: none;
  }
</style>
</head>
<body>

<header role="banner" aria-label="Encabezado principal">
  <h1>TROGUI</h1>
  <div class="header-info" aria-live="polite">Envío gratis, pago contra entrega toda Colombia</div>
  <div class="cart-info" id="cartTotal" aria-live="polite" aria-atomic="true">Carrito: vacío</div>
</header>

<main>
  <section id="productsGrid" aria-live="polite" aria-label="Listado de productos">
    <!-- Productos generados aquí -->
  </section>

  <button id="sendCartBtn" disabled aria-disabled="true" aria-label="Enviar pedido completo por WhatsApp">
    Comprar todo por WhatsApp
  </button>
</main>

<footer>
  &copy; 2025 TROGUI - Tienda Online. Todos los derechos reservados.
</footer>

<script>
  const products = [
    {
      id: 1,
      name: "Estante Giratorio para Cocina",
      price: 239000,
      shortDesc: "Organiza tus alimentos con estante giratorio, resistente y sin óxido.",
      img: "https://cdn.pixabay.com/photo/2017/08/10/07/50/shelf-2614026_1280.jpg"
    },
    {
      id: 2,
      name: "Organizador de Baño Esquinero",
      price: 59000,
      shortDesc: "Organiza tu baño con este estante resistente y sin necesidad de tornillos.",
      img: "https://d39ru7awumhhs2.cloudfront.net/colombia/products/270260/1724105603four_trays_towel_bar.jpg"
    },
    {
      id: 3,
      name: "Lámpara Esfera 3D Diseño Luna",
      price: 99000,
      shortDesc: "Lámpara decorativa esfera 3D con diseño de luna, perfecta para regalar.",
      img: "https://cdn.pixabay.com/photo/2017/09/25/13/12/lamp-2785857_1280.jpg"
    },
    {
      id: 4,
      name: "Mopa Giratoria 360° con Doble Cabezal",
      price: 59000,
      shortDesc: "Mopa de microfibra con cabezal turbo doble para limpieza rápida y eficiente.",
      img: "https://cdn.pixabay.com/photo/2016/11/29/05/08/mop-1869206_1280.jpg"
    }
  ];

  const waNumber = "573206572598";
  const productsGrid = document.getElementById("productsGrid");
  const cartTotalDiv = document.getElementById("cartTotal");
  const sendCartBtn = document.getElementById("sendCartBtn");

  let cart = [];

  function formatPrice(num) {
    return num.toLocaleString('es-CO', { style: 'currency', currency: 'COP' });
  }

  function updateCartInfo() {
    if(cart.length === 0) {
      cartTotalDiv.textContent = "Carrito: vacío";
      sendCartBtn.disabled = true;
      sendCartBtn.setAttribute("aria-disabled", "true");
    } else {
      const total = cart.reduce((acc, item) => acc + item.price * item.qty, 0);
      cartTotalDiv.textContent = `Carrito: ${cart.length} producto(s) - Total: ${formatPrice(total)}`;
      sendCartBtn.disabled = false;
      sendCartBtn.setAttribute("aria-disabled", "false");
    }
  }

  function addToCart(product) {
    const existing = cart.find(item => item.id === product.id);
    if(existing) {
      existing.qty++;
    } else {
      cart.push({...product, qty: 1});
    }
    updateCartInfo();
  }

  function createProductCard(product) {
    const article = document.createElement("article");
    article.className = "product-card";
    article.tabIndex = 0;
    article.setAttribute("aria-label", `${product.name}, precio ${formatPrice(product.price)}`);

    article.innerHTML = `
      <img src="${product.img}" alt="${product.name}" class="product-img" loading="lazy" />
      <div class="product-content">
        <h3 class="product-title">${product.name}</h3>
        <p class="product-price">${formatPrice(product.price)}</p>
        <p class="product-desc">${product.shortDesc}</p>
        <div class="buttons">
          <button class="btn-add" aria-label="Añadir ${product.name} al carrito">Añadir al carrito</button>
          <button class="btn-buy" aria-label="Comprar ${product.name} por WhatsApp">Comprar por WhatsApp</button>
        </div>
      </div>
    `;

    const addBtn = article.querySelector(".btn-add");
    const buyBtn = article.querySelector(".btn-buy");

    addBtn.addEventListener("click", () => {
      addToCart(product);
      addBtn.textContent = "Añadido ✓";
      setTimeout(() => addBtn.textContent = "Añadir al carrito", 1500);
    });

    buyBtn.addEventListener("click", () => {
      const message = encodeURIComponent(`¡Hola! Quisiera realizar la compra del producto: "${product.name}" por ${formatPrice(product.price)}. ¿Me ayudas con los detalles?`);
      window.open(`https://wa.me/${waNumber}?text=${message}`, "_blank");
    });

    return article;
  }

  function sendCartWhatsApp() {
    if(cart.length === 0) return;

    let message = "¡Hola! Quisiera realizar la compra de estos productos:\n\n";
    cart.forEach(item => {
      message += `- ${item.name} x${item.qty} = ${formatPrice(item.price * item.qty)}\n`;
    });
    const total = cart.reduce((acc, item) => acc + item.price * item.qty, 0);
    message += `\nTotal: ${formatPrice(total)}\n\n¿Me ayudas con los detalles?`;

    const encodedMessage = encodeURIComponent(message);
    window.open(`https://wa.me/${waNumber}?text=${encodedMessage}`, "_blank");
  }

  products.forEach(prod => {
    productsGrid.appendChild(createProductCard(prod));
  });

  sendCartBtn.addEventListener("click", sendCartWhatsApp);

  updateCartInfo();
</script>

</body>
</html>
