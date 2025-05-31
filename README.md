<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>TROGUI - Tu tienda en Colombia</title>
<style>
  :root {
    --orange: #f57c00;
    --white: #fff;
    --gray-light: #f9f9f9;
    --gray-dark: #444;
    --font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  * {
    box-sizing: border-box;
  }
  body {
    margin: 0; padding: 0;
    font-family: var(--font-family);
    background: var(--gray-light);
    color: var(--gray-dark);
  }
  header {
    background-color: var(--orange);
    color: var(--white);
    padding: 1rem 1.5rem;
    text-align: center;
    font-weight: 700;
    font-size: 1.8rem;
    letter-spacing: 1.1px;
    user-select: none;
  }
  header small {
    display: block;
    font-weight: 400;
    font-size: 1rem;
    margin-top: 0.25rem;
  }
  .info-bar {
    background: var(--orange);
    color: var(--white);
    text-align: center;
    font-weight: 600;
    padding: 0.5rem 0;
    font-size: 1rem;
    user-select: none;
  }
  main {
    max-width: 960px;
    margin: 1.5rem auto 3rem;
    padding: 0 1rem;
  }
  .search-bar {
    margin-bottom: 1rem;
    display: flex;
  }
  .search-bar input {
    flex-grow: 1;
    padding: 0.6rem 1rem;
    font-size: 1rem;
    border: 2px solid var(--orange);
    border-radius: 4px 0 0 4px;
    outline-offset: 2px;
  }
  .search-bar button {
    background: var(--orange);
    border: none;
    color: var(--white);
    padding: 0 1rem;
    font-size: 1.1rem;
    border-radius: 0 4px 4px 0;
    cursor: pointer;
    transition: background 0.3s ease;
  }
  .search-bar button:hover {
    background: #e66f00;
  }
  .products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(280px,1fr));
    gap: 1.4rem;
  }
  .product-card {
    background: var(--white);
    border-radius: 8px;
    box-shadow: 0 0 8px rgb(0 0 0 / 0.1);
    display: flex;
    flex-direction: column;
    transition: transform 0.2s ease;
  }
  .product-card:hover {
    transform: translateY(-5px);
  }
  .product-img {
    width: 100%;
    aspect-ratio: 1/1;
    object-fit: contain;
    border-radius: 8px 8px 0 0;
    background: #fafafa;
  }
  .product-content {
    flex-grow: 1;
    padding: 0.9rem 1rem 1.2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .product-title {
    font-weight: 700;
    font-size: 1.1rem;
    margin-bottom: 0.3rem;
    color: var(--orange);
    user-select: none;
  }
  .product-price {
    font-weight: 700;
    color: #333;
    margin-bottom: 0.5rem;
  }
  .product-desc {
    font-size: 0.9rem;
    color: #555;
    margin-bottom: 0.7rem;
    user-select: none;
  }
  .read-more {
    color: var(--orange);
    cursor: pointer;
    font-weight: 600;
    font-size: 0.9rem;
    user-select: none;
    margin-bottom: 0.9rem;
  }
  .buttons {
    display: flex;
    gap: 0.6rem;
  }
  button {
    cursor: pointer;
    border: none;
    border-radius: 5px;
    padding: 0.5rem;
    font-weight: 700;
    font-size: 0.9rem;
    transition: background-color 0.3s ease;
    user-select: none;
  }
  .btn-add {
    flex-grow: 1;
    background: #ffb74d;
    color: #3e2723;
  }
  .btn-add:hover {
    background: #ffa726;
  }
  .btn-buy {
    background: var(--orange);
    color: var(--white);
    min-width: 110px;
  }
  .btn-buy:hover {
    background: #e65100;
  }
  #cart-info {
    position: fixed;
    top: 0; right: 0;
    background: var(--orange);
    color: var(--white);
    font-weight: 700;
    padding: 0.7rem 1rem;
    border-bottom-left-radius: 10px;
    font-size: 1rem;
    user-select: none;
    z-index: 9999;
  }
  #cart-finalize {
    position: fixed;
    bottom: 1.2rem;
    right: 1.2rem;
    background: var(--orange);
    color: var(--white);
    border-radius: 50px;
    font-weight: 700;
    padding: 0.9rem 1.4rem;
    font-size: 1rem;
    cursor: pointer;
    user-select: none;
    box-shadow: 0 0 10px rgb(245 124 0 / 0.6);
    display: none;
    z-index: 9999;
    text-decoration: none;
  }
  #cart-finalize:hover {
    background: #e65100;
  }
  footer {
    text-align: center;
    margin: 3rem 0 1rem;
    color: #777;
    font-size: 0.9rem;
  }
  /* Modal styles */
  .modal {
    display: none;
    position: fixed;
    z-index: 10000;
    left: 0; top: 0;
    width: 100%; height: 100%;
    overflow: auto;
    background-color: rgba(0,0,0,0.6);
  }
  .modal-content {
    background-color: #fff;
    margin: 8% auto;
    padding: 1.8rem 2rem;
    border-radius: 10px;
    max-width: 480px;
    position: relative;
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
  }
  .modal-close {
    color: #aaa;
    position: absolute;
    top: 12px; right: 20px;
    font-size: 1.6rem;
    font-weight: 700;
    cursor: pointer;
    user-select: none;
  }
  .modal-close:hover {
    color: var(--orange);
  }
  .modal-img {
    width: 100%;
    object-fit: contain;
    margin-bottom: 1rem;
  }
  .modal-title {
    font-weight: 700;
    font-size: 1.4rem;
    margin-bottom: 0.7rem;
    color: var(--orange);
  }
  .modal-price {
    font-weight: 700;
    color: #333;
    font-size: 1.2rem;
    margin-bottom: 1rem;
  }
  .modal-desc {
    font-size: 1rem;
    color: #555;
    margin-bottom: 1.4rem;
    white-space: pre-wrap;
  }
  .modal-buttons {
    display: flex;
    gap: 1rem;
  }
  .btn-close {
    background: #bbb;
    color: #fff;
    flex-grow: 1;
    font-weight: 700;
    border-radius: 5px;
    padding: 0.5rem;
    cursor: pointer;
    user-select: none;
  }
  .btn-close:hover {
    background: #999;
  }
