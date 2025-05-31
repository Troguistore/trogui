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
  }
  header {
    text-align: center;
    background-color: #ff6000;
    color: #000;
    font-size: 28px;
    font-weight: bold;
    padding: 15px;
  }
  .barra-carrito {
    background-color: #000;
    color: #fff;
    text-align: center;
    padding: 12px;
    font-size: 16px;
    font-weight: bold;
    display: flex;
    justify-content: center;
    gap: 20px;
    align-items: center;
  }
  .barra-carrito span {
    min-width: 120px;
  }
  .productos {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 20px;
    padding: 20px;
  }
  .producto {
    background: #fff;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .producto img {
    width: 100%;
    height: auto;
    object-fit: contain;
  }
  .producto h2 {
    color: #ff6000;
    margin: 10px;
    font-size: 20px;
  }
  .descripcion {
    color: #333;
    font-size: 14px;
    margin: 0 10px 10px;
    line-height: 1.4em;
    min-height: 56px; /* aprox 4 líneas */
  }
  .descripcion .mas {
    display: none;
  }
  .descripcion .leer-mas {
    color: #007bff;
    font-weight: bold;
    cursor: pointer;
    user-select: none;
  }
  .precio {
    margin: 10px;
    font-weight: bold;
    font-size: 16px;
  }
  .botones {
    display: flex;
    gap: 10px;
    margin: 10px;
  }
  .btn-carrito, .btn-whatsapp {
    flex: 1;
    padding: 12px 0;
    border: none;
    border-radius: 5px;
    font-size: 15px;
    cursor: pointer;
    font-weight: 600;
    transition: background-color 0.3s ease;
  }
  .btn-carrito {
    background-color: #000;
    color: #fff;
  }
  .btn-carrito:hover {
    background-color: #333;
  }
  .btn-whatsapp {
    background-color: #25d366;
    color: #fff;
  }
  .btn-whatsapp:hover {
    background-color: #1da851;
  }
  footer {
    text-align: center;
    color: #fff;
    padding: 15px;
    font-size: 14px;
    background-color: #ff6000;
  }
</style>
</head>
<body>

<header>TROGUI</header>

<div class="barra-carrito">
  <span>🛒 Productos: <strong id="cantidad">0</strong></span>
  <span>Total: $<strong id="total">0</strong> COP</span>
  <button class="btn-whatsapp" style="flex: 0 0 auto; padding: 10px 15px;" onclick="enviarWhatsAppCarrito()">Comprar por WhatsApp</button>
</div>

<div class="productos" id="productos">

  <!-- Producto 1 -->
  <div class="producto" data-nombre="Organizador Esquinero" data-precio="50000">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/270260/1724105603four_trays_towel_bar.jpg" alt="Organizador Esquinero" />
    <h2>Organizador Esquinero</h2>
    <div class="descripcion">
      <span class="preview"></span><span class="mas"></span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <div class="precio">Precio: $50,000 COP</div>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Organizador Esquinero', 50000)">Añadir al carrito</button>
      <button class="btn-whatsapp" onclick="comprarAhora('Organizador Esquinero', 50000)">Comprar por WhatsApp</button>
    </div>
  </div>

  <!-- Producto 2 -->
  <div class="producto" data-nombre="Estante Giratorio" data-precio="70000">
    <img src="https://image.made-in-china.com/2f0j00cMJViCrPkeGm/Estante-De-Almacenamiento-Giratorio-De-5-Niveles-Cesta-De-Verduras-Multicapa-Giratoria-De-360-Grados-Organizador-De-Metal-Y-PC-PARA-Cocina-10-Uds-.webp" alt="Estante Giratorio" />
    <h2>Estante Giratorio</h2>
    <div class="descripcion">
      <span class="preview"></span><span class="mas"></span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <div class="precio">Precio: $70,000 COP</div>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Estante Giratorio', 70000)">Añadir al carrito</button>
      <button class="btn-whatsapp" onclick="comprarAhora('Estante Giratorio', 70000)">Comprar por WhatsApp</button>
    </div>
  </div>

  <!-- Producto 3 -->
  <div class="producto" data-nombre="Trapeador Giratorio" data-precio="30000">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/921548/1729192710171258895217018792991701879299Jkk7xvfHpZ5pl65qAuBlpNNcNECiV4wLumqrDTkN%20(1).jpg" alt="Trapeador Giratorio" />
    <h2>Trapeador Giratorio</h2>
    <div class="descripcion">
      <span class="preview"></span><span class="mas"></span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <div class="precio">Precio: $30,000 COP</div>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Trapeador Giratorio', 30000)">Añadir al carrito</button>
      <button class="btn-whatsapp" onclick="comprarAhora('Trapeador Giratorio', 30000)">Comprar por WhatsApp</button>
    </div>
  </div>

