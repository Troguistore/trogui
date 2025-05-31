<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>TROGUI - Tienda Online</title>
<style>
  body {
    background-color: #ff6f00;
    font-family: Arial, sans-serif;
    margin: 0;
  }

  header {
    background-color: #000;
    color: #fff;
    text-align: center;
    padding: 10px;
    font-size: 18px;
    position: sticky;
    top: 0;
    z-index: 100;
  }

  .carrito-info {
    background-color: #fff;
    color: #000;
    text-align: center;
    padding: 8px;
    font-size: 14px;
  }

  .productos {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
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
    color: #ff6f00;
    font-size: 16px;
    margin: 10px;
  }

  .producto p {
    color: #333;
    font-size: 14px;
    margin: 0 10px 10px;
    max-height: 40px;
    overflow: hidden;
  }

  .producto .leer-mas {
    color: #000;
    font-size: 12px;
    margin: 0 10px 10px;
    cursor: pointer;
  }

  .boton {
    text-align: center;
    text-decoration: none;
    padding: 10px;
    margin: 5px 10px 10px;
    border-radius: 4px;
    font-size: 14px;
    display: block;
  }

  .boton-carrito {
    background-color: #ff6f00;
    color: #fff;
  }

  .boton-whatsapp {
    background-color: #25d366;
    color: #fff;
  }

  footer {
    text-align: center;
    font-size: 14px;
    color: #fff;
    padding: 10px;
    background-color: #ff6f00;
  }
</style>
<script>
  let carrito = [];
  let total = 0;

  function toggleDescripcion(el) {
    const p = el.previousElementSibling;
    if (p.style.maxHeight === 'none') {
      p.style.maxHeight = '40px';
      el.innerText = 'Leer más';
    } else {
      p.style.maxHeight = 'none';
      el.innerText = 'Leer menos';
    }
  }

  function añadirCarrito(nombre, precio) {
    carrito.push({ nombre, precio });
    total += precio;
    actualizarCarrito();
  }

  function actualizarCarrito() {
    const cantidad = carrito.length;
    document.getElementById('carrito-cantidad').innerText = cantidad;
    document.getElementById('carrito-total').innerText = total.toLocaleString('es-CO', { style: 'currency', currency: 'COP' });
  }

  function comprarWhatsApp() {
    if (carrito.length === 0) {
      alert('¡No has añadido productos al carrito!');
      return;
    }
    let mensaje = '¡Hola! Quisiera comprar los siguientes productos:\n\n';
    carrito.forEach((item, index) => {
      mensaje += `${index + 1}. ${item.nombre} - ${item.precio.toLocaleString('es-CO', { style: 'currency', currency: 'COP' })}\n`;
    });
    mensaje += `\nTotal: ${total.toLocaleString('es-CO', { style: 'currency', currency: 'COP' })}`;
    const enlace = `https://wa.me/573206572598?text=${encodeURIComponent(mensaje)}`;
    window.open(enlace, '_blank');
  }
</script>
</head>
<body>

<header>TROGUI - Carrito: <span id="carrito-cantidad">0</span> productos | Total: <span id="carrito-total">$0</span></header>

<div class="productos">

  <div class="producto">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/270260/1724105603four_trays_towel_bar.jpg" alt="Organizador Esquinero">
    <h2>Organizador Esquinero</h2>
    <p>Organizador esquinero para baño, resistente y práctico. ¡Aprovecha su diseño funcional y calidad superior para mantener tu espacio ordenado!</p>
    <div class="leer-mas" onclick="toggleDescripcion(this)">Leer más</div>
    <a class="boton boton-carrito" href="javascript:void(0)" onclick="añadirCarrito('Organizador Esquinero', 59000)">Añadir al carrito</a>
  </div>

  <div class="producto">
    <img src="https://image.made-in-china.com/2f0j00cMJViCrPkeGm/Estante-De-Almacenamiento-Giratorio-De-5-Niveles-Cesta-De-Verduras-Multicapa-Giratoria-De-360-Grados-Organizador-De-Metal-Y-PC-PARA-Cocina-10-Uds-.webp" alt="Estante Giratorio">
    <h2>Estante Giratorio</h2>
    <p>Estante giratorio de 5 niveles, ideal para frutas y verduras, giratorio 360°, ventilado y fácil de mover con ruedas bloqueables.</p>
    <div class="leer-mas" onclick="toggleDescripcion(this)">Leer más</div>
    <a class="boton boton-carrito" href="javascript:void(0)" onclick="añadirCarrito('Estante Giratorio', 239000)">Añadir al carrito</a>
  </div>

  <div class="producto">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/921548/1729192710171258895217018792991701879299Jkk7xvfHpZ5pl65qAuBlpNNcNECiV4wLumqrDTkN%20(1).jpg" alt="Trapeador Giratorio">
    <h2>Trapeador Giratorio</h2>
    <p>Trapeador con sistema de 360°, incluye dos cabezales de microfibra. Limpia rápido y fácil, perfecto para todo tipo de pisos.</p>
    <div class="leer-mas" onclick="toggleDescripcion(this)">Leer más</div>
    <a class="boton boton-carrito" href="javascript:void(0)" onclick="añadirCarrito('Trapeador Giratorio', 59000)">Añadir al carrito</a>
  </div>

</div>

<div style="text-align:center; margin: 20px;">
  <a class="boton boton-whatsapp" href="javascript:void(0)" onclick="comprarWhatsApp()">Comprar por WhatsApp</a>
</div>

<footer>&copy; 2025 TROGUI</footer>

</body>
</html>