</style>
</head>
<body>

<header>
  Dropi
  <small>Envío gratis | Pago contra entrega en Colombia</small>
</header>

<div class="info-bar">Compra productos prácticos y ahorra espacio. Calidad garantizada, atención personalizada.</div>

<main>
  <div class="search-bar" role="search">
    <input id="searchInput" type="search" placeholder="Buscar productos..." aria-label="Buscar productos" />
    <button id="searchBtn" aria-label="Buscar">🔍</button>
  </div>

  <div class="products-grid" id="productsGrid">
    <!-- Productos cargados aquí -->
  </div>
</main>

<div id="cart-info" aria-live="polite" aria-atomic="true" role="status" style="display:none;">
  Total carrito: $0
</div>

<a id="cart-finalize" href="#" target="_blank" rel="noopener noreferrer" aria-label="Comprar productos por WhatsApp">Comprar por WhatsApp</a>

<footer>
  &copy; 2025 TROGUI - Tienda online en Colombia
</footer>

<!-- Modal producto -->
<div id="productModal" class="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" aria-describedby="modalDesc">
  <div class="modal-content">
    <span class="modal-close" id="modalClose" aria-label="Cerrar">&times;</span>
    <img src="" alt="" class="modal-img" id="modalImg" />
    <h2 class="modal-title" id="modalTitle"></h2>
    <div class="modal-price" id="modalPrice"></div>
    <div class="modal-desc" id="modalDesc"></div>
    <div class="modal-buttons">
      <button class="btn-add" id="modalAddBtn">Añadir al carrito</button>
      <button class="btn-buy" id="modalBuyBtn">Comprar por WhatsApp</button>
    </div>
  </div>
</div>

