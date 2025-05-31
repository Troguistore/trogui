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
    color: #333;
  }
  header {
    text-align: center;
    font-size: 32px;
    font-weight: bold;
    color: #000;
    padding: 20px 0;
  }
  .barra-carrito {
    background-color: #000;
    color: #fff;
    padding: 12px 0;
    font-size: 18px;
    text-align: center;
    user-select: none;
    cursor: pointer;
  }
  .productos {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
    gap: 20px;
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto 40px;
  }
  .producto {
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 3px 8px rgba(0,0,0,0.2);
    overflow: hidden;
    display: flex;
    flex-direction: column;
  }
  .producto img {
    width: 100%;
    height: auto;
    object-fit: contain;
  }
  .producto h2 {
    color: #ff6000;
    font-size: 20px;
    margin: 12px 15px 6px;
  }
  .descripcion {
    font-size: 14px;
    margin: 0 15px 12px;
    line-height: 1.4;
  }
  .descripcion .texto-visible {
    display: inline;
  }
  .descripcion .texto-oculto {
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
    gap: 10px;
    margin: 0 15px 15px;
  }
  .btn-carrito, .btn-whatsapp {
    flex: 1;
    padding: 10px;
    font-size: 15px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    color: white;
    text-align: center;
    user-select: none;
  }
  .btn-carrito {
    background-color: #000;
  }
  .btn-whatsapp {
    background-color: #25d366;
    text-decoration: none;
    display: inline-block;
  }
  footer {
    text-align: center;
    color: #fff;
    padding: 12px 0;
    font-size: 14px;
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
    <div class="descripcion" data-texto-completo="Fabricado en acero inoxidable con acabado negro antióxido, este organizador esquinero soporta hasta 200 libras. Su diseño ventilado mantiene frutas y verduras frescas y evita la humedad. Cuenta con ruedas giratorias 360° con frenos para movilidad y estabilidad. Ideal para cocinas, baños, oficinas y más. No requiere instalación y es fácil de limpiar.">
      <span class="texto-visible"></span><span class="texto-oculto"></span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <p style="margin: 0 15px 10px; font-weight:bold;">Precio: $50,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Organizador Esquinero', 50000)">Añadir al carrito</button>
      <a class="btn-whatsapp" href="#" onclick="comprarAhora('Organizador Esquinero', 50000)">Comprar por WhatsApp</a>
    </div>
  </div>

  <div class="producto">
    <img src="https://image.made-in-china.com/2f0j00cMJViCrPkeGm/Estante-De-Almacenamiento-Giratorio-De-5-Niveles-Cesta-De-Verduras-Multicapa-Giratoria-De-360-Grados-Organizador-De-Metal-Y-PC-PARA-Cocina-10-Uds-.webp" alt="Estante Giratorio">
    <h2>Estante Giratorio</h2>
    <div class="descripcion" data-texto-completo="Este estante giratorio de 5 niveles maximiza el espacio de almacenamiento. Fabricado con metal resistente y PC duradero, es ideal para almacenar frutas, verduras y artículos de limpieza. Su diseño giratorio de 360 grados facilita el acceso y mantiene tu cocina o baño ordenados y limpios. Resistente a la corrosión y fácil de limpiar.">
      <span class="texto-visible"></span><span class="texto-oculto"></span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <p style="margin: 0 15px 10px; font-weight:bold;">Precio: $70,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Estante Giratorio', 70000)">Añadir al carrito</button>
      <a class="btn-whatsapp" href="#" onclick="comprarAhora('Estante Giratorio', 70000)">Comprar por WhatsApp</a>
    </div>
  </div>

  <div class="producto">
    <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/921548/1729192710171258895217018792991701879299Jkk7xvfHpZ5pl65qAuBlpNNcNECiV4wLumqrDTkN%20(1).jpg" alt="Trapeador Giratorio">
    <h2>Trapeador Giratorio</h2>
    <div class="descripcion" data-texto-completo="Trapeador con cabezal de microfibra ultra absorbente que atrapa suciedad y polvo. Su balde con sistema centrifugador 360° mantiene el agua limpia mientras limpias, ahorrando esfuerzo y tiempo. Perfecto para mantener pisos impecables en menos tiempo, con alta durabilidad y facilidad de uso.">
      <span class="texto-visible"></span><span class="texto-oculto"></span>
      <span class="leer-mas" onclick="toggleDescripcion(this)">Leer más</span>
    </div>
    <p style="margin: 0 15px 10px; font-weight:bold;">Precio: $30,000 COP</p>
    <div class="botones">
      <button class="btn-carrito" onclick="agregarAlCarrito('Trapeador Giratorio', 30000)">Añadir al carrito</button>
      <a class="btn-whatsapp" href="#" onclick="comprarAhora('Trapeador Giratorio', 30000)">Comprar por WhatsApp</a>
    </div>
  </div>

</div>

<footer>&copy; 2025 TROGUI</footer>

<script>
  // Función para mostrar solo las primeras 15 palabras y ocultar el resto
  function inicializarDescripciones() {
    const descripciones = document.querySelectorAll('.descripcion');
    descripciones.forEach(desc => {
      const textoCompleto = desc.getAttribute('data-texto-completo').trim();
      const palabras = textoCompleto.split(' ');
      if (palabras.length <= 15) {
        // Si tiene 15 o menos palabras, mostrar todo y ocultar botón leer más
        desc.querySelector('.texto-visible').textContent = textoCompleto;
        desc.querySelector('.leer-mas').style.display = 'none';
      } else {
        const visibles = palabras.slice(0, 15).join(' ') + '... ';
        const ocultas = palabras.slice(15).join(' ');
        desc.querySelector('.texto-visible').textContent = visibles;
        desc.querySelector('.texto-oculto').textContent = ocultas;
        desc.querySelector('.texto-oculto').style.display = 'none';
      }
    });
  }

  function toggleDescripcion(elemento) {
    const desc = elemento.parentElement;
    const textoOculto = desc.querySelector('.texto-oculto');
    if (textoOculto.style.display === 'none') {
      textoOculto.style.display = 'inline';
      elemento.textContent = 'Leer menos';
      // quitar "..." de visible
      let textoVisible = desc.querySelector('.texto-visible').textContent;
      if (textoVisible.endsWith('... ')) {
        desc.querySelector('.texto-visible').textContent = textoVisible.slice(0, -4) + ' ';
      }
    } else {
      textoOculto.style.display = 'none';
      elemento.textContent = 'Leer más';
      // agregar "..." si no está
      let textoVisible = desc.querySelector('.texto-visible').textContent;
      if (!textoVisible.endsWith('... ')) {
        desc.querySelector('.texto-visible').textContent = textoVisible.trim() + '... ';
      }
    }
  }

  // Carrito global
  let carrito = [];
  let cantidad = 0;
  let total = 0;

  function agregarAlCarrito(nombre, precio) {
    carrito.push({ nombre, precio });
    cantidad++;
    total += precio;
    actualizarBarraCarrito();
  }

  function actualizarBarraCarrito() {
    document.getElementById('cantidad').innerText = cantidad;
    document.getElementById('total').innerText = total.toLocaleString();
  }

  function comprarAhora(nombre, precio) {
    const mensaje = `¡Hola! Quiero comprar:\n- ${nombre} ($${precio.toLocaleString()} COP)\n\nGracias.`;
    const url = `https://wa.me/573001234567?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
  }

  function comprarCarrito() {
    if (carrito.length === 0) {
      alert('El carrito está vacío.');
      return;
    }
    let mensaje = '¡Hola! Quiero comprar los siguientes productos:\n';
    carrito.forEach((item, index) => {
      mensaje += `${index + 1}. ${item.nombre} ($${item.precio.toLocaleString()} COP)\n`;
    });
    mensaje += `\nTotal: $${total.toLocaleString()} COP\n\nGracias.`;
    const url = `https://wa.me/573001234567?text=${encodeURIComponent(mensaje)}`;
    window.open(url, '_blank');
  }

  // Inicializamos las descripciones al cargar
  window.onload = inicializarDescripciones;
</script>

</body>
</html>
