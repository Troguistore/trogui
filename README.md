<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>TROGUI - Tienda Online</title>
  <style>
    /* Reset básico */
    * {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #fff;
      color: #222;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }
    header {
      background-color: #FFA500; /* naranja */
      color: #000; /* negro */
      padding: 1rem 1.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    header h1 {
      margin: 0;
      font-weight: 900;
      font-size: 1.8rem;
      letter-spacing: 2px;
    }
    .header-info {
      color: #fff;
      font-weight: 600;
      background-color: #FFA500;
      padding: 0.5rem 1rem;
      border-radius: 4px;
      font-size: 0.9rem;
      margin-top: 0.5rem;
      flex-basis: 100%;
      text-align: center;
    }
    .search-bar {
      display: flex;
      margin-top: 0.5rem;
      flex-basis: 100%;
      justify-content: center;
    }
    .search-bar input {
      width: 100%;
      max-width: 400px;
      padding: 0.5rem 1rem;
      font-size: 1rem;
      border: 2px solid #FFA500;
      border-radius: 4px 0 0 4px;
      outline: none;
    }
    .search-bar button {
      background-color: #FFA500;
      border: none;
      color: #000;
      font-weight: 700;
      padding: 0 1.5rem;
      cursor: pointer;
      border-radius: 0 4px 4px 0;
      font-size: 1rem;
      transition: background-color 0.3s ease;
    }
    .search-bar button:hover,
    .search-bar button:focus {
      background-color: #cc8400;
    }

    main {
      flex-grow: 1;
      padding: 1.5rem 1rem 4rem;
      max-width: 1200px;
      margin: 0 auto;
      width: 100%;
    }
    #productsGrid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }
    article.product-card {
      border: 1px solid #ddd;
      border-radius: 8px;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      background: #fff;
      box-shadow: 0 2px 8px rgb(0 0 0 / 0.05);
      transition: box-shadow 0.3s ease;
      cursor: pointer;
    }
    article.product-card:hover,
    article.product-card:focus-within {
      box-shadow: 0 4px 12px rgb(0 0 0 / 0.15);
    }
    .product-img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      background: #f8f8f8;
      flex-shrink: 0;
    }
    .product-content {
      padding: 1rem;
      display: flex;
      flex-direction: column;
      flex-grow: 1;
    }
    .product-title {
      margin: 0 0 0.5rem;
      font-size: 1.15rem;
      font-weight: 700;
      color: #000;
      flex-shrink: 0;
    }
    .product-price {
      font-weight: 700;
      color: #000;
      margin-bottom: 0.75rem;
      font-size: 1.1rem;
      flex-shrink: 0;
    }
    .product-desc {
      flex-grow: 1;
      font-size: 0.9rem;
      color: #444;
      margin-bottom: 1rem;
      line-height: 1.3;
    }
    .read-more {
      color: #FFA500;
      cursor: pointer;
      font-weight: 600;
      user-select: none;
      text-decoration: underline;
    }
    .buttons {
      display: flex;
      gap: 1rem;
      justify-content: flex-end;
    }
    button.btn-add {
      background-color: #000; /* negro */
      color: #fff;
      border: none;
      padding: 0.5rem 1rem;
      font-weight: 700;
      cursor: pointer;
      border-radius: 4px;
      transition: background-color 0.3s ease;
      flex-grow: 1;
    }
    button.btn-add:hover,
    button.btn-add:focus {
      background-color: #333;
    }
    button.btn-buy {
      background-color: #25D366; /* verde WhatsApp */
      color: #fff;
      border: none;
      padding: 0.5rem 1rem;
      font-weight: 700;
      cursor: pointer;
      border-radius: 4px;
      flex-grow: 1;
      transition: background-color 0.3s ease;
    }
    button.btn-buy:hover,
    button.btn-buy:focus {
      background-color: #1ebe56;
    }

    /* Carrito info */
    #cart-info {
      position: fixed;
      top: 1rem;
      right: 1rem;
      background-color: #fff;
      border: 2px solid #000; /* negro */
      padding: 0.5rem 1rem;
      font-weight: 700;
      color: #000;
      border-radius: 4px;
      z-index: 1100;
      box-shadow: 0 2px 6px rgb(0 0 0 / 0.15);
      user-select: none;
      min-width: 180px;
      text-align: center;
      font-size: 1rem;
    }
    #cart-finalize {
      position: fixed;
      bottom: 1rem;
      right: 1rem;
      background-color: #25D366; /* verde WhatsApp */
      color: #fff;
      font-weight: 700;
      padding: 0.75rem 1.5rem;
      border-radius: 40px;
      text-decoration: none;
      box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
      z-index: 1100;
      font-size: 1.1rem;
      transition: background-color 0.3s ease;
    }
    #cart-finalize:hover,
    #cart-finalize:focus {
      background-color: #1ebe56;
    }

    /* Footer */
    footer {
      background-color: #FFA500; /* naranja */
      color: #000;
      padding: 1rem;
      text-align: center;
      font-weight: 700;
      font-size: 1rem;
      margin-top: auto;
    }

    /* Modal producto */
    .modal {
      display: none;
      position: fixed;
      z-index: 1200;
      left: 0; top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgb(0 0 0 / 0.6);
      backdrop-filter: blur(3px);
      justify-content: center;
      align-items: center;
      padding: 1rem;
    }
    .modal-content {
      background: #fff;
      border-radius: 8px;
      max-width: 500px;
      width: 100%;
      padding: 1rem 1.5rem 2rem;
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      outline: none;
    }
    .modal-close {
      position: absolute;
      top: 0.5rem;
      right: 1rem;
      font-size: 2rem;
      font-weight: 700;
      color: #333;
      cursor: pointer;
      user-select: none;
      background: none;
      border: none;
    }
    .modal-img {
      width: 100%;
      max-height: 300px;
      object-fit: contain;
      border-radius: 6px;
      margin-bottom: 1rem;
    }
    .modal-title {
      font-weight: 800;
      font-size: 1.5rem;
      margin-bottom: 0.5rem;
      color: #000;
      text-align: center;
    }
    .modal-price {
      font-weight: 700;
      font-size: 1.25rem;
      color: #000;
      margin-bottom: 1rem;
    }
    .modal-desc {
      font-size: 1rem;
      color: #444;
      line-height: 1.3;
      margin-bottom: 1.5rem;
      white-space: pre-wrap;
    }
    .modal-buttons {
      display: flex;
      gap: 1rem;
      width: 100%;
    }
    .modal-buttons button {
      flex-grow: 1;
      font-weight: 700;
      padding: 0.75rem 0;
      border-radius: 6px;
      cursor: pointer;
      border: none;
      transition: background-color 0.3s ease;
    }
    .modal-btn-add {
      background-color: #000;
      color: #fff;
    }
    .modal-btn-add:hover {
      background-color: #333;
    }
    .modal-btn-buy {
      background-color: #25D366;
      color: #fff;
    }
    .modal-btn-buy:hover {
      background-color: #1ebe56;
    }

    @media (max-width: 600px) {
      header {
        flex-direction: column;
        align-items: flex-start;
      }
      .header-info {
        flex-basis: auto;
        margin-top: 0.5rem;
        padding: 0.3rem 0.6rem;
        font-size: 0.85rem;
      }
      .search-bar {
        justify-content: flex-start;
      }
      .search-bar input {
        max-width: 100%;
      }
    }
  </style>
