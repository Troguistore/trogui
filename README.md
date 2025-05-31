<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>TROGUI - Tienda Online</title>
<style>
  body {
    background-color: #ff6000;
    font-family: Arial, sans-serif;
    margin: 0;
    color: #000;
  }

  header {
    text-align: center;
    font-size: 2.5rem;
    font-weight: bold;
    padding: 20px 10px;
    color: #000;
  }

  .barra-carrito {
    background: #000;
    color: #fff;
    font-weight: bold;
    padding: 12px;
    font-size: 1rem;
    text-align: center;
    cursor: pointer;
  }

  .productos {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(260px,1fr));
    gap: 20px;
    padding: 20px;
  }

  .producto {
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 3px 7px rgba(0,0,0,0.2);
    display: flex;
    flex-direction: column;
  }

  .producto img {
    width: 100%;
    height: 180px;
    object-fit: contain;
    background: #f0f0f0;
    border-bottom: 1px solid #ddd;
  }

  .producto h2 {
    margin: 15px 10px 10px;
    color: #ff6000;
    font-size: 1.3rem;
  }

  .descripcion {
    margin: 0 10px 10px;
    font-size: 0.9rem;
    color: #333;
  }

  .descripcion .parte-corta {
    display: inline;
  }

  .descripcion .parte-larga {
    display: none;
  }

  .leer-mas {
    color: #007bff;
    font-weight: bold;
    cursor: pointer;
    user-select: none;
  }

  .botones {
    display: flex;
    justify-content: space-around;
    padding: 15px 10px 20px;
    gap: 10px;
  }

  button.btn-carrito,
  a.btn-whatsapp {
    flex: 1;
    padding: 12px;
    border-radius: 6px;
    font-weight: bold;
    font-size: 1rem;
    border: none;
    cursor: pointer;
    text-align: center;
    text-decoration: none;
  }

  button.btn-carrito {
    background-color: #000;
    color: #fff;
    transition: background-color 0.3s ease;
  }

  button.btn-carrito:hover {
    background-color: #333;
  }

  a.btn-whatsapp {
    background-color: #25d366;
    color: #fff;
    display: inline-block;
  }

  a.btn-whatsapp:hover {
    background-color: #1ebe57;
  }
</style>
</head>
<body>

<header>TROGUI</header>

