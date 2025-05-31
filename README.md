<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
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
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
  }

  .productos {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 15px;
    padding: 20px;
  }

  .producto {
    background-color: #fff;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    display: flex;
    flex-direction: column;
  }

  .producto img {
    width: 100%;
    height: auto;
    display: block;
  }

  .producto h2 {
    color: #ff6000;
    font-size: 18px;
    margin: 10px;
  }

  .descripcion {
    color: #333;
    font-size: 14px;
    margin: 0 10px 10px;
  }

  .descripcion .mas {
    display: none;
  }

  .descripcion .leer-mas {
    color: #007bff;
    cursor: pointer;
    font-weight: bold;
  }

  .botones {
    display: flex;
    justify-content: space-around;
    margin: 10px;
  }

  .btn-carrito, .btn-whatsapp {
    flex: 1;
    margin: 0 5px;
    text-align: center;
    text-decoration: none;
    padding: 10px;
    border-radius: 4px;
    font-size: 14px;
    cursor: pointer;
  }

  .btn-carrito {
    background-color: #000;
    color: #fff;
  }

  .btn-whatsapp {
    background-color: #25d366;
    color: #fff;
  }

  footer {
    text-align: center;
    font-size: 14px;
    color: #fff;
    padding: 10px;
    background-color: #ff6000;
  }
</style>
</head>
<body>

<header>TROGUI</header>
<div class="barra-carrito" onclick="comprarCarrito()">
  🛒 Carrito: <span id="cantidad">0</span> producto(s) | Total: $<span id="total">0</span> COP
</div>

<div class="productos">

  <div class="producto">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/270260/1724105603four_trays_towel_bar.jpg" alt="Organizador Esquinero">
    <h2>Organizador Esquinero</h2>
    <div class="descripcion">
      Este organizador aprovecha cada rincón con estilo y funcionalidad.
      <span class="mas"> Fabricado en acero inoxidable con acabado negro antióxido, soporta hasta 200 libras y su diseño de cestas ventiladas evita la humedad y mantiene frutas y vegetales frescos. Con ruedas giratorias 360° y frenos para estabilidad, es ideal para cocinas, baños, oficinas y más.</span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <p style="margin: 10px;">Precio: $50,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Organizador Esquinero', 50000)">Añadir al carrito</button>
      <a class="btn-whatsapp" href="#" onclick="comprarAhora('Organizador Esquinero', 50000)">Comprar por WhatsApp</a>
    </div>
  </div>

  <div class="producto">
    <img src="https://image.made-in-china.com/2f0j00cMJViCrPkeGm/Estante-De-Almacenamiento-Giratorio-De-5-Niveles-Cesta-De-Verduras-Multicapa-Giratoria-De-360-Grados-Organizador-De-Metal-Y-PC-PARA-Cocina-10-Uds-.webp" alt="Estante Giratorio">
    <h2>Estante Giratorio</h2>
    <div class="descripcion">
      Un práctico organizador giratorio que maximiza tu espacio.
      <span class="mas"> Sus cinco niveles permiten almacenar frutas, verduras o artículos de limpieza con facilidad. Fabricado en metal y PC de alta resistencia, es resistente a la corrosión y puede colocarse en la cocina, baño o cualquier lugar que necesite orden.</span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <p style="margin: 10px;">Precio: $70,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Estante Giratorio', 70000)">Añadir al carrito</button>
      <a class="btn-whatsapp" href="#" onclick="comprarAhora('Estante Giratorio', 70000)">Comprar por WhatsApp</a>
    </div>
  </div>

  <div class="producto">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/921548/1729192710171258895217018792991701879299Jkk7xvfHpZ5pl65qAuBlpNNcNECiV4wLumqrDTkN%20(1).jpg" alt="Trapeador Giratorio">
    <h2>Trapeador Giratorio</h2>
    <div class="descripcion">
      Limpieza fácil y rápida con el trapeador giratorio.
      <span class="mas"> Su cabezal de microfibra ultra absorbente atrapa la suciedad y el polvo con facilidad. El balde con sistema de centrifugado 360° mantiene el agua limpia y reduce el esfuerzo. ¡Ideal para pisos relucientes en menos tiempo!</span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <p style="margin: 10px;">Precio: $30,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Trapeador Giratorio', 30000)">Añadir al carrito</button>
      <a class="btn-whatsapp" href="#" onclick="comprarAhora('Trapeador Giratorio', 30000)">Comprar por WhatsApp</a>
    </div>
  </div>

</div>

<footer>&copy; 2025 TROGUI</footer>

<script>
  let carrito = [];
  let cantidad = 0;
  let total = 0;

  function toggleDescripcion(elemento) {
    const mas = elemento.previousElementSibling;
    if (mas.style.display === 'inline') {
      mas.style.display = 'none';
      elemento.innerText = 'Leer más';
    } else {
      mas.style.display = 'inline';
      elemento.innerText = 'Leer menos';
    }
  }

  function agregarAlCarrito(nombre, precio) {
    carrito.push({ nombre, precio });
    cantidad++;
    total += precio;
    document.getElementById('cantidad').innerText = cantidad;
    document.getElementById('total').innerText = total.toLocaleString();
  }

  function comprarAhora(nombre, precio) {
    const mensaje = `¡Hola! Quiero comprar:\n- ${nombre} ($${precio.toLocaleString()} COP)\n\nGracias.`;
    const url = `https://wa.me/573206572598?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
  }

  function comprarCarrito() {
    if (carrito.length === 0) {
      alert('¡El carrito está vacío!');
      return;
    }
    let mensaje = '¡Hola! Quiero comprar:\n';
    carrito.forEach(item => {
      mensaje += `- ${item.nombre} ($${item.precio.toLocaleString()} COP)\n`;
    });
    mensaje += `\nTotal: $${total.toLocaleString()} COP\n\nGracias.`;
    const url = `https://wa.me/573206572598?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
  }
</script>

</body>
</html>