</div>

<footer>&copy; 2025 TROGUI</footer>

<script>
  // Descripciones completas para cada producto
  const descripcionesCompletas = {
    "Organizador Esquinero": "Este organizador aprovecha cada rincón con estilo y funcionalidad. Fabricado en acero inoxidable con acabado negro antióxido, soporta hasta 200 libras y su diseño de cestas ventiladas evita la humedad y mantiene frutas y vegetales frescos. Con ruedas giratorias 360° y frenos para estabilidad, es ideal para cocinas, baños, oficinas y más.",
    "Estante Giratorio": "Un práctico organizador giratorio que maximiza tu espacio. Sus cinco niveles permiten almacenar frutas, verduras o artículos de limpieza con facilidad. Fabricado en metal y PC de alta resistencia, es resistente a la corrosión y puede colocarse en la cocina, baño o cualquier lugar que necesite orden.",
    "Trapeador Giratorio": "Limpieza fácil y rápida con el trapeador giratorio. Su cabezal de microfibra ultra absorbente atrapa la suciedad y el polvo con facilidad. El balde con sistema de centrifugado 360° mantiene el agua limpia y reduce el esfuerzo. ¡Ideal para pisos relucientes en menos tiempo!"
  };

  // Mostrar solo las primeras 15 palabras inicialmente
  function setupDescripcion() {
    const productos = document.querySelectorAll('.producto');
    productos.forEach(prod => {
      const nombre = prod.dataset.nombre;
      const fullText = descripcionesCompletas[nombre];
      const palabras = fullText.split(' ');
      const previewTexto = palabras.slice(0, 15).join(' ') + (palabras.length > 15 ? '...' : '');
      const previewSpan = prod.querySelector('.preview');
      const masSpan = prod.querySelector('.mas');
      previewSpan.textContent = previewTexto;
      masSpan.textContent = palabras.length > 15 ? palabras.slice(15).join(' ') : '';
    });
  }

  function toggleDescripcion(el) {
    const mas = el.previousElementSibling;
    if (mas.style.display === 'inline') {
      mas.style.display = 'none';
      el.textContent = 'Leer más';
    } else {
      mas.style.display = 'inline';
      el.textContent = 'Leer menos';
    }
  }

  // Carrito
  let carrito = [];
  let cantidad = 0;
  let total = 0;

  function actualizarBarra() {
    document.getElementById('cantidad').textContent = cantidad;
    document.getElementById('total').textContent = total.toLocaleString('es-CO');
  }

  function agregarAlCarrito(nombre, precio) {
    // Ver si ya existe el producto en el carrito
    const index = carrito.findIndex(p => p.nombre === nombre);
    if (index >= 0) {
      carrito[index].cantidad++;
    } else {
      carrito.push({ nombre, precio, cantidad: 1 });
    }
    cantidad++;
    total += precio;
    actualizarBarra();
    alert(`Agregaste "${nombre}" al carrito.`);
  }

  // Comprar un solo producto directamente
  function comprarAhora(nombre, precio) {
    const texto = `¡Hola! Quisiera realizar una compra en tu tienda. ¿Puedes ayudarme con los detalles de mi pedido? Producto: ${nombre} - Precio: $${precio.toLocaleString('es-CO')} COP`;
    const url = `https://wa.me/573206572598?text=${encodeURIComponent(texto)}`;
    window.open(url, '_blank');
  }

  // Comprar todos los productos del carrito
  function enviarWhatsAppCarrito() {
    if (carrito.length === 0) {
      alert("Tu carrito está vacío. Añade productos para comprar.");
      return;
    }

    let texto = "¡Hola! Quisiera realizar una compra en tu tienda. ¿Puedes ayudarme con los detalles de mi pedido? \n\nProductos:\n";
    carrito.forEach(p => {
      texto += `- ${p.nombre} x${p.cantidad} = $${(p.precio * p.cantidad).toLocaleString('es-CO')} COP\n`;
    });
    texto += `\nTotal: $${total.toLocaleString('es-CO')} COP`;

    const url = `https://wa.me/573206572598?text=${encodeURIComponent(texto)}`;
    window.open(url, '_blank');
  }

  // Inicializar descripciones
  setupDescripcion();
</script>

</body>
</html>
