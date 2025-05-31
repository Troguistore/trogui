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
      font-family: Arial, sans-serif;
      background: #fff;
      color: #000;
    }
    header {
      background-color: #cc6600; /* naranja más oscuro */
      color: #000;
      padding: 1rem;
      text-align: center; /* centrar TROGUI */
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
      color: #fff; /* blanco para contraste */
      font-weight: 600;
      font-size: 1rem;
    }
    main {
      padding: 1rem;
      max-width: 1100px;
      margin: auto;
    }
    #productsGrid {
      display: grid;
      grid-template-columns: repeat(auto-fill,minmax(280px,1fr));
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
      object-fit: cover;
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
      color: #cc6600;
      font-size: 1.2rem;
      margin-bottom: 0.5rem;
      text-align: center;
    }
    .product-desc {
      font-size: 0.9rem;
      color: #555;
      margin-bottom: 1rem;
      text-align: center;
      min-height: 44px; /* para evitar saltos al leer más */
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
      background-color: #25d366; /* verde WhatsApp */
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
</header>

<main>
  <section id="productsGrid" aria-live="polite" aria-label="Listado de productos">
    <!-- Productos se generan aquí -->
  </section>
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
      img: "https://cdn.pixabay.com/photo/2016/03/27/21/56/shelf-1283913_1280.jpg"
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

  const productsGrid = document.getElementById("productsGrid");
  const waNumber = "573206572598"; // Número correcto WhatsApp

  function formatPrice(num) {
    return num.toLocaleString('es-CO', { style: 'currency', currency: 'COP' });
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
      alert(`Producto "${product.name}" añadido al carrito.`);
      // Aquí puedes agregar funcionalidad para un carrito real si quieres
    });

    buyBtn.addEventListener("click", () => {
      const msg = `¡Hola! Quisiera comprar el producto: ${product.name} por favor.`;
      const url = `https://wa.me/${waNumber}?text=${encodeURIComponent(msg)}`;
      window.open(url, "_blank", "noopener");
    });

    return article;
  }

  function renderProducts() {
    productsGrid.innerHTML = "";
    products.forEach(product => {
      const card = createProductCard(product);
      productsGrid.appendChild(card);
    });
  }

  renderProducts();
</script>

</body>
</html>
