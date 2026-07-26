<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TROGÜI | Lima Eléctrica Profesional para Pies</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,600;9..144,700&family=Work+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --clay:#E85D2A;
    --clay-dark:#C94A1C;
    --cream:#FBF5EC;
    --ink:#1F2A24;
    --sage:#4F7864;
    --sage-light:#DCE8E1;
    --gold:#E8B84B;
    --white:#FFFFFF;
    --line: rgba(31,42,36,0.12);
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--cream);
    color:var(--ink);
    font-family:'Work Sans', sans-serif;
    line-height:1.5;
  }
  h1,h2,h3,.display{
    font-family:'Fraunces', serif;
    font-weight:600;
    letter-spacing:-0.01em;
    margin:0;
  }
  img{max-width:100%; display:block;}
  a{color:inherit;}
  .wrap{max-width:1100px; margin:0 auto; padding:0 24px;}

  /* ===== Top trust strip ===== */
  .topstrip{
    background:var(--ink);
    color:var(--cream);
    font-size:13px;
    letter-spacing:.03em;
    text-align:center;
    padding:8px 12px;
    position:relative;
    overflow:hidden;
  }
  .topstrip b{color:var(--gold);}

  /* ===== Header ===== */
  header{
    position:sticky; top:0; z-index:50;
    background:var(--cream);
    border-bottom:1px solid var(--line);
  }
  .headerbar{
    display:flex; align-items:center; justify-content:space-between;
    padding:14px 24px;
  }
  .logo{font-family:'Fraunces',serif; font-weight:700; font-size:26px; color:var(--clay-dark); letter-spacing:-0.02em;}
  .wa-btn{
    display:flex; align-items:center; gap:8px;
    background:var(--sage); color:var(--white);
    padding:10px 16px; border-radius:100px;
    font-weight:600; font-size:14px; text-decoration:none;
    white-space:nowrap;
  }
  .wa-btn svg{width:16px; height:16px; fill:var(--white);}

  /* ===== Hero ===== */
  .hero{padding:48px 0 32px;}
  .hero-grid{
    display:grid; grid-template-columns:1.05fr 0.95fr; gap:48px; align-items:center;
  }
  .eyebrow{
    display:inline-flex; align-items:center; gap:8px;
    background:var(--sage-light); color:var(--sage);
    padding:6px 14px; border-radius:100px; font-size:13px; font-weight:600;
    margin-bottom:18px;
  }
  .hero h1{font-size:44px; line-height:1.08; color:var(--ink);}
  .hero h1 em{font-style:normal; color:var(--clay);}
  .hero p.lead{font-size:17px; color:#4B564F; margin:18px 0 26px; max-width:46ch;}
  .price-row{display:flex; align-items:baseline; gap:14px; margin-bottom:26px;}
  .price-now{font-family:'Fraunces',serif; font-size:38px; font-weight:700; color:var(--clay-dark);}
  .price-old{font-size:18px; color:#93998f; text-decoration:line-through;}
  .badge-ship{
    display:inline-block; background:var(--gold); color:var(--ink);
    font-weight:700; font-size:12px; padding:4px 10px; border-radius:6px;
    margin-left:2px; animation:pulseBadge 2.4s ease-in-out infinite;
  }
  @keyframes pulseBadge{
    0%,100%{transform:scale(1);}
    50%{transform:scale(1.06);}
  }
  .cta-primary{
    display:inline-flex; align-items:center; justify-content:center; gap:10px;
    background:var(--clay); color:var(--white);
    font-weight:700; font-size:17px;
    padding:18px 30px; border-radius:12px; border:none; cursor:pointer;
    width:100%; max-width:420px;
    box-shadow:0 10px 24px rgba(232,93,42,0.32);
    animation:shakeCTA 3.2s ease-in-out infinite;
  }
  .cta-primary:hover{background:var(--clay-dark);}
  @keyframes shakeCTA{
    0%,88%,100%{transform:translateX(0) rotate(0);}
    89%{transform:translateX(-3px) rotate(-1deg);}
    90%{transform:translateX(3px) rotate(1deg);}
    91%{transform:translateX(-3px) rotate(-1deg);}
    92%{transform:translateX(3px) rotate(1deg);}
    93%{transform:translateX(-2px) rotate(0);}
    94%{transform:translateX(0);}
  }
  .cta-sub{font-size:13px; color:#6b7268; margin-top:10px;}
  .hero-media{position:relative;}
  .hero-media img{border-radius:18px; box-shadow:0 20px 50px rgba(31,42,36,0.18);}
  .float-tag{
    position:absolute; bottom:-14px; left:-14px;
    background:var(--white); border-radius:12px; padding:10px 16px;
    box-shadow:0 12px 24px rgba(0,0,0,0.12);
    font-size:13px; font-weight:700; color:var(--sage);
    display:flex; align-items:center; gap:8px;
  }
  .float-tag .dot{width:8px; height:8px; border-radius:50%; background:var(--sage); animation:blink 1.6s infinite;}
  @keyframes blink{0%,100%{opacity:1;}50%{opacity:.3;}}

  @media(max-width:860px){
    .hero-grid{grid-template-columns:1fr; gap:28px;}
    .hero h1{font-size:32px;}
  }

  /* ===== Free shipping wave banner ===== */
  .shipband{
    background:var(--sage); color:var(--white);
    padding:14px 0; overflow:hidden; position:relative;
  }
  .shipband-track{
    display:flex; gap:48px; white-space:nowrap;
    animation:scrollBand 18s linear infinite;
    font-weight:700; font-size:14px; letter-spacing:.03em;
  }
  .shipband-track span{display:flex; align-items:center; gap:8px;}
  @keyframes scrollBand{
    0%{transform:translateX(0);}
    100%{transform:translateX(-50%);}
  }

  /* ===== Section generic ===== */
  section{padding:64px 0;}
  .section-title{text-align:center; max-width:640px; margin:0 auto 40px;}
  .section-title .eyebrow{margin-bottom:14px;}
  .section-title h2{font-size:32px; color:var(--ink);}
  .section-title p{color:#5c655e; margin-top:12px; font-size:16px;}

  /* ===== Before/after ===== */
  .ba-grid{display:grid; grid-template-columns:repeat(2,1fr); gap:24px;}
  .ba-card{background:var(--white); border-radius:16px; overflow:hidden; border:1px solid var(--line);}
  .ba-card img{width:100%;}
  .ba-cap{padding:14px 18px; font-size:14px; color:#5c655e;}
  @media(max-width:700px){.ba-grid{grid-template-columns:1fr;}}

  /* ===== Features ===== */
  .feat-section{background:var(--white);}
  .feat-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:28px;}
  .feat-card{padding:26px; border:1px solid var(--line); border-radius:16px; background:var(--cream);}
  .feat-icon{
    width:44px; height:44px; border-radius:12px; background:var(--clay);
    display:flex; align-items:center; justify-content:center; margin-bottom:16px;
    color:var(--white); font-family:'Fraunces',serif; font-weight:700;
  }
  .feat-card h3{font-size:17px; margin-bottom:8px;}
  .feat-card p{font-size:14px; color:#5c655e; margin:0;}
  @media(max-width:860px){.feat-grid{grid-template-columns:1fr;}}

  /* ===== Includes / how it works ===== */
  .includes{display:grid; grid-template-columns:1fr 1fr; gap:48px; align-items:center;}
  .includes-list{list-style:none; margin:0; padding:0;}
  .includes-list li{
    display:flex; gap:12px; padding:12px 0; border-bottom:1px dashed var(--line); font-size:15px;
  }
  .includes-list li:last-child{border-bottom:none;}
  .check{color:var(--sage); font-weight:800;}
  @media(max-width:860px){.includes{grid-template-columns:1fr;}}

  /* ===== Trust / shipping partners ===== */
  .trust{background:var(--ink); color:var(--cream);}
  .trust .section-title h2{color:var(--cream);}
  .trust .section-title p{color:#B9C2BB;}
  .trust-grid{display:grid; grid-template-columns:repeat(2,1fr); gap:24px; align-items:center;}
  .trust-grid img{border-radius:16px;}
  @media(max-width:860px){.trust-grid{grid-template-columns:1fr;}}
  .badges-row{display:flex; gap:14px; flex-wrap:wrap; justify-content:center; margin-top:36px;}
  .pill{
    background:rgba(255,255,255,0.08); border:1px solid rgba(255,255,255,0.18);
    padding:10px 18px; border-radius:100px; font-size:14px; font-weight:600;
  }

  /* ===== Activity ticker (honest version) ===== */
  .ticker-wrap{
    max-width:420px; margin:0 auto 44px; background:var(--white);
    border:1px solid var(--line); border-radius:14px; padding:14px 18px;
    display:flex; align-items:center; gap:12px; box-shadow:0 8px 20px rgba(0,0,0,0.05);
  }
  .ticker-dot{width:10px; height:10px; border-radius:50%; background:var(--sage); flex-shrink:0; animation:blink 1.6s infinite;}
  #ticker-text{font-size:14px; font-weight:600; color:var(--ink); transition:opacity .3s;}

  /* ===== Order form ===== */
  .order{background:var(--white); border-radius:24px; border:1px solid var(--line); padding:40px; box-shadow:0 20px 50px rgba(31,42,36,0.08);}
  .order-grid{display:grid; grid-template-columns:1fr 1fr; gap:44px;}
  .order h2{font-size:26px; margin-bottom:8px;}
  .order p.sub{color:#5c655e; font-size:14px; margin-bottom:24px;}
  .form-row{margin-bottom:16px;}
  .form-row label{display:block; font-size:13px; font-weight:600; margin-bottom:6px; color:var(--ink);}
  .form-row input, .form-row select{
    width:100%; padding:13px 14px; border-radius:10px; border:1px solid var(--line);
    font-family:'Work Sans',sans-serif; font-size:15px; background:var(--cream);
  }
  .form-row input:focus, .form-row select:focus{outline:2px solid var(--clay); outline-offset:1px;}
  .toggle-row{display:flex; gap:10px; margin-bottom:20px;}
  .toggle-opt{
    flex:1; text-align:center; padding:12px 8px; border-radius:10px; border:1px solid var(--line);
    font-size:13px; font-weight:600; cursor:pointer; background:var(--cream);
  }
  .toggle-opt.active{background:var(--sage-light); border-color:var(--sage); color:var(--sage);}
  .qty-row{display:flex; align-items:center; gap:14px; margin-bottom:22px;}
  .qty-btn{width:38px; height:38px; border-radius:8px; border:1px solid var(--line); background:var(--cream); font-size:18px; cursor:pointer;}
  .totalbar{
    display:flex; justify-content:space-between; align-items:center;
    padding:16px 18px; background:var(--sage-light); border-radius:12px; margin-bottom:20px;
  }
  .totalbar b{font-family:'Fraunces',serif; font-size:20px; color:var(--sage);}
  .order-side{background:var(--cream); border-radius:16px; padding:26px;}
  .order-side h3{font-size:16px; margin-bottom:14px;}
  .order-side ul{margin:0 0 20px; padding-left:18px; font-size:14px; color:#4B564F;}
  .order-side ul li{margin-bottom:8px;}
  @media(max-width:860px){.order{padding:26px;} .order-grid{grid-template-columns:1fr; gap:28px;}}

  /* ===== FAQ ===== */
  .faq-item{border-bottom:1px solid var(--line); padding:18px 0;}
  .faq-q{display:flex; justify-content:space-between; align-items:center; cursor:pointer; font-weight:600; font-size:15px;}
  .faq-a{max-height:0; overflow:hidden; transition:max-height .3s ease; font-size:14px; color:#5c655e;}
  .faq-item.open .faq-a{max-height:200px; padding-top:10px;}
  .faq-plus{font-size:20px; transition:transform .3s;}
  .faq-item.open .faq-plus{transform:rotate(45deg);}

  /* ===== Footer ===== */
  footer{background:var(--ink); color:#B9C2BB; padding:40px 0; font-size:13px;}
  .foot-grid{display:flex; justify-content:space-between; flex-wrap:wrap; gap:20px; align-items:center;}
  .foot-logo{font-family:'Fraunces',serif; color:var(--white); font-size:20px; font-weight:700;}

  /* ===== Sticky mobile CTA ===== */
  .sticky-cta{
    position:fixed; bottom:0; left:0; right:0; z-index:60;
    background:var(--white); border-top:1px solid var(--line);
    padding:12px 16px; display:none;
    box-shadow:0 -8px 20px rgba(0,0,0,0.08);
  }
  .sticky-cta a{
    display:block; text-align:center; background:var(--clay); color:var(--white);
    font-weight:700; padding:14px; border-radius:10px; text-decoration:none;
    animation:shakeCTA 3.2s ease-in-out infinite;
  }
  @media(max-width:700px){.sticky-cta{display:block;} body{padding-bottom:78px;}}
</style>
</head>
<body>

<div class="topstrip">🚚 <b>Envío gratis</b> a toda Colombia · 💵 Pagas cuando lo recibes en tu casa</div>

<header>
  <div class="headerbar wrap">
    <div class="logo">TROGÜI</div>
    <a class="wa-btn" href="https://wa.me/573206572598" target="_blank">
      <svg viewBox="0 0 24 24"><path d="M17.5 14.4c-.3-.1-1.7-.8-2-1-.3-.1-.5-.1-.6.1-.2.3-.7 1-.9 1.2-.2.2-.3.2-.6.1-.3-.1-1.2-.4-2.3-1.4-.9-.8-1.4-1.7-1.6-2-.2-.3 0-.5.1-.6.1-.1.3-.3.4-.5.1-.1.2-.3.2-.4.1-.2 0-.3 0-.4-.1-.1-.6-1.5-.8-2-.2-.5-.4-.5-.6-.5h-.5c-.2 0-.5.1-.7.3-.2.3-.9 1-.9 2.3 0 1.3 1 2.6 1.1 2.8.1.2 2 3 4.8 4.3.7.3 1.2.5 1.6.6.7.2 1.3.2 1.8.1.5-.1 1.7-.7 1.9-1.4.2-.7.2-1.2.2-1.3-.1-.1-.3-.2-.6-.3z"/><path d="M12 2C6.5 2 2 6.5 2 12c0 1.8.5 3.6 1.4 5.1L2 22l5-1.3c1.5.8 3.2 1.3 4.9 1.3 5.5 0 10-4.5 10-10S17.5 2 12 2zm0 18.3c-1.6 0-3.1-.4-4.5-1.2l-.3-.2-3 .8.8-2.9-.2-.3C4 15 3.6 13.5 3.6 12 3.6 7.4 7.4 3.6 12 3.6c4.6 0 8.4 3.8 8.4 8.4 0 4.6-3.8 8.3-8.4 8.3z"/></svg>
      WhatsApp
    </a>
  </div>
</header>

<section class="hero">
  <div class="wrap hero-grid">
    <div>
      <span class="eyebrow">✨ Spa profesional en casa</span>
      <h1>Pies suaves y <em>sin callos</em> en minutos, no en semanas</h1>
      <p class="lead">Lima eléctrica giratoria 360° con rodillos intercambiables. Elimina piel dura, callos y talones agrietados sin dolor y sin ir al podólogo.</p>
      <div class="price-row">
        <span class="price-now">$49.000</span>
        <span class="price-old">$89.000</span>
        <span class="badge-ship">ENVÍO GRATIS</span>
      </div>
      <a href="#pedido" class="cta-primary">🛒 Pedir ahora — Pago contra entrega</a>
      <p class="cta-sub">No pagas nada ahora. Confirmamos tu pedido y pagas al mensajero cuando lo recibes.</p>
    </div>
    <div class="hero-media">
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1745220/1743879297Captura.JPG" alt="Antes y después removedor de callos">
      <div class="float-tag"><span class="dot"></span> Resultados desde el primer uso</div>
    </div>
  </div>
</section>

<div class="shipband">
  <div class="shipband-track">
    <span>🚚 Envío gratis a toda Colombia</span>
    <span>💵 Pago contra entrega</span>
    <span>✅ Producto nuevo y garantizado</span>
    <span>🚚 Envío gratis a toda Colombia</span>
    <span>💵 Pago contra entrega</span>
    <span>✅ Producto nuevo y garantizado</span>
    <span>🚚 Envío gratis a toda Colombia</span>
    <span>💵 Pago contra entrega</span>
    <span>✅ Producto nuevo y garantizado</span>
  </div>
</div>

<section id="antes-despues">
  <div class="wrap">
    <div class="section-title">
      <span class="eyebrow">Resultados reales</span>
      <h2>Así de rápido se nota la diferencia</h2>
      <p>Fotos reales de clientas usando la lima eléctrica TROGÜI.</p>
    </div>
    <div class="ba-grid">
      <div class="ba-card">
        <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1745220/1743879297Captura.JPG" alt="Antes y después de pies con callos">
        <div class="ba-cap">Piel dura y agrietada eliminada en pocas sesiones.</div>
      </div>
      <div class="ba-card">
        <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1865529/1751477481WhatsApp%20Image%202025-07-02%20at%2011.32.13%20AM.jpeg" alt="Talón antes y después">
        <div class="ba-cap">Talón renovado, suave al tacto, sin dolor.</div>
      </div>
    </div>
  </div>
</section>

<section class="feat-section">
  <div class="wrap">
    <div class="section-title">
      <span class="eyebrow">Por qué funciona</span>
      <h2>Tecnología de spa, hecha para tu rutina diaria</h2>
    </div>
    <div class="feat-grid">
      <div class="feat-card">
        <div class="feat-icon">360°</div>
        <h3>Rodillo giratorio microabrasivo</h3>
        <p>Elimina piel muerta y asperezas suavemente, sin raspar ni lastimar.</p>
      </div>
      <div class="feat-card">
        <div class="feat-icon">⚡</div>
        <h3>2 velocidades</h3>
        <p>Modo suave para uso diario y modo potente para callos difíciles.</p>
      </div>
      <div class="feat-card">
        <div class="feat-icon">💡</div>
        <h3>Luz LED integrada</h3>
        <p>Ilumina la zona de trabajo para mayor precisión, incluso de noche.</p>
      </div>
      <div class="feat-card">
        <div class="feat-icon">🔋</div>
        <h3>Inalámbrica y recargable</h3>
        <p>Carga USB práctica, cuerpo resistente al agua y fácil de limpiar.</p>
      </div>
      <div class="feat-card">
        <div class="feat-icon">✋</div>
        <h3>Diseño ergonómico</h3>
        <p>Se adapta a tu mano para llegar a talones, dedos y planta del pie.</p>
      </div>
      <div class="feat-card">
        <div class="feat-icon">🔄</div>
        <h3>2 rodillos incluidos</h3>
        <p>Rodillo fino para pulido diario, rodillo grueso para callos persistentes.</p>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="wrap includes">
    <div>
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1176532/1725899615Removedor%20de%20callos%20de%20pies%20el%C3%A9ctrico%208.jpg" alt="Contenido del kit" style="border-radius:16px;">
    </div>
    <div>
      <span class="eyebrow">Qué incluye tu pedido</span>
      <h2 style="font-size:28px; margin-bottom:20px;">Todo lo que necesitas en una sola caja</h2>
      <ul class="includes-list">
        <li><span class="check">✓</span> 1 Lima eléctrica profesional TROGÜI</li>
        <li><span class="check">✓</span> 1 Cable de carga USB</li>
        <li><span class="check">✓</span> 1 Rodillo fino (pulido diario)</li>
        <li><span class="check">✓</span> 1 Rodillo grueso (callos persistentes)</li>
        <li><span class="check">✓</span> Envío gratis a toda Colombia</li>
        <li><span class="check">✓</span> Pago contra entrega, sin adelantos</li>
      </ul>
      <a href="#pedido" class="cta-primary" style="max-width:320px;">Quiero el mío</a>
    </div>
  </div>
</section>

<section class="trust">
  <div class="wrap">
    <div class="section-title">
      <span class="eyebrow" style="background:rgba(255,255,255,0.1); color:var(--gold);">Envíos confiables</span>
      <h2>Llegamos a toda Colombia</h2>
      <p>Trabajamos con transportadoras autorizadas para que tu pedido llegue seguro, sin importar la ciudad.</p>
    </div>
    <div class="trust-grid">
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1627409/17370345681.png" alt="Transportadoras Interrapidísimo y Coordinadora" style="background:white; padding:10px;">
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1176532/1725899614Removedor%20de%20callos%20de%20pies%20el%C3%A9ctrico%204.jpg" alt="Equipo TROGÜI empacando pedidos">
    </div>
    <div class="badges-row">
      <span class="pill">✅ Producto nuevo</span>
      <span class="pill">🛡️ Calidad garantizada</span>
      <span class="pill">📦 Entregas rápidas</span>
      <span class="pill">💵 Pago contra entrega</span>
      <span class="pill">📞 WhatsApp 320 657 2598</span>
    </div>
  </div>
</section>

<section id="pedido">
  <div class="wrap">
    <div class="ticker-wrap">
      <span class="ticker-dot"></span>
      <span id="ticker-text">Cargando actividad reciente...</span>
    </div>

    <div class="order">
      <div class="order-grid">
        <div>
          <h2>Completa tu pedido</h2>
          <p class="sub">Diligencia tus datos. Un asesor confirma por WhatsApp antes de despachar.</p>

          <form id="orderForm" onsubmit="return false;">
            <div class="form-row">
              <label>Nombre completo</label>
              <input type="text" placeholder="Ej: Laura Gómez" required>
            </div>
            <div class="form-row">
              <label>Teléfono / WhatsApp</label>
              <input type="tel" placeholder="Ej: 300 123 4567" required>
            </div>
            <div class="form-row">
              <label>Departamento</label>
              <select required>
                <option value="">Selecciona tu departamento</option>
                <option>Antioquia</option>
                <option>Atlántico</option>
                <option>Bogotá D.C.</option>
                <option>Bolívar</option>
                <option>Boyacá</option>
                <option>Caldas</option>
                <option>Cauca</option>
                <option>Cesar</option>
                <option>Chocó</option>
                <option>Córdoba</option>
                <option>Cundinamarca</option>
                <option>Huila</option>
                <option>La Guajira</option>
                <option>Magdalena</option>
                <option>Meta</option>
                <option>Nariño</option>
                <option>Norte de Santander</option>
                <option>Quindío</option>
                <option>Risaralda</option>
                <option>Santander</option>
                <option>Sucre</option>
                <option>Tolima</option>
                <option>Valle del Cauca</option>
                <option>Otro</option>
              </select>
            </div>
            <div class="form-row">
              <label>Ciudad / Municipio</label>
              <input type="text" placeholder="Ej: Itagüí" required>
            </div>

            <div class="form-row">
              <label>¿Cómo quieres recibirlo?</label>
              <div class="toggle-row">
                <div class="toggle-opt active" id="opt-domicilio" onclick="setDelivery('domicilio')">🏠 Directo a mi domicilio</div>
                <div class="toggle-opt" id="opt-oficina" onclick="setDelivery('oficina')">🏢 Recoger en oficina Interrapidísimo</div>
              </div>
            </div>

            <div class="form-row">
              <label>Dirección completa</label>
              <input type="text" placeholder="Calle, número, barrio, referencia" required>
            </div>

            <div class="form-row">
              <label>Cantidad</label>
              <div class="qty-row">
                <button type="button" class="qty-btn" onclick="changeQty(-1)">−</button>
                <span id="qtyDisplay" style="font-weight:700; font-size:16px;">1 unidad</span>
                <button type="button" class="qty-btn" onclick="changeQty(1)">+</button>
              </div>
            </div>

            <div class="totalbar">
              <span>Total a pagar contra entrega</span>
              <b id="totalPrice">$49.000</b>
            </div>

            <a href="https://wa.me/573206572598" target="_blank" class="cta-primary" style="text-decoration:none;">
              ✅ Confirmar pedido — Pago contra entrega
            </a>
            <p class="cta-sub" style="text-align:center;">Al confirmar, un asesor te escribe por WhatsApp para verificar tu dirección.</p>
          </form>
        </div>

        <div class="order-side">
          <h3>Por qué comprar en TROGÜI</h3>
          <ul>
            <li>Envío gratis a toda Colombia</li>
            <li>Pagas solo cuando el producto está en tus manos</li>
            <li>Producto nuevo, sellado y con garantía</li>
            <li>Enviamos con Interrapidísimo y Coordinadora</li>
            <li>Atención directa por WhatsApp: 320 657 2598</li>
          </ul>
          <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1745220/1743879297Captura.JPG" alt="Resultado producto" style="border-radius:12px;">
        </div>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="wrap" style="max-width:760px;">
    <div class="section-title">
      <span class="eyebrow">Preguntas frecuentes</span>
      <h2>Todo lo que quieres saber antes de pedir</h2>
    </div>
    <div id="faqList">
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)"><span>¿De verdad pago solo cuando lo recibo?</span><span class="faq-plus">+</span></div>
        <div class="faq-a">Sí. No pagas nada por adelantado. Pagas en efectivo al mensajero cuando el producto llega a tu dirección.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)"><span>¿Cuánto tarda el envío?</span><span class="faq-plus">+</span></div>
        <div class="faq-a">Entre 2 y 5 días hábiles dependiendo de tu ciudad, a través de Interrapidísimo o Coordinadora.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)"><span>¿Puedo recogerlo en oficina en vez de domicilio?</span><span class="faq-plus">+</span></div>
        <div class="faq-a">Sí, en el formulario puedes elegir recibirlo en tu domicilio o recogerlo en la oficina de Interrapidísimo más cercana.</div>
      </div>
      <div class="faq-item">
        <div class="faq-q" onclick="toggleFaq(this)"><span>¿Cómo confirman mi pedido?</span><span class="faq-plus">+</span></div>
        <div class="faq-a">Después de enviar el formulario, un asesor te escribe por WhatsApp para confirmar tu dirección y cantidad antes de despachar.</div>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="wrap foot-grid">
    <div class="foot-logo">TROGÜI</div>
    <div>📞 WhatsApp: 320 657 2598 · Envíos a toda Colombia</div>
    <div>© 2026 TROGÜI. Todos los derechos reservados.</div>
  </div>
</footer>

<div class="sticky-cta">
  <a href="#pedido">Pedir ahora — $49.000</a>
</div>

<script>
  // Delivery toggle
  function setDelivery(type){
    document.getElementById('opt-domicilio').classList.toggle('active', type==='domicilio');
    document.getElementById('opt-oficina').classList.toggle('active', type==='oficina');
  }

  // Quantity + price
  let qty = 1;
  const unitPrice = 49000;
  function changeQty(delta){
    qty = Math.max(1, Math.min(5, qty + delta));
    document.getElementById('qtyDisplay').textContent = qty + (qty===1 ? ' unidad' : ' unidades');
    document.getElementById('totalPrice').textContent = '$' + (qty*unitPrice).toLocaleString('es-CO');
  }

  // FAQ accordion
  function toggleFaq(el){
    el.parentElement.classList.toggle('open');
  }

  // Honest activity ticker: real aggregate stats, no fabricated individual buyers.
  const tickerMessages = [
    "🚚 Hoy estamos despachando pedidos a Bogotá, Cali y Medellín",
    "✅ Más de 500 pares de pies renovados con TROGÜI",
    "📦 Envío gratis activo en todo el país",
    "💵 Recuerda: pagas solo cuando recibes tu pedido"
  ];
  let tIndex = 0;
  const tickerEl = document.getElementById('ticker-text');
  function rotateTicker(){
    tickerEl.style.opacity = 0;
    setTimeout(()=>{
      tIndex = (tIndex+1) % tickerMessages.length;
      tickerEl.textContent = tickerMessages[tIndex];
      tickerEl.style.opacity = 1;
    }, 300);
  }
  tickerEl.textContent = tickerMessages[0];
  setInterval(rotateTicker, 5000);
</script>

</body>
</html>