<div class="barra-carrito" onclick="mostrarCarrito()">
  🛒 Carrito: <span id="cantidad">0</span> producto(s> | Total: $<span id="total">0</span> COP
</div>

<div class="productos">

  <div class="producto" data-nombre="Organizador Esquinero" data-precio="50000">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/270260/1724105603four_trays_towel_bar.jpg" alt="Organizador Esquinero" />
    <h2>Organizador Esquinero</h2>
    <p class="descripcion">
      <span class="parte-corta">
        Optimiza tus espacios con este organizador resistente y elegante que se adapta a cualquier rincón.
      </span>
      <span class="parte-larga">
        Fabricado en acero inoxidable con acabado negro antióxido, soporta hasta 200 libras. Su diseño ventilado mantiene frutas y verduras frescas, y las ruedas giratorias con freno facilitan el movimiento sin rayar el suelo. Ideal para cocina, baño, oficina y más.
      </span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </p>
    <p style="margin: 0 10px 10px; font-weight: bold;">Precio: $50,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito(this)">Añadir al carrito</button>
      <a href="#" class="btn-whatsapp" onclick="comprarDirecto(this); return false;">Comprar por WhatsApp</a>
    </div>
  </div>

  <div class="producto" data-nombre="Estante Giratorio" data-precio="70000">
    <img src="https://image.made-in-china.com/2f0j00cMJViCrPkeGm/Estante-De-Almacenamiento-Giratorio-De-5-Niveles-Cesta-De-Verduras-Multicapa-Giratoria-De-360-Grados-Organizador-De-Metal-Y-PC-PARA-Cocina-10-Uds-.webp" alt="Estante Giratorio" />
    <h2>Estante Giratorio</h2>
    <p class="descripcion">
      <span class="parte-corta">
        Estante giratorio multiuso que facilita el acceso y organización de tus productos.
      </span>
      <span class="parte-larga">
        Cuenta con cinco niveles robustos fabricados en metal y plástico resistente, ideal para almacenar frutas, verduras o utensilios. Diseño anticorrosión y versátil, perfecto para cualquier espacio que requiera orden y funcionalidad.
      </span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </p>
    <p style="margin: 0 10px 10px; font-weight: bold;">Precio: $70,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito(this)">Añadir al carrito</button>
      <a href="#" class="btn-whatsapp" onclick="comprarDirecto(this); return false;">Comprar por WhatsApp</a>
    </div>
  </div>

  <div class="producto" data-nombre="Trapeador Giratorio" data-precio="30000">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/921548/1729192710171258895217018792991701879299Jkk7xvfHpZ5pl65qAuBlpNNcNECiV4wLumqrDTkN%20(1).jpg" alt="Trapeador Giratorio" />
    <h2>Trapeador Giratorio</h2>
    <p class="descripcion">
      <span class="parte-corta">
        Limpieza rápida y eficiente con este trapeador giratorio de microfibra ultra absorbente.
      </span>
      <span class="parte-larga">
        Su balde con sistema centrifugador 360° mantiene el agua limpia y reduce el esfuerzo. Ideal para todo tipo de pisos, atrapa polvo y suciedad de manera efectiva, haciéndote ahorrar tiempo y energía.
      </span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </p>
    <p style="margin: 0 10px 10px; font-weight: bold;">Precio: $30,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito(this)">Añadir al carrito</button>
      <a href="#" class="btn-whatsapp" onclick="comprarDirecto(this); return false;">Comprar por WhatsApp</a>
    </div>
  </div>

</div>

<script>
  let carrito = [];
  let cantidad = 0;
  let total = 0;

  // Alternar descripción corta/larga
  function toggleDescripcion(el) {
    const descripcion = el.parentElement;
    const corta = descripcion.querySelector('.parte-corta');
    const larga = descripcion.querySelector('.parte-larga');
    if (larga.style.display === 'inline') {
      larga.style.display = 'none';
      corta.style.display = 'inline';
      el.textContent = 'Leer más';
    } else {
      larga.style.display = 'inline';
      corta.style.display = 'none';
      el.textContent = 'Leer menos';
    }
  }

  // Añadir producto al carrito
  function agregarAlCarrito(btn) {
    const productoDiv = btn.closest('.producto');
    const nombre = productoDiv.getAttribute('data-nombre');
    const precio = parseInt(productoDiv.getAttribute('data-precio'));

    carrito.push({ nombre, precio });
    cantidad++;
    total += precio;

    document.getElementById('cantidad').textContent = cantidad;
    document.getElementById('total').textContent = total.toLocaleString();

    alert(`Agregaste "${nombre}" al carrito.`);
  }

  // Comprar solo ese producto ahora por WhatsApp
  function comprarDirecto(el) {
    const productoDiv = el.closest('.producto');
    const nombre = productoDiv.getAttribute('data-nombre');
    const precio = parseInt(productoDiv.getAttribute('data-precio'));

    const mensaje = `¡Hola! Quisiera realizar una compra en tu tienda.\n- ${nombre} ($${precio.toLocaleString()} COP)\n\n¿Puedes ayudarme con los detalles?`;
    const url = `https://wa.me/573206572598?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
  }

  // Mostrar carrito y enviar lista completa a WhatsApp
  function mostrarCarrito() {
    if (carrito.length === 0) {
      alert('El carrito está vacío.');
      return;
    }

    let mensaje = '¡Hola! Quisiera realizar una compra en tu tienda con los siguientes productos:\n\n';

    // Crear lista con productos y precio
    carrito.forEach((item, i) => {
      mensaje += `${i+1}. ${item.nombre} - $${item.precio.toLocaleString()} COP\n`;
    });

    mensaje += `\nTotal: $${total.toLocaleString()} COP\n\n¿Puedes ayudarme con los detalles?`;

    const url = `https://wa.me/573206572598?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
  }
</script>

</body>
</html>