</head>
<body>

<header role="banner" aria-label="Encabezado principal">
  <h1>TROGUI</h1>
  <div class="header-info" aria-live="polite">Envío gratis, pago contra entrega toda Colombia</div>

  <form class="search-bar" role="search" aria-label="Buscar productos">
    <input type="search" id="searchInput" placeholder="Buscar producto..." aria-label="Buscar producto" />
    <button type="submit" aria-label="Buscar">Buscar</button>
  </form>
</header>

<main>
  <section id="productsGrid" aria-live="polite" aria-label="Listado de productos">
    <!-- Los productos se generarán aquí dinámicamente -->
  </section>
</main>

<!-- Info carrito -->
<div id="cart-info" aria-live="polite" aria-atomic="true">Carrito: $0 COP</div>
<a href="#" id="cart-finalize" aria-label="Comprar productos por WhatsApp" target="_blank" rel="noopener noreferrer">Comprar por WhatsApp</a>

<!-- Modal producto -->
<div id="productModal" class="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" aria-describedby="modalDesc">
  <div class="modal-content">
    <button class="modal-close" aria-label="Cerrar ventana modal">&times;</button>
    <img src="" alt="" class="modal-img" />
    <h2 class="modal-title" id="modalTitle"></h2>
    <p class="modal-price"></p>
    <p class="modal-desc" id="modalDesc"></p>
    <div class="modal-buttons">
      <button class="modal-btn-add">Añadir al carrito</button>
      <button class="modal-btn-buy">Comprar por WhatsApp</button>
    </div>
  </div>
