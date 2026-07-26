<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1">
<title>Lima Eléctrica Spa Pies™ — Envío gratis + Pago contra entrega</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600;9..144,700&family=Work+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#1E2B25;
    --bg:#EFF5F0;
    --bg-soft:#FAFCF9;
    --pine:#173A31;
    --pine-2:#20493E;
    --coral:#E86A57;
    --coral-dark:#C6503F;
    --gold:#C89B3C;
    --line:rgba(23,58,49,0.14);
    --shadow:0 20px 45px -20px rgba(23,58,49,0.35);
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    font-family:'Work Sans',sans-serif;
    color:var(--ink);
    background:var(--bg);
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3,.display{
    font-family:'Fraunces',serif;
    font-weight:600;
    letter-spacing:-0.01em;
    margin:0;
  }
  img{max-width:100%;display:block;}
  a{color:inherit;}
  .wrap{max-width:1120px;margin:0 auto;padding:0 20px;}
  .eyebrow{
    font-size:12px;
    letter-spacing:0.14em;
    text-transform:uppercase;
    font-weight:700;
    color:var(--pine-2);
    opacity:0.75;
  }
  /* ---- top utility bar ---- */
  .topbar{background:var(--pine);color:#EFF5F0;font-size:13px;text-align:center;padding:8px 12px;font-weight:600;letter-spacing:0.01em;}
  .topbar span.dot{opacity:0.6;margin:0 8px;}

  /* ---- hero ---- */
  .hero{
    background:radial-gradient(120% 140% at 85% -10%, #2C5C4E 0%, var(--pine) 55%, #102820 100%);
    color:#F4F7F2;
    padding:38px 0 54px;
    position:relative;
    overflow:hidden;
  }
  .hero::after{
    content:"";
    position:absolute;
    right:-120px;top:-120px;
    width:360px;height:360px;
    border-radius:50%;
    border:1px solid rgba(255,255,255,0.12);
  }
  .hero::before{
    content:"";
    position:absolute;
    right:-40px;top:-40px;
    width:220px;height:220px;
    border-radius:50%;
    border:1px solid rgba(255,255,255,0.10);
  }
  .hero-grid{
    display:grid;
    grid-template-columns:1.05fr 0.95fr;
    gap:44px;
    align-items:center;
  }
  .badge-row{display:flex;flex-wrap:wrap;gap:8px;margin:18px 0 20px;}
  .badge{
    display:inline-flex;align-items:center;gap:6px;
    background:rgba(255,255,255,0.10);
    border:1px solid rgba(255,255,255,0.2);
    padding:7px 12px;border-radius:99px;
    font-size:12.5px;font-weight:600;
  }
  .hero h1{font-size:clamp(30px,4.2vw,46px);line-height:1.06;color:#fff;}
  .hero h1 em{font-style:normal;color:var(--gold);}
  .hero p.lead{font-size:17px;line-height:1.55;color:rgba(244,247,242,0.86);margin-top:16px;max-width:46ch;}
  .price-block{display:flex;align-items:baseline;gap:14px;margin:24px 0 6px;flex-wrap:wrap;}
  .price-old{font-size:19px;color:rgba(244,247,242,0.55);text-decoration:line-through;}
  .price-new{font-size:44px;font-family:'Fraunces',serif;font-weight:700;color:#fff;}
  .price-tag{font-size:13px;color:var(--gold);font-weight:700;}
  .cta{
    display:inline-flex;align-items:center;justify-content:center;gap:10px;
    background:var(--coral);color:#fff;border:none;
    font-family:'Work Sans',sans-serif;font-weight:700;font-size:16.5px;
    padding:17px 26px;border-radius:12px;cursor:pointer;
    box-shadow:0 14px 30px -10px rgba(232,106,87,0.6);
    text-decoration:none;
    transition:transform .15s ease, box-shadow .15s ease;
  }
  .cta:hover{transform:translateY(-2px);box-shadow:0 18px 34px -10px rgba(232,106,87,0.7);}
  .cta.block{width:100%;}
  .hero-cta-note{font-size:12.5px;color:rgba(244,247,242,0.65);margin-top:10px;}
  .hero-media{position:relative;}
  .hero-media img{
    border-radius:20px;
    box-shadow:var(--shadow);
    border:6px solid rgba(255,255,255,0.08);
  }
  .hero-media .float-card{
    position:absolute;bottom:-18px;left:-18px;
    background:#fff;color:var(--ink);
    border-radius:14px;padding:12px 16px;
    box-shadow:0 18px 30px -12px rgba(0,0,0,0.35);
    font-size:13px;font-weight:700;
    display:flex;align-items:center;gap:10px;
    max-width:230px;
  }
  .ring{
    width:34px;height:34px;border-radius:50%;
    border:3px solid var(--coral);
    border-top-color:transparent;
    flex:none;
    animation:spin 2.2s linear infinite;
  }
  @keyframes spin{to{transform:rotate(360deg);}}

  /* ---- trust strip ---- */
  .trust{background:var(--bg-soft);border-bottom:1px solid var(--line);padding:16px 0;}
  .trust-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;text-align:center;}
  .trust-grid div{font-size:12.5px;font-weight:700;color:var(--pine-2);}
  .trust-grid div span{display:block;font-size:20px;margin-bottom:4px;}

  /* ---- section shell ---- */
  section{padding:64px 0;}
  .section-head{max-width:640px;margin:0 auto 40px;text-align:center;}
  .section-head h2{font-size:clamp(24px,3.2vw,34px);margin-top:10px;}
  .section-head p{color:rgba(30,43,37,0.68);margin-top:12px;font-size:15.5px;line-height:1.6;}

  /* ---- problem/solution ---- */
  .agitate{background:var(--bg-soft);}
  .agitate-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;}
  .agitate-card{
    background:#fff;border:1px solid var(--line);border-radius:16px;padding:22px 20px;
  }
  .agitate-card .mark{
    width:38px;height:38px;border-radius:50%;background:rgba(232,106,87,0.12);
    color:var(--coral-dark);font-weight:800;display:flex;align-items:center;justify-content:center;
    margin-bottom:14px;font-size:15px;
  }
  .agitate-card h3{font-size:16.5px;margin-bottom:6px;}
  .agitate-card p{font-size:14px;color:rgba(30,43,37,0.68);line-height:1.55;margin:0;}

  /* ---- how it works ---- */
  .how{display:grid;grid-template-columns:0.95fr 1.05fr;gap:48px;align-items:center;}
  .how-steps{display:flex;flex-direction:column;gap:22px;}
  .step{display:flex;gap:16px;}
  .step .ring-num{
    width:44px;height:44px;border-radius:50%;flex:none;
    border:2.5px solid var(--pine-2);
    display:flex;align-items:center;justify-content:center;
    font-family:'Fraunces',serif;font-weight:700;color:var(--pine-2);
    position:relative;
  }
  .step .ring-num::before{
    content:"";position:absolute;inset:-7px;border-radius:50%;
    border:1px dashed rgba(23,58,49,0.25);
  }
  .step h3{font-size:16.5px;margin-bottom:5px;}
  .step p{font-size:14.5px;color:rgba(30,43,37,0.68);margin:0;line-height:1.55;}
  .how-media img{border-radius:18px;box-shadow:var(--shadow);}

  /* ---- features ---- */
  .features{background:var(--pine);color:#F4F7F2;}
  .features .section-head p{color:rgba(244,247,242,0.72);}
  .features .eyebrow{color:var(--gold);opacity:1;}
  .feature-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;}
  .feature-card{
    background:rgba(255,255,255,0.06);
    border:1px solid rgba(255,255,255,0.12);
    border-radius:16px;padding:22px 18px;
  }
  .feature-card .ico{font-size:24px;margin-bottom:12px;}
  .feature-card h3{font-size:15px;color:#fff;margin-bottom:6px;font-family:'Work Sans',sans-serif;font-weight:700;}
  .feature-card p{font-size:13.5px;color:rgba(244,247,242,0.72);margin:0;line-height:1.5;}

  /* ---- included ---- */
  .included-grid{display:grid;grid-template-columns:1fr 1fr;gap:36px;align-items:center;}
  .included-list{list-style:none;margin:0;padding:0;display:flex;flex-direction:column;gap:14px;}
  .included-list li{display:flex;gap:12px;align-items:flex-start;font-size:15px;}
  .included-list li b{display:block;font-size:15px;}
  .included-list li span.chk{
    width:22px;height:22px;border-radius:50%;background:var(--pine-2);color:#fff;
    display:flex;align-items:center;justify-content:center;font-size:12px;flex:none;margin-top:2px;
  }
  .included-media{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
  .included-media img{border-radius:14px;box-shadow:0 12px 24px -14px rgba(23,58,49,0.4);}

  /* ---- reviews ---- */
  .reviews{background:var(--bg-soft);}
  .review-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;}
  .review-card{background:#fff;border:1px solid var(--line);border-radius:16px;padding:20px;}
  .review-stars{color:var(--gold);font-size:14px;letter-spacing:2px;margin-bottom:10px;}
  .review-card p{font-size:14px;line-height:1.6;color:rgba(30,43,37,0.78);margin:0 0 14px;}
  .review-person{display:flex;align-items:center;gap:10px;}
  .review-avatar{
    width:34px;height:34px;border-radius:50%;background:var(--pine-2);color:#fff;
    display:flex;align-items:center;justify-content:center;font-weight:700;font-size:13px;flex:none;
  }
  .review-person span{font-size:13px;font-weight:700;display:block;}
  .review-person small{font-size:11.5px;color:rgba(30,43,37,0.5);}

  /* ---- faq ---- */
  .faq{max-width:760px;margin:0 auto;}
  .faq-item{border-bottom:1px solid var(--line);}
  .faq-q{
    width:100%;text-align:left;background:none;border:none;
    padding:18px 4px;font-family:'Work Sans',sans-serif;font-weight:700;font-size:15.5px;
    color:var(--ink);cursor:pointer;display:flex;justify-content:space-between;align-items:center;gap:12px;
  }
  .faq-q .plus{transition:transform .2s ease;font-size:20px;color:var(--coral-dark);flex:none;}
  .faq-item.open .faq-q .plus{transform:rotate(45deg);}
  .faq-a{max-height:0;overflow:hidden;transition:max-height .25s ease;}
  .faq-a p{font-size:14.5px;line-height:1.6;color:rgba(30,43,37,0.7);padding:0 4px 18px;margin:0;}

  /* ---- order form ---- */
  .order{background:radial-gradient(120% 140% at 15% 0%, #2C5C4E 0%, var(--pine) 55%, #102820 100%);color:#fff;}
  .order-grid{display:grid;grid-template-columns:0.9fr 1.1fr;gap:44px;align-items:flex-start;}
  .order-card{
    background:#fff;color:var(--ink);border-radius:20px;padding:28px;box-shadow:var(--shadow);
  }
  .order-card h3{font-size:20px;margin-bottom:4px;}
  .order-card .sub{font-size:13.5px;color:rgba(30,43,37,0.6);margin-bottom:20px;}
  .field{margin-bottom:14px;}
  .field label{display:block;font-size:13px;font-weight:700;margin-bottom:6px;color:var(--pine-2);}
  .field input,.field select{
    width:100%;padding:12px 13px;border-radius:10px;border:1.5px solid var(--line);
    font-family:'Work Sans',sans-serif;font-size:14.5px;background:#F8FAF8;color:var(--ink);
  }
  .field input:focus,.field select:focus{outline:2px solid var(--coral);outline-offset:1px;border-color:var(--coral);}
  .qty-row{display:flex;gap:10px;}
  .qty-opt{
    flex:1;border:1.5px solid var(--line);border-radius:12px;padding:12px 10px;text-align:center;cursor:pointer;
    font-size:12.5px;font-weight:700;
  }
  .qty-opt.active{border-color:var(--coral);background:rgba(232,106,87,0.08);color:var(--coral-dark);}
  .qty-opt .qty-price{display:block;font-family:'Fraunces',serif;font-size:17px;margin-top:4px;}
  .order-summary{display:flex;justify-content:space-between;font-size:14px;font-weight:700;margin:16px 0;padding-top:14px;border-top:1px dashed var(--line);}
  .order-note{font-size:12px;color:rgba(30,43,37,0.55);margin-top:12px;text-align:center;line-height:1.5;}
  .order-copy .eyebrow{color:var(--gold);opacity:1;}
  .order-copy h2{color:#fff;font-size:clamp(22px,3vw,30px);margin-top:10px;}
  .order-copy p{color:rgba(244,247,242,0.78);font-size:15px;margin-top:12px;line-height:1.6;max-width:44ch;}
  .order-copy ul{list-style:none;padding:0;margin:22px 0 0;display:flex;flex-direction:column;gap:12px;}
  .order-copy li{display:flex;gap:10px;font-size:14.5px;align-items:flex-start;}
  .order-copy li span.chk{
    width:20px;height:20px;border-radius:50%;background:rgba(255,255,255,0.14);
    display:flex;align-items:center;justify-content:center;font-size:11px;flex:none;margin-top:2px;
  }
  .countdown{display:flex;gap:10px;margin-top:24px;}
  .countdown div{background:rgba(255,255,255,0.1);border:1px solid rgba(255,255,255,0.18);border-radius:10px;padding:10px 14px;text-align:center;min-width:64px;}
  .countdown div b{display:block;font-family:'Fraunces',serif;font-size:20px;}
  .countdown div small{font-size:10px;text-transform:uppercase;letter-spacing:0.06em;opacity:0.7;}

  footer{background:#102820;color:rgba(244,247,242,0.6);padding:34px 0 100px;font-size:12.5px;text-align:center;}
  footer .wrap{display:flex;flex-direction:column;gap:8px;align-items:center;}

  .wa-float{
    position:fixed;bottom:18px;right:18px;z-index:50;
    background:#25D366;color:#fff;width:58px;height:58px;border-radius:50%;
    display:flex;align-items:center;justify-content:center;box-shadow:0 14px 26px -8px rgba(0,0,0,0.4);
    text-decoration:none;font-size:26px;
  }
  .sticky-cta{
    position:fixed;left:0;right:0;bottom:0;z-index:40;
    background:#fff;border-top:1px solid var(--line);
    padding:10px 14px;display:none;
    align-items:center;justify-content:space-between;gap:12px;
    box-shadow:0 -12px 24px -18px rgba(0,0,0,0.4);
  }
  .sticky-cta .p{font-size:13px;font-weight:700;color:var(--pine);}
  .sticky-cta .p small{display:block;font-weight:500;color:rgba(30,43,37,0.55);font-size:11px;}

  @media (max-width:880px){
    .hero-grid,.how,.included-grid,.order-grid{grid-template-columns:1fr;}
    .hero-media{order:-1;}
    .agitate-grid{grid-template-columns:1fr;}
    .feature-grid{grid-template-columns:1fr 1fr;}
    .review-grid{grid-template-columns:1fr;}
    .trust-grid{grid-template-columns:1fr 1fr;}
    .included-media{grid-template-columns:1fr 1fr;}
    .sticky-cta{display:flex;}
    section{padding:46px 0;}
    footer{padding-bottom:110px;}
  }
</style>
</head>
<body>

<div class="topbar">🚚 ENVÍO GRATIS A TODA COLOMBIA <span class="dot">•</span> 💵 PAGA CUANDO LO RECIBAS <span class="dot">•</span> 🛡️ GARANTÍA DE 30 DÍAS</div>

<header class="hero">
  <div class="wrap hero-grid">
    <div>
      <div class="badge-row">
        <span class="badge">⭐ 4.8/5 valoración</span>
        <span class="badge">🔋 Recargable USB</span>
        <span class="badge">⚙️ 2 velocidades</span>
      </div>
      <h1>Pies suaves y renovados <em>en minutos</em>, sin salir de casa</h1>
      <p class="lead">La Lima Eléctrica Profesional elimina la piel dura, los callos persistentes y los talones agrietados con un sistema giratorio 360° — como una sesión de spa, pero en tu propia casa.</p>
      <div class="price-block">
        <span class="price-old">$89.000</span>
        <span class="price-new">$49.000</span>
        <span class="price-tag">Ahorras $40.000 hoy</span>
      </div>
      <a href="#pedido" class="cta">Pedir ahora — pago contra entrega →</a>
      <p class="hero-cta-note">Sin tarjeta, sin anticipos. Revisas tu pedido y pagas al mensajero.</p>
    </div>
    <div class="hero-media">
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1176532/1725899615Removedor%20de%20callos%20de%20pies%20el%C3%A9ctrico%208.jpg" alt="Lima eléctrica para pies en uso">
      <div class="float-card"><span class="ring"></span> Rodillo giratorio 360° — resultados desde el primer uso</div>
    </div>
  </div>
</header>

<div class="trust">
  <div class="wrap trust-grid">
    <div><span>🚚</span>Envío gratis</div>
    <div><span>💵</span>Pago contra entrega</div>
    <div><span>⏱️</span>Entrega 2–5 días hábiles</div>
    <div><span>🔁</span>Garantía de cambio</div>
  </div>
</div>

<section class="agitate">
  <div class="wrap">
    <div class="section-head">
      <div class="eyebrow">El problema</div>
      <h2>¿Te suena familiar?</h2>
      <p>Los callos y talones agrietados no solo duelen — también te hacen dudar antes de usar sandalias.</p>
    </div>
    <div class="agitate-grid">
      <div class="agitate-card">
        <div class="mark">1</div>
        <h3>La piedra pómez ya no alcanza</h3>
        <p>Tallas y tallas y la piel dura vuelve a los pocos días, además de ser un método lento e incómodo.</p>
      </div>
      <div class="agitate-card">
        <div class="mark">2</div>
        <h3>La pedicura sale cara y toca pedir cita</h3>
        <p>Entre el tiempo y el costo de ir cada mes, terminas posponiéndolo — y el problema sigue ahí.</p>
      </div>
      <div class="agitate-card">
        <div class="mark">3</div>
        <h3>Las cuchillas de callos dan miedo</h3>
        <p>Un mal movimiento y puedes lastimarte. No es la forma más segura de cuidar tus pies en casa.</p>
      </div>
    </div>
  </div>
</section>

<section class="how">
  <div class="wrap how" style="display:grid;">
    <div class="how-steps">
      <div class="eyebrow">Cómo funciona</div>
      <h2 style="margin:10px 0 22px;font-size:clamp(22px,3vw,30px);">Spa profesional, en 3 pasos</h2>
      <div class="step">
        <div class="ring-num">1</div>
        <div><h3>Elige tu rodillo</h3><p>Rodillo fino para mantenimiento diario o rodillo grueso para callos más persistentes.</p></div>
      </div>
      <div class="step">
        <div class="ring-num">2</div>
        <div><h3>Selecciona la velocidad</h3><p>Modo suave para zonas sensibles o modo potente para piel muy endurecida.</p></div>
      </div>
      <div class="step">
        <div class="ring-num">3</div>
        <div><h3>Desliza sobre la piel seca</h3><p>El sistema giratorio 360° retira la piel muerta de forma pareja, sin esfuerzo ni dolor.</p></div>
      </div>
    </div>
    <div class="how-media">
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1176532/1725899614Removedor%20de%20callos%20de%20pies%20el%C3%A9ctrico%204.jpg" alt="Rodillos de la lima eléctrica">
    </div>
  </div>
</section>

<section class="features">
  <div class="wrap">
    <div class="section-head">
      <div class="eyebrow">Características</div>
      <h2>Diseñada para uso diario, real</h2>
      <p>Cada detalle pensado para que la uses cómodamente sin pensarlo dos veces.</p>
    </div>
    <div class="feature-grid">
      <div class="feature-card"><div class="ico">🌀</div><h3>Giro 360°</h3><p>Rodillos microabrasivos que eliminan la piel dura de forma pareja.</p></div>
      <div class="feature-card"><div class="ico">🔋</div><h3>Inalámbrica</h3><p>Carga por USB, cuerpo resistente al agua y fácil de limpiar.</p></div>
      <div class="feature-card"><div class="ico">💡</div><h3>Luz LED</h3><p>Ilumina la zona para mayor precisión, incluso en la noche.</p></div>
      <div class="feature-card"><div class="ico">⚙️</div><h3>2 velocidades</h3><p>Modo suave para uso diario y modo potente para callos difíciles.</p></div>
    </div>
  </div>
</section>

<section class="included">
  <div class="wrap included-grid">
    <div class="included-media">
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1627409/17370345681.png" alt="Contenido del kit">
      <img src="https://d39ru7awumhhs2.cloudfront.net/colombia/products/1745220/1743879297Captura.JPG" alt="Detalle del producto">
    </div>
    <div>
      <div class="eyebrow">Qué incluye tu pedido</div>
      <h2 style="margin:10px 0 20px;font-size:clamp(22px,3vw,30px);">Todo listo para tu primera sesión</h2>
      <ul class="included-list">
        <li><span class="chk">✓</span><div><b>1 Lima eléctrica</b>mango ergonómico, resistente al agua</div></li>
        <li><span class="chk">✓</span><div><b>1 Cable de carga USB</b>compatible con cualquier cargador o power bank</div></li>
        <li><span class="chk">✓</span><div><b>1 Rodillo fino</b>para pulido y mantenimiento diario</div></li>
        <li><span class="chk">✓</span><div><b>1 Rodillo grueso</b>para callos persistentes y piel muy dura</div></li>
      </ul>
    </div>
  </div>
</section>

<section class="reviews">
  <div class="wrap">
    <div class="section-head">
      <div class="eyebrow">Clientas</div>
      <h2>Lo que dicen quienes ya la probaron</h2>
      <p>Reseñas de ejemplo — reemplázalas por las opiniones reales de tus primeras clientas apenas empieces a vender.</p>
    </div>
    <div class="review-grid">
      <div class="review-card">
        <div class="review-stars">★★★★★</div>
        <p>"Fácil de usar y no fue nada brusca con la piel. En dos usos ya sentí los talones más suaves."</p>
        <div class="review-person"><div class="review-avatar">M</div><div><span>Clienta verificada</span><small>Bogotá</small></div></div>
      </div>
      <div class="review-card">
        <div class="review-stars">★★★★★</div>
        <p>"Llegó en 3 días y pagué contra entrega sin problema. La luz LED ayuda mucho a ver bien lo que haces."</p>
        <div class="review-person"><div class="review-avatar">L</div><div><span>Clienta verificada</span><small>Medellín</small></div></div>
      </div>
      <div class="review-card">
        <div class="review-stars">★★★★☆</div>
        <p>"Buena batería y silenciosa. El rodillo grueso funciona bien para las zonas más resecas del talón."</p>
        <div class="review-person"><div class="review-avatar">C</div><div><span>Clienta verificada</span><small>Cali</small></div></div>
      </div>
    </div>
  </div>
</section>

<section class="faqs">
  <div class="wrap">
    <div class="section-head">
      <div class="eyebrow">Preguntas frecuentes</div>
      <h2>Antes de pedir</h2>
    </div>
    <div class="faq">
      <div class="faq-item open">
        <button class="faq-q">¿Cómo funciona el pago contra entrega? <span class="plus">+</span></button>
        <div class="faq-a" style="max-height:120px;"><p>Haces tu pedido sin pagar nada ahora. Un mensajero lleva el producto a tu dirección y pagas en efectivo o transferencia al momento de recibirlo.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">¿Cuánto tarda el envío? <span class="plus">+</span></button>
        <div class="faq-a"><p>Entre 2 y 5 días hábiles según tu ciudad. Te contactamos por WhatsApp para confirmar la dirección antes de despachar.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">¿El envío realmente es gratis? <span class="plus">+</span></button>
        <div class="faq-a"><p>Sí, el costo de envío está incluido en el precio y no pagas nada adicional por transporte a ninguna parte de Colombia.</p></div>
      </div>
      <div class="faq-item">
        <button class="faq-q">¿Qué pasa si no me gusta? <span class="plus">+</span></button>
        <div class="faq-a"><p>Cuentas con 30 días de garantía por defectos de fabricación. Escríbenos por WhatsApp y te ayudamos con el cambio.</p></div>
      </div>
    </div>
  </div>
</section>

<section class="order" id="pedido">
  <div class="wrap order-grid">
    <div class="order-copy">
      <div class="eyebrow">Últimas unidades de esta semana</div>
      <h2>Completa tus datos y confírmanos por WhatsApp</h2>
      <p>Sin pagos en línea. Solo diligencias el formulario, uno de nuestros asesores te confirma el pedido y pagas cuando lo recibas en tu puerta.</p>
      <ul>
        <li><span class="chk">✓</span> Envío gratis a toda Colombia</li>
        <li><span class="chk">✓</span> Pago contra entrega, sin tarjeta</li>
        <li><span class="chk">✓</span> Garantía de 30 días</li>
      </ul>
      <div class="countdown" id="countdown">
        <div><b id="cd-h">00</b><small>Horas</small></div>
        <div><b id="cd-m">00</b><small>Min</small></div>
        <div><b id="cd-s">00</b><small>Seg</small></div>
      </div>
    </div>

    <div class="order-card">
      <h3>Haz tu pedido</h3>
      <div class="sub">Te escribimos por WhatsApp para confirmar antes de despachar.</div>

      <div class="field">
        <label>Cantidad</label>
        <div class="qty-row">
          <div class="qty-opt active" data-qty="1" data-price="49000">1 unidad<span class="qty-price">$49.000</span></div>
          <div class="qty-opt" data-qty="2" data-price="89000">2 unidades<span class="qty-price">$89.000</span></div>
        </div>
      </div>

      <div class="field">
        <label for="nombre">Nombre completo</label>
        <input id="nombre" type="text" placeholder="Ej: María Gómez">
      </div>
      <div class="field">
        <label for="telefono">WhatsApp / Celular</label>
        <input id="telefono" type="tel" placeholder="Ej: 300 123 4567">
      </div>
      <div class="field">
        <label for="ciudad">Ciudad</label>
        <input id="ciudad" type="text" placeholder="Ej: Bogotá">
      </div>
      <div class="field">
        <label for="direccion">Dirección de entrega</label>
        <input id="direccion" type="text" placeholder="Barrio, calle, número">
      </div>

      <div class="order-summary">
        <span>Total a pagar contra entrega</span>
        <span id="total-price">$49.000</span>
      </div>

      <button class="cta block" id="submit-order">Confirmar pedido por WhatsApp →</button>
      <p class="order-note">Al confirmar, se abrirá WhatsApp con tus datos ya escritos para que solo debas enviar el mensaje.</p>
    </div>
  </div>
</section>

<footer>
  <div class="wrap">
    <div>Lima Eléctrica Spa Pies™ · Distribución en Colombia</div>
    <div>Atención al cliente por WhatsApp · Lunes a sábado, 8am–7pm</div>
    <div style="opacity:0.6;">Este producto es de uso cosmético para el cuidado de la piel. No sustituye atención podológica o médica profesional.</div>
  </div>
</footer>

<a class="wa-float" id="wa-float" href="#" target="_blank" rel="noopener" aria-label="Escribir por WhatsApp">💬</a>

<div class="sticky-cta">
  <div class="p">$49.000 <small>Envío gratis · Pago contra entrega</small></div>
  <a href="#pedido" class="cta" style="padding:12px 18px;font-size:14px;">Pedir ahora</a>
</div>

<script>
  // ======= CONFIGURA AQUÍ TU NÚMERO DE WHATSAPP (con indicativo 57, sin +, sin espacios) =======
  const WHATSAPP_NUMBER = "573001234567"; // <-- reemplaza este número por el tuyo

  document.getElementById('wa-float').href = `https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent('Hola, tengo una pregunta sobre la Lima Eléctrica Spa Pies 🦶')}`;

  // Quantity selector
  const qtyOpts = document.querySelectorAll('.qty-opt');
  const totalPriceEl = document.getElementById('total-price');
  let selectedQty = { qty: 1, price: 49000 };
  qtyOpts.forEach(opt => {
    opt.addEventListener('click', () => {
      qtyOpts.forEach(o => o.classList.remove('active'));
      opt.classList.add('active');
      selectedQty = { qty: Number(opt.dataset.qty), price: Number(opt.dataset.price) };
      totalPriceEl.textContent = '$' + selectedQty.price.toLocaleString('es-CO');
    });
  });

  // FAQ accordion
  document.querySelectorAll('.faq-item').forEach(item => {
    const q = item.querySelector('.faq-q');
    const a = item.querySelector('.faq-a');
    q.addEventListener('click', () => {
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(i => {
        i.classList.remove('open');
        i.querySelector('.faq-a').style.maxHeight = null;
      });
      if (!isOpen) {
        item.classList.add('open');
        a.style.maxHeight = a.scrollHeight + 'px';
      }
    });
  });

  // Order form -> WhatsApp
  document.getElementById('submit-order').addEventListener('click', () => {
    const nombre = document.getElementById('nombre').value.trim();
    const telefono = document.getElementById('telefono').value.trim();
    const ciudad = document.getElementById('ciudad').value.trim();
    const direccion = document.getElementById('direccion').value.trim();

    if (!nombre || !telefono || !ciudad || !direccion) {
      alert('Por favor completa todos los campos antes de confirmar tu pedido.');
      return;
    }

    const mensaje = `¡Hola! Quiero pedir la Lima Eléctrica Spa Pies 🦶

` +
      `👤 Nombre: ${nombre}
` +
      `📱 Celular: ${telefono}
` +
      `🏙️ Ciudad: ${ciudad}
` +
      `📍 Dirección: ${direccion}
` +
      `📦 Cantidad: ${selectedQty.qty} unidad(es)
` +
      `💰 Total a pagar contra entrega: $${selectedQty.price.toLocaleString('es-CO')}`;

    window.open(`https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent(mensaje)}`, '_blank');
  });

  // Countdown timer resets at midnight local time — creates daily urgency
  function updateCountdown() {
    const now = new Date();
    const end = new Date(now);
    end.setHours(23, 59, 59, 999);
    const diff = Math.max(0, end - now);
    const h = String(Math.floor(diff / 3600000)).padStart(2, '0');
    const m = String(Math.floor((diff % 3600000) / 60000)).padStart(2, '0');
    const s = String(Math.floor((diff % 60000) / 1000)).padStart(2, '0');
    document.getElementById('cd-h').textContent = h;
    document.getElementById('cd-m').textContent = m;
    document.getElementById('cd-s').textContent = s;
  }
  updateCountdown();
  setInterval(updateCountdown, 1000);
</script>

</body>
</html>