<script>
  const products = [
    {
      id: 1,
      title: "Estante giratorio para cocina",
      price: 239000,
      img: "https://i.imgur.com/1PA9eI6.jpg",
      description: "Resistente y duradero, acero de alta calidad, anti-óxido. Mantiene frutas frescas, gira 360°, sin instalación.",
      descriptionFull: "Resistente y duradero, acero de alta calidad con acabado negro anti-óxido. Diseño ventilado para mantener frutas y verduras frescas. Ruedas con bloqueo para fácil movimiento. Ideal para cocina, baño y oficina. Sin instalación, listo para usar.",
    },
    {
      id: 2,
      title: "Organizador de baño en esquina",
      price: 59000,
      img: "https://i.imgur.com/ZZhDcXH.jpg",
      description: "Acero inoxidable y ABS, resistente y sin óxido, con estantes reforzados y base antideslizante.",
      descriptionFull: "Organizador de baño en esquina hecho en acero inoxidable y ABS. Estantes reforzados para mayor capacidad y durabilidad. Base antideslizante que evita accidentes. No requiere tornillos, fácil de instalar. Incluye barra para colgar y 4 ganchos. Perfecto para baño y cocina.",
    },
    {
      id: 3,
      title: "Mopa 360° con doble cabezal de microfibra",
      price: 59000,
      img: "https://i.imgur.com/9rFf1Bt.jpg",
      description: "Mopa con sistema giratorio, ultra absorbente, limpia 6 veces más rápido y fácil de usar.",
      descriptionFull: "Mopa con dos cabezales turbo de microfibra que giran 360°. Cubo con sistema giratorio profundo y plástico resistente. Limpia polvo y suciedad atrapándolos efectivamente. Ideal para suelos y superficies delicadas. Rápida, eficiente y durable.",
    }
  ];

  const cart = [];

  const productsGrid = document.getElementById("productsGrid");
  const cartInfo = document.getElementById("cart-info");
  const cartFinalize = document.getElementById("cart-finalize");
  const searchInput = document.getElementById("searchInput");
  const searchBtn = document.getElementById("searchBtn");

  const productModal = document.getElementById("productModal");
  const modalClose = document.getElementById("modalClose");
  const modalImg = document.getElementById("modalImg");
  const modalTitle = document.getElementById("modalTitle");
  const modalPrice = document.getElementById("modalPrice");
  const modalDesc = document.getElementById("modalDesc");
  const modalAddBtn = document.getElementById("modalAddBtn");
  const modalBuyBtn = document.getElementById("modalBuyBtn");

  let modalCurrentProduct = null;

  // Función para mostrar productos
  function showProducts(list) {
    productsGrid.innerHTML = "";
    list.forEach(product => {
      const card = document.createElement("article");
      card.className = "product-card";
      card.tabIndex = 0;
      card.setAttribute("aria-label", product.title + " " + product.price + " pesos");

      card.innerHTML = `
        <img src="${product.img}" alt="${product.title}" class="product-img" loading="lazy" />
        <div class="product-content">
          <h3 class="product-title">${product.title}</h3>
          <div class="product-price">$${product.price.toLocaleString('es-CO')}</div>
          <p class="product-desc">${shortenText(product.description, 20)} <span class="read-more" role="button" tabindex="0" aria-label="Leer más de ${product.title}">Leer más</span></p>
          <div class="buttons">
            <button class="btn-add" data-id="${product.id}">Añadir al carrito</button>
            <button class="btn-buy" data-id="${product.id}">Comprar por WhatsApp</button>
          </div>
        </div>
      `;

      productsGrid.appendChild(card);
    });
  }

  // Recortar texto a max palabras
  function shortenText(text, maxWords) {
    const words = text.split(" ");
    if (words.length <= maxWords) return text;
    return words.slice(0, maxWords).join(" ") + "...";
  }

  // Buscar productos con tolerancia a tildes y mayúsculas
  function normalizeText(text) {
    return text.normalize("NFD").replace(/[\u0300-\u036f]/g, "").toLowerCase();
  }

  function searchProducts(query) {
    const normQuery = normalizeText(query.trim());
    if (!normQuery) return products;
    return products.filter(p => normalizeText(p.title).includes(normQuery) || normalizeText(p.description).includes(normQuery));
  }

  // Actualizar carrito y mostrar total
  function updateCartInfo() {
    if (cart.length === 0) {
      cartInfo.style.display = "none";
      cartFinalize.style.display = "none";
      return;
    }
    cartInfo.style.display = "block";
    cartFinalize.style.display = "block";

    const total = cart.reduce((acc, item) => acc + item.price * item.qty, 0);
    cartInfo.textContent = `Total carrito: $${total.toLocaleString('es-CO')}`;

    // Actualizar link de WhatsApp con mensaje
    const whatsappBase = "https://wa.me/573206572598?text=";
    let message = "¡Hola! Quisiera realizar una compra en TROGUI. Aquí están los productos:\n";

    cart.forEach(item => {
      message += `- ${item.title} x${item.qty} = $${(item.price * item.qty).toLocaleString('es-CO')}\n`;
    });

    message += `Total: $${total.toLocaleString('es-CO')}\n¿Puedes ayudarme con los detalles?`;

    const encodedMessage = encodeURIComponent(message);
    cartFinalize.href = whatsappBase + encodedMessage;
  }

  // Añadir producto al carrito
  function addToCart(id) {
    const product = products.find(p => p.id === id);
    if (!product) return;
    const index = cart.findIndex(item => item.id === id);
    if (index > -1) {
      cart[index].qty++;
    } else {
      cart.push({...product, qty: 1});
    }
    updateCartInfo();
  }

  // Comprar un producto directo por WhatsApp
  function buyNow(id) {
    const product = products.find(p => p.id === id);
    if (!product) return;
    const whatsappBase = "https://wa.me/573206572598?text=";
    let message = `¡Hola! Quisiera comprar el producto "${product.title}" en TROGUI. ¿Me puedes ayudar con los detalles?`;
    const encodedMessage = encodeURIComponent(message);
    window.open(whatsappBase + encodedMessage, "_blank", "noopener");
  }

  // Modal producto
  function openModal(product) {
    modalCurrentProduct = product;
    modalImg.src = product.img;
    modalImg.alt = product.title;
    modalTitle.textContent = product.title;
    modalPrice.textContent = `$${product.price.toLocaleString('es-CO')}`;
    modalDesc.textContent = product.descriptionFull;
    productModal.style.display = "block";
    modalAddBtn.focus();
  }
  function closeModal() {
    productModal.style.display = "none";
    modalCurrentProduct = null;
  }

  // Eventos
  document.addEventListener("click", e => {
    // Añadir al carrito botón
    if (e.target.matches(".btn-add")) {
      const id = parseInt(e.target.getAttribute("data-id"));
      addToCart(id);
    }
    // Comprar por WhatsApp botón
    if (e.target.matches(".btn-buy")) {
      const id = parseInt(e.target.getAttribute("data-id"));
      buyNow(id);
    }
    // Leer más
    if (e.target.classList.contains("read-more")) {
      const card = e.target.closest(".product-card");
      if (!card) return;
      const idAttr = card.querySelector(".btn-add").getAttribute("data-id");
      const product = products.find(p => p.id === parseInt(idAttr));
      if (product) openModal(product);
    }
    // Cerrar modal
    if (e.target === modalClose || e.target === productModal) {
      closeModal();
    }
  });

  // Accesibilidad para leer más con teclado
  document.addEventListener("keydown", e => {
    if (e.key === "Escape" && productModal.style.display === "block") {
      closeModal();
    }
    if (e.target.classList.contains("read-more") && (e.key === "Enter" || e.key === " ")) {
      e.preventDefault();
      e.target.click();
    }
  });

  // Buscar productos
  function doSearch() {
    const query = searchInput.value;
    const results = searchProducts(query);
    showProducts(results);
  }
  searchBtn.addEventListener("click", doSearch);
  searchInput.addEventListener("keyup", e => {
    if (e.key === "Enter") doSearch();
  });

  // Mostrar todos los productos inicialmente
  showProducts(products);
</script>

</body>
</html>