</div>

<footer>
  &copy; 2025 TROGUI - Tienda Online. Todos los derechos reservados.
</footer>

<script>
  // Lista de productos con imágenes válidas
  const products = [
    {
      id: 1,
      name: "Estante Giratorio para Cocina",
      price: 239000,
      shortDesc: "Organiza tus alimentos con estante giratorio, resistente y sin óxido.",
      longDesc: "Estante giratorio 360° hecho de acero de alta calidad con acabado anti-óxido. Capacidad hasta 200 libras. Diseño ventilado para mantener frutas y verduras frescas. Ideal para cocina, baño, oficina o sala.",
      img: "https://cdn.pixabay.com/photo/2017/08/10/07/50/shelf-2614026_1280.jpg"
    },
    {
      id: 2,
      name: "Organizador de Baño Esquinero",
      price: 59000,
      shortDesc: "Organiza tu baño con este estante resistente y sin necesidad de tornillos.",
      longDesc: "Organizador para baño con 4 estantes ajustables, base antideslizante y sistema de drenaje. Fabricado en acero inoxidable y plástico ABS. Instalación sin tornillos, envío gratis y pago contra entrega en Colombia.",
      img: "https://cdn.pixabay.com/photo/2016/03/27/21/56/shelf-1283913_1280.jpg"
    },
    {
      id: 3,
      name: "Lampara Esfera 3D Diseño Luna",
      price: 99000,
      shortDesc: "Lámpara decorativa esfera 3D con diseño de luna, perfecta para regalar.",
      longDesc: "Lámpara decorativa 3D con tecnología LED, imita la superficie lunar con detalles realistas. Ideal para decorar cualquier ambiente o regalar en Día de Amor y Amistad. Incluye cargador USB y control remoto.",
      img: "https://cdn.pixabay.com/photo/2017/09/25/13/12/lamp-2785857_1280.jpg"
    },
    {
      id: 4,
      name: "Mopa Giratoria 360° con Doble Cabezal",
      price: 59000,
      shortDesc: "Mopa de microfibra con cabezal turbo doble para limpieza rápida y eficiente.",
      longDesc: "Mopa giratoria 360° con cubeta profunda y sistema spin mop para mantener el agua limpia. Limpieza 6 veces más rápida que trapeadores tradicionales. Ideal para hogares y oficinas. Precio especial con envío gratis.",
      img: "https://cdn.pixabay.com/photo/2016/11/29/05/08/mop-1869206_1280.jpg"
    }
  ];

  // Estado carrito
  let cart = [];

  // Referencias DOM
  const productsGrid = document.getElementById("productsGrid");
  const cartInfo = document.getElementById("cart-info");
  const cartFinalize = document.getElementById("cart-finalize");
  const searchForm = document.querySelector(".search-bar");
  const searchInput = document.getElementById("searchInput");
  const productModal = document.getElementById("productModal");
  const modalCloseBtn = productModal.querySelector(".modal-close");
  const modalImg = productModal.querySelector(".modal-img");
  const modalTitle = productModal.querySelector(".modal-title");
  const modalPrice = productModal.querySelector(".modal-price");
  const modalDesc = productModal.querySelector(".modal-desc");
  const modalBtnAdd = productModal.querySelector(".modal-btn-add");
  const modalBtnBuy = productModal.querySelector(".modal-btn-buy");

  // Función para formatear precio
  function formatPrice(num) {
    return num.toLocaleString('es-CO', { style: 'currency', currency: 'COP' });
  }

  // Función para mostrar productos
  function renderProducts(productsList) {
    productsGrid.innerHTML = "";
    productsList.forEach(p => {
      const article = document.createElement("article");
      article.className = "product-card";
      article.tabIndex = 0;
      article.setAttribute("aria-label", `${p.name}, precio ${formatPrice(p.price)}`);

      article.innerHTML = `
        <img src="${p.img}" alt="${p.name}" class="product-img" loading="lazy" />
        <div class="product-content">
          <h3 class="product-title">${p.name}</h3>
          <p class="product-price">${formatPrice(p.price)}</p>
          <p class="product-desc">${p.shortDesc.length > 50 ? p.shortDesc.slice(0, 50) + '...' : p.shortDesc} <span class="read-more" tabindex="0" role="button" aria-pressed="false">Leer más</span></p>
          <div class="buttons">
            <button class="btn-add" aria-label="Añadir ${p.name} al carrito">Añadir al carrito</button>
            <button class="btn-buy" aria-label="Comprar ${p.name} por WhatsApp">Comprar por WhatsApp</button>
          </div>
        </div>
      `;

      // Abrir modal con info extendida al dar click en "Leer más"
      const readMoreBtn = article.querySelector(".read-more");
      readMoreBtn.addEventListener("click", () => openModal(p));
      readMoreBtn.addEventListener("keydown", e => {
        if(e.key === "Enter" || e.key === " ") openModal(p);
      });

      // Añadir al carrito
      const addBtn = article.querySelector(".btn-add");
      addBtn.addEventListener("click", e => {
        e.stopPropagation();
        addToCart(p);
      });

      // Comprar por WhatsApp directo producto único
      const buyBtn = article.querySelector(".btn-buy");
      buyBtn.addEventListener("click", e => {
        e.stopPropagation();
        buySingleProduct(p);
      });

      productsGrid.appendChild(article);
    });
  }

  // Función abrir modal con info extendida
  function openModal(product) {
    modalImg.src = product.img;
    modalImg.alt = product.name;
    modalTitle.textContent = product.name;
    modalPrice.textContent = formatPrice(product.price);
    modalDesc.textContent = product.longDesc;
    modalBtnAdd.onclick = () => {
      addToCart(product);
      closeModal();
    };
    modalBtnBuy.onclick = () => {
      buySingleProduct(product);
      closeModal();
    };
    productModal.style.display = "flex";
    modalCloseBtn.focus();
  }

  // Cerrar modal
  function closeModal() {
    productModal.style.display = "none";
  }
  modalCloseBtn.addEventListener("click", closeModal);
  productModal.addEventListener("click", e => {
    if (e.target === productModal) closeModal();
  });
  document.addEventListener("keydown", e => {
    if(e.key === "Escape" && productModal.style.display === "flex") closeModal();
  });

  // Añadir producto al carrito
  function addToCart(product) {
    const itemIndex = cart.findIndex(item => item.id === product.id);
    if(itemIndex > -1) {
      cart[itemIndex].quantity++;
    } else {
      cart.push({ ...product, quantity: 1 });
    }
    updateCartInfo();
  }

  // Actualizar info del carrito arriba
  function updateCartInfo() {
    let total = 0;
    cart.forEach(item => {
      total += item.price * item.quantity;
    });
    cartInfo.textContent = `Carrito: ${formatPrice(total)}`;
    updateCartWhatsAppLink();
  }

  // Generar texto para WhatsApp con lista de productos en carrito
  function generateWhatsAppMessage() {
    if(cart.length === 0) return encodeURIComponent("¡Hola! Quisiera realizar una compra en tu tienda TROGUI.");
    let message = "¡Hola! Quisiera realizar una compra en TROGUI. Aquí está mi pedido:\n\n";
    cart.forEach(item => {
      message += `- ${item.name} x${item.quantity} - ${formatPrice(item.price * item.quantity)}\n`;
    });
    message += `\nTotal: ${formatPrice(cart.reduce((sum, item) => sum + item.price * item.quantity, 0))}\n\nPor favor, contáctame para coordinar el envío. Gracias.`;
    return encodeURIComponent(message);
  }

  // Actualizar enlace WhatsApp del carrito
  function updateCartWhatsAppLink() {
    const waBaseUrl = "https://wa.me/573001234567"; // Cambia este número por el de WhatsApp de TROGUI
    cartFinalize.href = waBaseUrl + "?text=" + generateWhatsAppMessage();
  }

  // Comprar producto único por WhatsApp
  function buySingleProduct(product) {
    const waBaseUrl = "https://wa.me/573001234567"; // Cambia este número por el de WhatsApp de TROGUI
    const message = `¡Hola! Quisiera comprar el producto: ${product.name} por favor.`;
    const encodedMsg = encodeURIComponent(message);
    window.open(waBaseUrl + "?text=" + encodedMsg, "_blank", "noopener");
  }

  // Buscar productos
  searchForm.addEventListener("submit", e => {
    e.preventDefault();
    const query = searchInput.value.trim().toLowerCase();
    if(!query) {
      renderProducts(products);
      return;
    }
    const filtered = products.filter(p => p.name.toLowerCase().includes(query) || p.shortDesc.toLowerCase().includes(query));
    renderProducts(filtered);
  });

  // Inicializar
  renderProducts(products);
  updateCartInfo();

</script>

</body>
</html>
