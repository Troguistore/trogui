<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Organizador Esquinero para Baño</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #ffffff;
            color: #000000;
        }
        header {
            background-color: #ff6600;
            padding: 20px;
            text-align: center;
            color: white;
        }
        header h1 {
            margin: 0;
            font-size: 24px;
            text-align: center;
        }
        header p {
            margin: 5px 0;
            font-size: 14px;
            text-align: center;
        }
        .container {
            padding: 20px;
            text-align: center;
        }
        .carousel {
            display: flex;
            overflow: hidden;
            width: 100%;
            max-width: 600px;
            margin: 20px auto;
        }
        .carousel img {
            width: 100%;
            transition: transform 0.5s ease-in-out;
        }
        .description {
            text-align: left;
            max-width: 600px;
            margin: 0 auto;
            padding: 10px;
        }
        .price {
            color: #ff6600;
            font-size: 24px;
            font-weight: bold;
            text-align: center;
            margin-top: 20px;
        }
        .buy-button {
            background-color: #28a745;
            color: white;
            padding: 15px;
            font-size: 18px;
            border: none;
            cursor: pointer;
            text-align: center;
            display: inline-block;
            margin-top: 20px;
            border-radius: 5px;
            animation: border-pulse 1.5s infinite;
        }
        .buy-button:hover {
            background-color: #218838;
        }
        .buy-button a {
            color: white;
            text-decoration: none;
        }
        @keyframes border-pulse {
            0% {
                box-shadow: 0 0 5px #28a745, 0 0 10px #28a745;
            }
            50% {
                box-shadow: 0 0 20px #28a745, 0 0 30px #28a745;
            }
            100% {
                box-shadow: 0 0 5px #28a745, 0 0 10px #28a745;
            }
        }
        .more-products {
            margin-top: 30px;
            font-size: 18px;
        }
        .more-products a {
            color: #ff6600;
            text-decoration: none;
            border: 2px solid #ff6600;
            padding: 10px 20px;
            border-radius: 5px;
            animation: border-pulse 1.5s infinite;
        }
        .more-products a:hover {
            background-color: #ff6600;
            color: white;
        }
    </style>
</head>
<body>
    <header>
        <h1>Organizador Esquinero para Baño</h1>
        <p>Envío gratis y pago contra entrega toda Colombia</p>
    </header>

    <div class="container">
        <!-- Carrusel de imágenes -->
        <div class="carousel">
            <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/591305/1704986444ESQUINERO%20BA%C3%91O%20GRANDE.webp" alt="Imagen 1 del producto">
            <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1007339/1721772949D_NQ_NP_936216-MCO71523561636_092023-O.webp" alt="Imagen 2 del producto">
            <img src="https://dojiw2m9tvv09.cloudfront.net/33039/product/0131-12400.jpg" alt="Imagen 3 del producto">
        </div>

        <!-- Descripción del producto -->
        <div class="description">
            <h2>Descripción</h2>
            <ul>
                <li>Altura ajustable: de 1 a 3 metros</li>
                <li>Ancho: 33.5 cm</li>
                <li>Profundidad de cada estante: 22 cm</li>
                <li>Niveles: 4 estantes</li>
                <li>Material: Estructura de acero inoxidable resistente y estantes de plástico de alto impacto, puede mojarlo sin problema porque no se va a oxidar</li>
                <li>Ligero y liviano</li>
                <li>No necesitas tornillos para instalar</li>
                <li>Diseño elegante</li>
                <li>Estabilidad y resistencia</li>
                <li>Optimiza el espacio</li>
                <li>Adaptable a cualquier esquina de la ducha</li>
                <li>Orificios de drenaje en repisas</li>
                <li>Tiempo de llegada: menos de 10 días</li>
                <li>Envío gratis y pago contra entrega toda Colombia</li>
            </ul>
        </div>

        <!-- Precio del producto -->
        <div class="price">Precio: 59,000 COP</div>

        <!-- Botón de WhatsApp -->
        <div class="buy-button">
            <a href="https://api.whatsapp.com/send?phone=+3206572598&text=*Hola%20quiero%20que%20me%20env%C3%ADes%20este%20producto*(%20Organizador%20Esquinero%20para%20Ba%C3%B1o_%20)%20*aqu%C3%AD%20te%20env%C3%ADo%20mi%20nombre%20y%20direcci%C3%B3n%20completa*%20(%20%20)%20(%20)%F0%9F%A5%B0" target="_blank">
                Comprar por WhatsApp
            </a>
        </div>

        <!-- Botón de "Mirar más productos" -->
        <div class="more-products">
            <a href="https://troguistore.github.io/Trogui-s/" target="_blank">Mirar más productos</a>
        </div>
    </div>

    <script>
        // Carrusel de imágenes
        let index = 0;
        const images = document.querySelectorAll('.carousel img');
        
        function showNextImage() {
            images[index].style.transform = 'translateX(-100%)';
            index = (index + 1) % images.length;
            images[index].style.transform = 'translateX(0)';
        }

        setInterval(showNextImage, 3000);
    </script>
</body>
</html>
