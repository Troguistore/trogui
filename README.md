<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TROGUI - Tienda Online Colombia 🇨🇴</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Poppins:wght@400;600;700;800;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;}
:root{
  --orange:#FF4500;
  --orange2:#FF6B00;
  --dark:#1a1a2e;
  --green:#00C853;
  --yellow:#FFB800;
  --white:#fff;
  --light:#f7f7f7;
  --gray:#6c757d;
  --shadow:0 2px 12px rgba(0,0,0,0.09);
}
body{font-family:'Nunito',sans-serif;background:#f5f5f5;color:#222;overflow-x:hidden;}
a{text-decoration:none;color:inherit;}

/* TOP BAR */
.topbar{background:var(--dark);color:#fff;text-align:center;padding:7px 15px;font-size:12.5px;font-weight:700;letter-spacing:.3px;}
.topbar span{margin:0 10px;}

/* HEADER */
header{background:#fff;box-shadow:0 2px 10px rgba(0,0,0,.1);position:sticky;top:0;z-index:900;}
.header-inner{display:flex;align-items:center;gap:12px;padding:10px 20px;flex-wrap:wrap;}
.logo-wrap{display:flex;align-items:center;gap:10px;cursor:pointer;}
.logo-wrap img{height:52px;width:auto;border-radius:8px;object-fit:contain;}
.logo-tagline{font-size:10px;color:var(--gray);font-weight:700;white-space:nowrap;}
.search-wrap{flex:1;min-width:200px;display:flex;border:2px solid var(--orange);border-radius:30px;overflow:hidden;height:44px;}
.search-wrap input{flex:1;border:none;outline:none;padding:0 16px;font-size:14px;font-family:'Nunito',sans-serif;}
.search-wrap button{background:var(--orange);color:#fff;border:none;padding:0 20px;font-size:18px;cursor:pointer;transition:.2s;}
.search-wrap button:hover{background:#cc3700;}
.header-actions{display:flex;align-items:center;gap:10px;flex-wrap:wrap;}
.btn-wa-header{background:#25D366;color:#fff;border:none;padding:9px 16px;border-radius:25px;font-weight:800;font-size:13px;cursor:pointer;display:flex;align-items:center;gap:7px;white-space:nowrap;}
.btn-cart{background:var(--orange);color:#fff;border:none;padding:9px 16px;border-radius:25px;font-weight:800;font-size:13px;cursor:pointer;display:flex;align-items:center;gap:7px;position:relative;white-space:nowrap;}
.cart-badge{background:var(--yellow);color:#000;border-radius:50%;width:20px;height:20px;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:900;}
.socials{display:flex;gap:8px;}
.soc-btn{width:34px;height:34px;border-radius:50%;border:none;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:900;color:#fff;transition:.2s;}
.soc-btn:hover{transform:scale(1.1);}
.soc-ig{background:radial-gradient(circle at 30% 107%,#fdf497 0%,#fd5949 45%,#d6249f 60%,#285AEB 90%);}
.soc-tt{background:#010101;}
.soc-wa{background:#25D366;}

/* TRUST BAR */
.trust-bar{background:#fff;border-top:1px solid #eee;display:flex;justify-content:center;align-items:center;gap:20px;padding:9px 20px;flex-wrap:wrap;}
.trust-item{display:flex;align-items:center;gap:7px;font-size:12.5px;font-weight:800;color:#333;white-space:nowrap;}
.trust-icon{font-size:18px;}

/* HERO SLIDER */
.hero{position:relative;overflow:hidden;height:280px;}
.slides-container{display:flex;width:300%;height:100%;transition:transform .7s ease;}
.slide{flex:0 0 33.333%;height:100%;display:flex;align-items:center;justify-content:center;flex-direction:column;text-align:center;padding:20px;color:#fff;position:relative;overflow:hidden;}
.slide1{background:linear-gradient(135deg,#FF4500,#FF6B00);}
.slide2{background:linear-gradient(135deg,#1a1a2e,#16213e);}
.slide3{background:linear-gradient(135deg,#00C853,#007735);}
.slide h2{font-family:'Poppins',sans-serif;font-size:clamp(22px,5vw,36px);font-weight:900;text-shadow:1px 2px 6px rgba(0,0,0,.3);margin-bottom:8px;}
.slide p{font-size:clamp(13px,3vw,17px);font-weight:600;margin-bottom:15px;opacity:.95;}
.slide-btn{background:#fff;border:none;border-radius:25px;padding:11px 28px;font-weight:900;font-size:14px;cursor:pointer;font-family:'Poppins',sans-serif;transition:.2s;}
.slide1 .slide-btn{color:var(--orange);}
.slide2 .slide-btn{color:#1a1a2e;}
.slide3 .slide-btn{color:#007735;}
.slide-btn:hover{transform:scale(1.06);box-shadow:0 5px 20px rgba(0,0,0,.25);}
.slider-dots{position:absolute;bottom:13px;left:50%;transform:translateX(-50%);display:flex;gap:7px;z-index:10;}
.sdot{width:10px;height:10px;border-radius:5px;background:rgba(255,255,255,.5);cursor:pointer;transition:.3s;}
.sdot.on{width:26px;background:#fff;}
.hero-arrow{position:absolute;top:50%;transform:translateY(-50%);background:rgba(255,255,255,.25);border:none;color:#fff;width:38px;height:38px;border-radius:50%;font-size:18px;cursor:pointer;z-index:10;display:flex;align-items:center;justify-content:center;}
.hero-arrow.left{left:10px;}
.hero-arrow.right{right:10px;}

/* SCROLL MARQUEE */
.marquee-bar{background:var(--dark);color:#fff;padding:9px 0;overflow:hidden;white-space:nowrap;}
.marquee-inner{display:inline-block;animation:marquee 28s linear infinite;font-weight:700;font-size:13px;}
@keyframes marquee{from{transform:translateX(100vw)}to{transform:translateX(-100%)}}

/* SECTION */
.section{padding:18px 16px;max-width:1200px;margin:0 auto;}
.sec-title{font-family:'Poppins',sans-serif;font-size:20px;font-weight:800;color:var(--dark);margin-bottom:14px;display:flex;align-items:center;gap:8px;}
.sec-title span{color:var(--orange);}
.sec-line{flex:1;height:2px;background:linear-gradient(to right,var(--orange),transparent);margin-left:8px;}

/* PRODUCT GRID */
.prod-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(175px,1fr));gap:14px;}

/* PRODUCT CARD */
.prod-card{background:#fff;border-radius:14px;overflow:hidden;box-shadow:var(--shadow);cursor:pointer;transition:all .25s;position:relative;display:flex;flex-direction:column;}
.prod-card:hover{transform:translateY(-5px);box-shadow:0 10px 28px rgba(0,0,0,.14);}
.card-badges{position:absolute;top:8px;left:8px;display:flex;flex-direction:column;gap:4px;z-index:5;}
.cbadge{padding:3px 9px;border-radius:14px;font-size:10.5px;font-weight:900;display:inline-block;}
.cbadge.red{background:var(--orange);color:#fff;}
.cbadge.green{background:var(--green);color:#fff;}
.cbadge.yellow{background:var(--yellow);color:#000;}
.prod-img-wrap{width:100%;height:175px;overflow:hidden;background:#f0f0f0;display:flex;align-items:center;justify-content:center;position:relative;}
.prod-img-wrap img{width:100%;height:100%;object-fit:cover;transition:.3s;}
.prod-card:hover .prod-img-wrap img{transform:scale(1.05);}
.prod-emoji{font-size:65px;user-select:none;}
.prod-body{padding:11px 12px;flex:1;display:flex;flex-direction:column;gap:4px;}
.prod-id{font-size:9.5px;color:#bbb;}
.prod-name{font-weight:800;font-size:13.5px;color:#222;line-height:1.3;}
.stars{color:var(--yellow);font-size:12.5px;}
.sold{font-size:11px;color:#999;}
.viewers{display:flex;align-items:center;gap:4px;font-size:11px;font-weight:700;color:#e65100;background:#fff3e0;padding:3px 8px;border-radius:12px;border:1px solid var(--yellow);width:fit-content;}
.price-old{text-decoration:line-through;color:#aaa;font-size:12.5px;}
.price-new{color:var(--orange);font-size:22px;font-weight:900;font-family:'Poppins',sans-serif;line-height:1.1;}
.shipping-badge{color:var(--green);font-size:11px;font-weight:800;}
.units{color:var(--orange);font-size:11px;font-weight:700;}
.timer-chip{background:#fff3e0;border:1px solid var(--yellow);border-radius:8px;padding:4px 8px;font-size:11px;font-weight:800;color:#bf360c;display:flex;align-items:center;gap:4px;animation:blink .9s infinite;}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.65}}
.btn-comprar{width:100%;background:var(--orange);color:#fff;border:none;padding:10px;border-radius:9px;font-weight:900;font-size:14px;cursor:pointer;margin-top:auto;font-family:'Nunito',sans-serif;transition:.2s;}
.btn-comprar:hover{background:#cc3700;}

/* FLOATING PURCHASE ALERT */
.purchase-alert{position:fixed;bottom:85px;left:16px;background:#fff;border-radius:14px;padding:11px 15px;box-shadow:0 4px 20px rgba(0,0,0,.2);font-size:12.5px;z-index:998;max-width:230px;border-left:4px solid var(--green);animation:slideup .5s ease;display:none;}
@keyframes slideup{from{transform:translateY(20px);opacity:0}to{transform:translateY(0);opacity:1}}
.purchase-alert strong{display:block;color:#222;font-weight:800;}
.purchase-alert span{color:#555;}

/* FLOATING WA */
.float-wa{position:fixed;bottom:20px;right:18px;background:#25D366;color:#fff;width:56px;height:56px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:26px;box-shadow:0 4px 18px rgba(37,211,102,.45);z-index:999;text-decoration:none;animation:bounce 2s infinite;}
@keyframes bounce{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}

/* ADMIN BUTTONS */
.admin-area{position:fixed;bottom:20px;left:18px;display:flex;gap:8px;z-index:1200;}
.admin-btn{width:30px;height:30px;border-radius:50%;border:1.5px solid #ccc;background:#fff;font-size:12px;font-weight:900;cursor:pointer;color:#bbb;display:flex;align-items:center;justify-content:center;transition:.2s;}
.admin-btn:hover{border-color:#555;color:#555;}

/* MODALS */
.overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,.72);z-index:2000;overflow-y:auto;padding:16px;}
.overlay.show{display:flex;align-items:flex-start;justify-content:center;}
.modal{background:#fff;border-radius:20px;padding:26px;max-width:520px;width:100%;margin:auto;position:relative;}
.modal-x{position:absolute;top:14px;right:14px;background:none;border:none;font-size:22px;cursor:pointer;color:#888;line-height:1;}

/* PRODUCT DETAIL */
.detail-imgs{display:grid;grid-template-columns:1fr 1fr;gap:6px;margin-bottom:14px;}
.detail-img{width:100%;height:145px;border-radius:10px;overflow:hidden;background:#f0f0f0;display:flex;align-items:center;justify-content:center;font-size:48px;}
.detail-img img{width:100%;height:100%;object-fit:cover;}

/* ORDER FORM */
.form-h{font-family:'Poppins',sans-serif;font-size:19px;font-weight:800;margin-bottom:4px;color:var(--dark);}
.form-sub{font-size:12.5px;color:#888;margin-bottom:18px;}
.fgrp{margin-bottom:14px;}
.flabel{display:block;font-weight:800;font-size:13.5px;margin-bottom:5px;color:#333;}
.finput{width:100%;border:2px solid #e5e5e5;border-radius:10px;padding:11px 14px;font-size:14px;font-family:'Nunito',sans-serif;outline:none;transition:.2s;}
.finput:focus{border-color:var(--orange);}
.fhint{font-size:11px;color:#999;margin-top:3px;}
.order-sum{background:#fff8f5;border:1.5px solid #ffd0b5;border-radius:12px;padding:14px;margin-bottom:14px;}
.os-name{font-weight:800;font-size:15px;color:#222;margin-bottom:4px;}
.os-id{font-size:11px;color:#bbb;margin-bottom:7px;}
.os-row{display:flex;align-items:baseline;gap:10px;}
.os-old{text-decoration:line-through;color:#bbb;font-size:13px;}
.os-new{color:var(--orange);font-size:26px;font-weight:900;font-family:'Poppins',sans-serif;}
.os-save{color:var(--green);font-size:12.5px;font-weight:800;}
.delivery-est{background:#e8f5e9;border-radius:10px;padding:10px 14px;font-size:13px;font-weight:800;color:#1b5e20;margin-bottom:14px;display:flex;align-items:center;gap:7px;}
.btn-confirm{width:100%;background:var(--green);color:#fff;border:none;padding:15px;border-radius:12px;font-weight:900;font-size:16px;cursor:pointer;font-family:'Poppins',sans-serif;transition:.2s;}
.btn-confirm:hover{background:#009624;transform:scale(1.02);}
.cod-badge{display:flex;align-items:center;gap:8px;background:#f0f7ff;border-radius:10px;padding:10px 14px;margin-bottom:14px;font-size:13px;font-weight:700;color:#0d47a1;}

/* ADMIN PANEL */
.admin-panel{display:none;position:fixed;inset:0;background:rgba(0,0,0,.85);z-index:3000;overflow-y:auto;padding:16px;}
.admin-panel.show{display:flex;align-items:flex-start;justify-content:center;}
.abox{background:#fff;border-radius:20px;padding:26px;max-width:700px;width:100%;margin:auto;max-height:92vh;overflow-y:auto;}
.abox h2{font-family:'Poppins',sans-serif;font-size:20px;font-weight:800;margin-bottom:16px;display:flex;justify-content:space-between;align-items:center;}
.tabs{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:18px;}
.tab{padding:7px 16px;border-radius:20px;border:2px solid #ddd;background:#fff;font-weight:700;font-size:13px;cursor:pointer;transition:.2s;}
.tab.on{background:var(--orange);color:#fff;border-color:var(--orange);}
.tcontent{display:none;}
.tcontent.on{display:block;}
.edit-card{border:1.5px solid #eee;border-radius:12px;padding:14px;margin-bottom:10px;display:flex;align-items:center;gap:12px;}
.edit-emoji{font-size:28px;}
.edit-info{flex:1;}
.edit-name{font-weight:800;font-size:14px;}
.edit-price{color:var(--orange);font-weight:800;font-size:13px;}
.btn-edit{background:var(--orange);color:#fff;border:none;padding:7px 14px;border-radius:8px;cursor:pointer;font-weight:700;font-size:12.5px;}
.orders-list{display:flex;flex-direction:column;gap:10px;max-height:50vh;overflow-y:auto;}
.order-row{background:#f9f9f9;border-radius:10px;padding:12px;font-size:13px;}
.order-row strong{display:block;font-size:14px;margin-bottom:4px;color:var(--dark);}
.clients-count{font-size:40px;font-weight:900;color:var(--orange);font-family:'Poppins',sans-serif;margin:10px 0;}

/* PAGE SETTINGS (E panel) */
.page-setting-row{display:flex;align-items:center;gap:12px;margin-bottom:12px;padding-bottom:12px;border-bottom:1px solid #eee;}
.page-setting-label{font-weight:700;font-size:13.5px;width:150px;flex-shrink:0;}
.page-setting-input{flex:1;border:1.5px solid #ddd;border-radius:8px;padding:8px 12px;font-size:13px;font-family:'Nunito',sans-serif;outline:none;}
.page-setting-input:focus{border-color:var(--orange);}
.btn-save-page{background:var(--orange);color:#fff;border:none;padding:10px 24px;border-radius:10px;font-weight:800;cursor:pointer;font-size:14px;margin-top:10px;}
.upload-btn{background:#f0f0f0;border:2px dashed #ccc;border-radius:10px;padding:12px 16px;cursor:pointer;text-align:center;font-size:13px;color:#666;font-weight:700;display:block;width:100%;}
.upload-btn:hover{border-color:var(--orange);color:var(--orange);}

/* REVIEWS */
.reviews-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:12px;margin-top:10px;}
.review-card{background:#fff;border-radius:12px;padding:14px;box-shadow:var(--shadow);}
.reviewer{display:flex;align-items:center;gap:10px;margin-bottom:8px;}
.rev-avatar{width:38px;height:38px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-weight:900;font-size:15px;color:#fff;flex-shrink:0;}
.rev-name{font-weight:800;font-size:13.5px;}
.rev-loc{font-size:11px;color:#999;}
.rev-stars{color:var(--yellow);font-size:13px;margin-bottom:6px;}
.rev-text{font-size:13px;color:#444;line-height:1.5;}
.rev-img{width:100%;height:100px;border-radius:8px;object-fit:cover;margin-top:8px;}

/* FOOTER */
footer{background:var(--dark);color:#fff;padding:30px 20px 20px;margin-top:20px;}
.footer-inner{max-width:1200px;margin:0 auto;display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:20px;}
.footer-col h4{font-family:'Poppins',sans-serif;font-size:15px;font-weight:800;margin-bottom:12px;color:var(--yellow);}
.footer-col p,.footer-col a{font-size:13px;color:rgba(255,255,255,.75);line-height:1.8;display:block;}
.footer-col a:hover{color:var(--yellow);}
.footer-bottom{text-align:center;margin-top:20px;padding-top:16px;border-top:1px solid rgba(255,255,255,.1);font-size:12px;color:rgba(255,255,255,.45);}

/* RESPONSIVE */
@media(max-width:600px){
.header-inner{gap:8px;}
.hero{height:220px;}
.slide h2{font-size:20px;}
.prod-grid{grid-template-columns:repeat(2,1fr);gap:10px;}
.trust-bar{gap:10px;}
.trust-item{font-size:11px;}
}
@media(max-width:380px){
.prod-grid{grid-template-columns:repeat(2,1fr);}
}

/* SEARCH SUGGESTIONS */
.suggestions{position:absolute;top:100%;left:0;right:0;background:#fff;border-radius:0 0 14px 14px;box-shadow:0 6px 20px rgba(0,0,0,.12);z-index:100;max-height:280px;overflow-y:auto;}
.sugg-item{padding:10px 16px;cursor:pointer;font-size:14px;border-bottom:1px solid #f0f0f0;display:flex;align-items:center;gap:10px;}
.sugg-item:hover{background:#fff3f0;color:var(--orange);}
.search-container{position:relative;flex:1;min-width:200px;}

/* TOAST */
.toast{position:fixed;top:80px;right:16px;background:#1a1a2e;color:#fff;padding:12px 20px;border-radius:12px;font-size:13.5px;font-weight:700;z-index:9999;animation:fadetoast .3s ease;display:none;}
.toast.show{display:block;}
@keyframes fadetoast{from{opacity:0;transform:translateY(-10px)}to{opacity:1;transform:translateY(0)}}

/* EDIT PRODUCT MODAL */
.ep-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
@media(max-width:480px){.ep-grid{grid-template-columns:1fr;}}

/* AUDIO BUTTON */
.audio-banner{background:linear-gradient(135deg,var(--orange),var(--orange2));color:#fff;text-align:center;padding:8px;font-size:13px;font-weight:700;cursor:pointer;display:flex;align-items:center;justify-content:center;gap:8px;}
</style>
</head>
<body>

<!-- TOP BAR -->
<div class="topbar">🇨🇴 Envío GRATIS a toda Colombia &nbsp;|&nbsp; 🚚 Interrapidísimo · Coordinadora · Enviá &nbsp;|&nbsp; 💳 Pago Contra Entrega</div>

<!-- HEADER -->
<header>
  <div class="header-inner">
    <div class="logo-wrap" onclick="document.getElementById('top').scrollIntoView({behavior:'smooth'})">
      <img id="logo-img" src="LOGO_PLACEHOLDER" alt="TROGUI">
    </div>
    <div class="search-container">
      <div class="search-wrap">
        <input type="text" id="search-input" placeholder="Buscar productos..." autocomplete="off" oninput="handleSearch(this.value)" onkeydown="if(event.key==='Enter')doSearch()">
        <button onclick="doSearch()">🔍</button>
      </div>
      <div class="suggestions" id="suggestions" style="display:none;"></div>
    </div>
    <div class="header-actions">
      <a href="https://wa.link/lhneng" target="_blank" class="btn-wa-header">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
        3206572598
      </a>
      <button class="btn-cart" onclick="openCart()">
        🛒 Carrito <span class="cart-badge" id="cart-count">0</span>
      </button>
      <div class="socials">
        <a href="https://www.instagram.com/store_trog" target="_blank" class="soc-btn soc-ig">📷</a>
        <a href="https://www.tiktok.com/@trogui_store" target="_blank" class="soc-btn soc-tt">♪</a>
        <a href="https://wa.link/lhneng" target="_blank" class="soc-btn soc-wa">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
        </a>
      </div>
    </div>
  </div>
  <!-- TRUST BAR -->
  <div class="trust-bar">
    <div class="trust-item"><span class="trust-icon">🚚</span> Envío GRATIS a toda Colombia</div>
    <div class="trust-item"><span class="trust-icon">💵</span> Pago Contra Entrega</div>
    <div class="trust-item"><span class="trust-icon">🔒</span> Compra Segura</div>
    <div class="trust-item"><span class="trust-icon">📦</span> 3 a 7 días hábiles</div>
    <div class="trust-item"><span class="trust-icon">⭐</span> +500 clientes satisfechos</div>
  </div>
</header>

<!-- MARQUEE -->
<div class="marquee-bar">
  <span class="marquee-inner">🔥 OFERTA ESPECIAL — Envío GRATIS a toda Colombia &nbsp;•&nbsp; 💳 Pago Contra Entrega disponible &nbsp;•&nbsp; 🚀 Despacho por Interrapidísimo, Coordinadora y Enviá &nbsp;•&nbsp; ⭐ Productos de calidad garantizados &nbsp;•&nbsp; 📦 3 a 7 días hábiles &nbsp;•&nbsp; 🇨🇴 100% colombiano &nbsp;•&nbsp;</span>
</div>

<!-- HERO SLIDER -->
<div class="hero" id="top">
  <div class="slides-container" id="slides-container">
    <div class="slide slide1">
      <h2>🔥 Ofertas Increíbles</h2>
      <p>Productos de calidad con envío GRATIS a toda Colombia</p>
      <button class="slide-btn" onclick="document.getElementById('productos').scrollIntoView({behavior:'smooth'})">Ver Ofertas →</button>
    </div>
    <div class="slide slide2">
      <h2>💳 Pago Contra Entrega</h2>
      <p>Recibe tu pedido y paga cuando llegue a tu puerta</p>
      <button class="slide-btn" onclick="document.getElementById('productos').scrollIntoView({behavior:'smooth'})">Comprar Ahora →</button>
    </div>
    <div class="slide slide3">
      <h2>📦 Envío Rápido</h2>
      <p>Despachamos por Interrapidísimo, Coordinadora y Enviá</p>
      <button class="slide-btn" onclick="document.getElementById('productos').scrollIntoView({behavior:'smooth'})">Ver Productos →</button>
    </div>
  </div>
  <button class="hero-arrow left" onclick="changeSlide(-1)">‹</button>
  <button class="hero-arrow right" onclick="changeSlide(1)">›</button>
  <div class="slider-dots" id="slider-dots"></div>
</div>

<!-- PRODUCTOS -->
<div class="section" id="productos">
  <div class="sec-title"><span>🔥</span> Productos en Oferta <div class="sec-line"></div></div>
  <div class="prod-grid" id="prod-grid"></div>
</div>

<!-- RESEÑAS -->
<div class="section">
  <div class="sec-title"><span>⭐</span> Lo que dicen nuestros clientes <div class="sec-line"></div></div>
  <div class="reviews-grid" id="reviews-grid"></div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-col">
      <h4>TROGUI Store</h4>
      <p>Tienda colombiana con los mejores productos al mejor precio.</p>
      <p style="margin-top:10px;">📞 WhatsApp: <a href="https://wa.link/lhneng" target="_blank">3206572598</a></p>
    </div>
    <div class="footer-col">
      <h4>Envíos</h4>
      <p>🚚 Interrapidísimo</p>
      <p>🚚 Coordinadora</p>
      <p>🚚 Enviá</p>
      <p>📦 3 a 7 días hábiles</p>
    </div>
    <div class="footer-col">
      <h4>Métodos de Pago</h4>
      <p>💵 Pago Contra Entrega</p>
      <p>🏦 Transferencia bancaria</p>
      <p>📱 Nequi / Daviplata</p>
    </div>
    <div class="footer-col">
      <h4>Síguenos</h4>
      <a href="https://www.instagram.com/store_trog" target="_blank">📷 Instagram</a>
      <a href="https://www.tiktok.com/@trogui_store" target="_blank">♪ TikTok</a>
      <a href="https://wa.link/lhneng" target="_blank">💬 WhatsApp</a>
    </div>
  </div>
  <div class="footer-bottom">© 2025 TROGUI Store — Todos los derechos reservados 🇨🇴</div>
</footer>

<!-- FLOATING WA -->
<a href="https://wa.link/lhneng" target="_blank" class="float-wa">
  <svg width="26" height="26" viewBox="0 0 24 24" fill="white"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
</a>

<!-- PURCHASE ALERT -->
<div class="purchase-alert" id="purchase-alert">
  <strong id="alert-name">Juan Camilo Paz</strong>
  <span id="alert-msg">acaba de pedir para Medellín 🎉</span>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<!-- ADMIN BUTTONS -->
<div class="admin-area">
  <button class="admin-btn" id="btn-r" title="Editor de productos" onclick="askAdminPass('r')">R</button>
  <button class="admin-btn" id="btn-c" title="Ver pedidos y clientes" onclick="askAdminPass('c')">C</button>
  <button class="admin-btn" id="btn-e" title="Editar página" onclick="askAdminPass('e')">E</button>
</div>

<!-- ===== OVERLAYS ===== -->

<!-- PRODUCT DETAIL -->
<div class="overlay" id="overlay-detail">
  <div class="modal">
    <button class="modal-x" onclick="closeOverlay('overlay-detail')">✕</button>
    <div id="detail-content"></div>
  </div>
</div>

<!-- ORDER FORM -->
<div class="overlay" id="overlay-order">
  <div class="modal">
    <button class="modal-x" onclick="closeOverlay('overlay-order')">✕</button>
    <div class="form-h">📦 Completar Pedido</div>
    <div class="form-sub">Llena todos los campos para confirmar tu compra</div>
    <div class="order-sum" id="order-summary"></div>
    <div class="delivery-est" id="delivery-est">📅 Estimado de entrega calculando...</div>
    <div class="cod-badge">💳 <span>Pago Contra Entrega — Pagas cuando recibes</span></div>
    <div class="fgrp">
      <label class="flabel">Nombre *</label>
      <input class="finput" id="f-nombre" placeholder="Escribe tu nombre" type="text">
      <div class="fhint">Tu nombre completo</div>
    </div>
    <div class="fgrp">
      <label class="flabel">Apellido *</label>
      <input class="finput" id="f-apellido" placeholder="Escribe tu apellido" type="text">
    </div>
    <div class="fgrp">
      <label class="flabel">Ciudad o Municipio *</label>
      <input class="finput" id="f-ciudad" placeholder="Ej: Bogotá, Medellín, Cali..." type="text">
    </div>
    <div class="fgrp">
      <label class="flabel">Dirección *</label>
      <input class="finput" id="f-direccion" placeholder="Tu dirección exacta" type="text">
      <div class="fhint">Entregamos directamente en casa o puedes recoger en oficina de Interrapidísimo</div>
    </div>
    <div class="fgrp">
      <label class="flabel">Teléfono *</label>
      <input class="finput" id="f-telefono" placeholder="Ej: 3001234567" type="tel">
    </div>
    <div class="fgrp">
      <label class="flabel">Nota adicional (opcional)</label>
      <input class="finput" id="f-nota" placeholder="Instrucciones especiales, apartamento, etc." type="text">
    </div>
    <button class="btn-confirm" onclick="confirmOrder()">✅ Confirmar Pedido por WhatsApp</button>
  </div>
</div>

<!-- EDIT PRODUCT MODAL -->
<div class="overlay" id="overlay-edit-prod">
  <div class="modal">
    <button class="modal-x" onclick="closeOverlay('overlay-edit-prod')">✕</button>
    <div class="form-h">✏️ Editar Producto</div>
    <div class="fgrp"><label class="flabel">Nombre</label><input class="finput" id="ep-name"></div>
    <div class="fgrp"><label class="flabel">Emoji / Ícono</label><input class="finput" id="ep-emoji" placeholder="🎁"></div>
    <div class="fgrp"><label class="flabel">Precio proveedor (COP)</label><input class="finput" id="ep-cost" type="number"></div>
    <div class="fgrp"><label class="flabel">Precio venta (COP)</label><input class="finput" id="ep-price" type="number"></div>
    <div class="fgrp"><label class="flabel">Precio tachado / antes (COP)</label><input class="finput" id="ep-old" type="number"></div>
    <div class="fgrp"><label class="flabel">Unidades vendidas</label><input class="finput" id="ep-sold" type="number"></div>
    <div class="fgrp"><label class="flabel">Estrellas (1-5)</label><input class="finput" id="ep-stars" type="number" min="1" max="5"></div>
    <div class="fgrp"><label class="flabel">Timer (minutos, 0=desactivado)</label><input class="finput" id="ep-timer" type="number" placeholder="120"></div>
    <div class="fgrp"><label class="flabel">Unidades restantes</label><input class="finput" id="ep-units" type="number"></div>
    <div class="fgrp"><label class="flabel">Descripción corta</label><input class="finput" id="ep-desc"></div>
    <div class="fgrp">
      <label class="flabel">Imagen (URL o subir)</label>
      <input class="finput" id="ep-img-url" placeholder="https://... o deja vacío para emoji">
      <label class="upload-btn" style="margin-top:8px;">
        📁 Subir imagen desde dispositivo
        <input type="file" accept="image/*,video/*" style="display:none" onchange="handleProductImgUpload(event)">
      </label>
      <img id="ep-img-preview" src="" alt="" style="width:100%;height:100px;object-fit:cover;border-radius:8px;margin-top:8px;display:none;">
    </div>
    <button class="btn-confirm" onclick="saveProductEdit()">💾 Guardar Cambios</button>
  </div>
</div>

<!-- ADMIN R PANEL -->
<div class="admin-panel" id="panel-r">
  <div class="abox">
    <h2>🛍️ Editor de Productos <button onclick="closeAdmin('panel-r')" style="background:none;border:none;font-size:22px;cursor:pointer;">✕</button></h2>
    <div id="edit-list"></div>
    <div style="margin-top:20px;padding-top:16px;border-top:1px solid #eee;">
      <button class="btn-confirm" onclick="addNewProduct()" style="background:var(--orange);margin-bottom:10px;">➕ Agregar Nuevo Producto</button>
    </div>
  </div>
</div>

<!-- ADMIN C PANEL -->
<div class="admin-panel" id="panel-c">
  <div class="abox">
    <h2>📊 Clientes y Pedidos <button onclick="closeAdmin('panel-c')" style="background:none;border:none;font-size:22px;cursor:pointer;">✕</button></h2>
    <div style="margin-bottom:16px;">
      <div style="font-size:14px;color:#666;margin-bottom:6px;font-weight:700;">Visitantes de hoy</div>
      <div class="clients-count" id="visitors-count">247</div>
      <div style="font-size:13px;color:#888;">personas han visitado la tienda hoy</div>
    </div>
    <div style="font-weight:800;font-size:15px;margin-bottom:10px;">📋 Pedidos recibidos:</div>
    <div class="orders-list" id="orders-list">
      <div style="color:#999;font-size:14px;text-align:center;padding:20px;">Aún no hay pedidos registrados</div>
    </div>
  </div>
</div>

<!-- ADMIN E PANEL -->
<div class="admin-panel" id="panel-e">
  <div class="abox">
    <h2>🎨 Editor de Página <button onclick="closeAdmin('panel-e')" style="background:none;border:none;font-size:22px;cursor:pointer;">✕</button></h2>
    <div class="tabs">
      <button class="tab on" onclick="switchTab(this,'etab-general')">General</button>
      <button class="tab" onclick="switchTab(this,'etab-redes')">Redes</button>
      <button class="tab" onclick="switchTab(this,'etab-banners')">Banners</button>
      <button class="tab" onclick="switchTab(this,'etab-resenas')">Reseñas</button>
      <button class="tab" onclick="switchTab(this,'etab-audio')">Audio</button>
    </div>

    <!-- General -->
    <div class="tcontent on" id="etab-general">
      <div class="page-setting-row">
        <span class="page-setting-label">Logo de la tienda</span>
        <label class="upload-btn" style="flex:1;font-size:12px;">
          📷 Cambiar logo
          <input type="file" accept="image/*" style="display:none" onchange="changeLogoFile(event)">
        </label>
      </div>
      <div class="page-setting-row">
        <span class="page-setting-label">Nombre tienda</span>
        <input class="page-setting-input" id="cfg-nombre" value="TROGUI Store">
      </div>
      <div class="page-setting-row">
        <span class="page-setting-label">Color principal</span>
        <input type="color" value="#FF4500" onchange="document.documentElement.style.setProperty('--orange',this.value)" style="width:50px;height:36px;border:none;cursor:pointer;border-radius:8px;">
      </div>
      <div class="page-setting-row">
        <span class="page-setting-label">WhatsApp</span>
        <input class="page-setting-input" id="cfg-wa" value="3206572598">
      </div>
      <div class="page-setting-row">
        <span class="page-setting-label">Anuncio barra top</span>
        <input class="page-setting-input" id="cfg-topbar" value="🇨🇴 Envío GRATIS a toda Colombia">
      </div>
      <div class="page-setting-row">
        <span class="page-setting-label">Banner marquee</span>
        <input class="page-setting-input" id="cfg-marquee" value="🔥 OFERTA ESPECIAL — Envío GRATIS a toda Colombia">
      </div>
      <button class="btn-save-page" onclick="applyPageSettings()">💾 Guardar Configuración</button>
    </div>

    <!-- Redes -->
    <div class="tcontent" id="etab-redes">
      <div class="page-setting-row">
        <span class="page-setting-label">Link Instagram</span>
        <input class="page-setting-input" id="cfg-ig" value="https://www.instagram.com/store_trog">
      </div>
      <div class="page-setting-row">
        <span class="page-setting-label">Link TikTok</span>
        <input class="page-setting-input" id="cfg-tt" value="https://www.tiktok.com/@trogui_store">
      </div>
      <div class="page-setting-row">
        <span class="page-setting-label">Link WhatsApp</span>
        <input class="page-setting-input" id="cfg-walink" value="https://wa.link/lhneng">
      </div>
      <button class="btn-save-page" onclick="applyPageSettings()">💾 Guardar</button>
    </div>

    <!-- Banners -->
    <div class="tcontent" id="etab-banners">
      <p style="font-size:13px;color:#888;margin-bottom:14px;">Personaliza los 3 slides del banner principal</p>
      <div id="banner-editor"></div>
      <button class="btn-save-page" onclick="saveBanners()">💾 Guardar Banners</button>
    </div>

    <!-- Reseñas -->
    <div class="tcontent" id="etab-resenas">
      <div id="reviews-editor"></div>
      <button class="btn-confirm" onclick="addReview()" style="background:var(--orange);margin-bottom:10px;margin-top:10px;">➕ Agregar Reseña</button>
    </div>

    <!-- Audio -->
    <div class="tcontent" id="etab-audio">
      <p style="font-size:14px;margin-bottom:14px;">Sube un audio o video para que se reproduzca automáticamente cuando el cliente entra a la tienda.</p>
      <div class="fgrp">
        <label class="flabel">Subir audio/video</label>
        <label class="upload-btn">
          🎵 Seleccionar archivo (audio o video)
          <input type="file" accept="audio/*,video/*" style="display:none" onchange="handleAudioUpload(event)">
        </label>
      </div>
      <div class="fgrp">
        <label class="flabel">O pegar URL de audio/video</label>
        <input class="finput" id="audio-url" placeholder="https://...">
        <button class="btn-save-page" onclick="setAudioFromUrl()" style="margin-top:8px;">Aplicar</button>
      </div>
      <audio id="store-audio" style="display:none;" loop></audio>
      <div id="audio-status" style="font-size:13px;color:#888;margin-top:10px;"></div>
    </div>
  </div>
</div>

<!-- CART OVERLAY -->
<div class="overlay" id="overlay-cart">
  <div class="modal">
    <button class="modal-x" onclick="closeOverlay('overlay-cart')">✕</button>
    <div class="form-h">🛒 Mi Carrito</div>
    <div id="cart-items" style="margin:16px 0;max-height:50vh;overflow-y:auto;"></div>
    <div id="cart-total" style="font-size:18px;font-weight:900;color:var(--orange);margin-bottom:14px;"></div>
    <button class="btn-confirm" onclick="checkoutCart()">📦 Proceder al Pedido</button>
  </div>
</div>

<!-- PASSWORD MODAL -->
<div class="overlay" id="overlay-pass">
  <div class="modal" style="max-width:320px;">
    <button class="modal-x" onclick="closeOverlay('overlay-pass')">✕</button>
    <div class="form-h">🔒 Acceso Administrativo</div>
    <div class="fgrp" style="margin-top:16px;">
      <label class="flabel">Contraseña</label>
      <input class="finput" id="admin-pass-input" type="password" placeholder="Ingresa la contraseña" onkeydown="if(event.key==='Enter')checkPass()">
    </div>
    <button class="btn-confirm" onclick="checkPass()">Ingresar</button>
  </div>
</div>

<script>
// ======= DATA =======
const ADMIN_PASS = '4325';
let pendingPanel = null;
let cartItems = [];
let currentOrderProduct = null;
let editingProductId = null;
let editingProductImg = null;
let visitorsCount = Math.floor(Math.random()*200)+150;
let orders = JSON.parse(localStorage.getItem('trogui_orders')||'[]');

let products = JSON.parse(localStorage.getItem('trogui_products')||'null') || [
  {id:'TRG-001',name:'Quita Callos Profesional',emoji:'🦶',price:49000,oldPrice:89000,cost:15000,stars:5,sold:120,units:8,timer:120,desc:'Elimina callos duros en minutos. Resultado garantizado.',img:''},
  {id:'TRG-002',name:'Removedor de Manchas Ropa',emoji:'👕',price:54000,oldPrice:98000,cost:18000,stars:5,sold:300,units:5,timer:30,desc:'Quita manchas difíciles en cualquier tela sin dañar los colores.',img:''},
  {id:'TRG-003',name:'Plancha de Pelo Profesional',emoji:'💇',price:79000,oldPrice:149000,cost:35000,stars:4,sold:85,units:12,timer:60,desc:'Temperatura regulable, planchas perfectas en casa.',img:''},
  {id:'TRG-004',name:'Masajeador Eléctrico Cuello',emoji:'💆',price:89000,oldPrice:169000,cost:42000,stars:5,sold:210,units:6,timer:45,desc:'Alivia el dolor de cuello y espalda con calor y vibración.',img:''},
  {id:'TRG-005',name:'Organizador de Cables USB',emoji:'🔌',price:39000,oldPrice:79000,cost:12000,stars:4,sold:180,units:20,timer:0,desc:'Ordena todos tus cables de escritorio y bolso.',img:''},
  {id:'TRG-006',name:'Crema Anticelulitis Corporal',emoji:'🧴',price:59000,oldPrice:109000,cost:22000,stars:5,sold:95,units:9,timer:90,desc:'Reduce celulitis y reafirma la piel en 4 semanas.',img:''},
  {id:'TRG-007',name:'Desengrasante Multiusos Cocina',emoji:'🧹',price:44000,oldPrice:85000,cost:15000,stars:4,sold:260,units:15,timer:0,desc:'Limpia grasa acumulada en hornillas, freidoras y superficies.',img:''},
  {id:'TRG-008',name:'Cortaúñas Eléctrico Bebé',emoji:'👶',price:64000,oldPrice:120000,cost:28000,stars:5,sold:130,units:7,timer:30,desc:'Seguro para bebés y recién nacidos, suave y silencioso.',img:''},
  {id:'TRG-009',name:'Lámpara LED Escritorio USB',emoji:'💡',price:49000,oldPrice:95000,cost:18000,stars:4,sold:175,units:18,timer:60,desc:'3 modos de luz, cuello flexible, ideal para estudiar o trabajar.',img:''},
  {id:'TRG-010',name:'Rodillo Facial Anti-Arrugas',emoji:'🌸',price:54000,oldPrice:99000,cost:20000,stars:5,sold:320,units:4,timer:20,desc:'Reduce bolsas, ojeras y arrugas con uso diario.',img:''},
  {id:'TRG-011',name:'Mini Ventilador Portatil USB',emoji:'💨',price:44000,oldPrice:85000,cost:16000,stars:4,sold:88,units:22,timer:0,desc:'Compacto, silencioso, ideal para oficina y viajes.',img:''},
  {id:'TRG-012',name:'Peladora de Verduras Eléctrica',emoji:'🥕',price:69000,oldPrice:130000,cost:30000,stars:5,sold:145,units:10,timer:90,desc:'Pela papas, zanahorias y más en segundos.',img:''},
  {id:'TRG-013',name:'Esponja Mágica Limpieza',emoji:'🧽',price:35000,oldPrice:70000,cost:8000,stars:4,sold:400,units:30,timer:0,desc:'Elimina marcas difíciles en paredes, zapatos y muebles.',img:''},
  {id:'TRG-014',name:'Reloj Digital Deportivo',emoji:'⌚',price:84000,oldPrice:160000,cost:40000,stars:5,sold:67,units:11,timer:60,desc:'Resistente al agua, pasos, calorías y sueño.',img:''},
  {id:'TRG-015',name:'Set Manicure 10 Piezas',emoji:'💅',price:59000,oldPrice:110000,cost:22000,stars:5,sold:200,units:8,timer:45,desc:'Todo lo que necesitas para cuidar tus uñas en casa.',img:''},
  {id:'TRG-016',name:'Aspiradora Portátil de Carro',emoji:'🚗',price:94000,oldPrice:178000,cost:45000,stars:4,sold:73,units:14,timer:30,desc:'Potente, inalámbrica, perfecta para limpiar el carro.',img:''},
  {id:'TRG-017',name:'Humidificador Aromaterapia',emoji:'🌫️',price:74000,oldPrice:140000,cost:33000,stars:5,sold:112,units:9,timer:120,desc:'Difusor de esencias con luz LED de colores para el hogar.',img:''},
  {id:'TRG-018',name:'Pasta Blanqueadora Dientes',emoji:'🦷',price:49000,oldPrice:90000,cost:16000,stars:4,sold:285,units:25,timer:0,desc:'Blanquea y elimina manchas sin dañar el esmalte.',img:''},
  {id:'TRG-019',name:'Cargador Inalámbrico 15W',emoji:'⚡',price:64000,oldPrice:120000,cost:28000,stars:5,sold:95,units:16,timer:60,desc:'Compatible con todos los celulares con carga rápida.',img:''},
  {id:'TRG-020',name:'Colchoneta Yoga Antideslizante',emoji:'🧘',price:79000,oldPrice:145000,cost:35000,stars:4,sold:58,units:20,timer:0,desc:'6mm de grosor, correa incluida, lavable a máquina.',img:''},
  {id:'TRG-021',name:'Jabón Artesanal de Azufre',emoji:'🧼',price:35000,oldPrice:68000,cost:10000,stars:5,sold:340,units:35,timer:0,desc:'Limpia el acné, espinillas y manchas de forma natural.',img:''},
  {id:'TRG-022',name:'Pinzas Cejas Profesionales',emoji:'✨',price:39000,oldPrice:75000,cost:12000,stars:4,sold:190,units:28,timer:0,desc:'Acero inoxidable, agarre preciso para un depilado perfecto.',img:''},
  {id:'TRG-023',name:'Filtro Ducha Anti-Cloro',emoji:'🚿',price:54000,oldPrice:100000,cost:20000,stars:5,sold:125,units:13,timer:90,desc:'Protege tu cabello y piel del cloro del agua del grifo.',img:''},
  {id:'TRG-024',name:'Delineador Permanente Ojos',emoji:'👁️',price:44000,oldPrice:85000,cost:15000,stars:5,sold:270,units:18,timer:30,desc:'Dura todo el día, prueba de agua y muy fácil de aplicar.',img:''},
  {id:'TRG-025',name:'Bolsa Térmica Lonchera',emoji:'🎒',price:64000,oldPrice:120000,cost:27000,stars:4,sold:82,units:20,timer:0,desc:'Mantiene los alimentos fríos o calientes por 6 horas.',img:''},
  {id:'TRG-026',name:'Sellador de Bolsas Alimentos',emoji:'🔐',price:49000,oldPrice:95000,cost:18000,stars:5,sold:155,units:22,timer:60,desc:'Sella cualquier bolsa plástica al instante, mantiene frescos los alimentos.',img:''},
  {id:'TRG-027',name:'Colágeno Facial en Polvo',emoji:'✨',price:74000,oldPrice:140000,cost:32000,stars:5,sold:98,units:10,timer:45,desc:'Reafirma la piel y reduce arrugas con uso diario.',img:''},
  {id:'TRG-028',name:'Repelente Mosquitos Natural',emoji:'🦟',price:39000,oldPrice:75000,cost:12000,stars:4,sold:215,units:30,timer:0,desc:'Base de citronela, seguro para niños y mascotas.',img:''},
  {id:'TRG-029',name:'Kit Limpieza PC Teclado',emoji:'💻',price:44000,oldPrice:85000,cost:15000,stars:4,sold:78,units:25,timer:0,desc:'Aire comprimido, microfibras y gel limpiador incluidos.',img:''},
  {id:'TRG-030',name:'Termómetro Digital Infrarrojo',emoji:'🌡️',price:69000,oldPrice:130000,cost:30000,stars:5,sold:190,units:12,timer:30,desc:'Medición sin contacto en 1 segundo, preciso y seguro.',img:''},
  {id:'TRG-031',name:'Cepillo Eléctrico Facial',emoji:'🌀',price:84000,oldPrice:158000,cost:38000,stars:5,sold:65,units:8,timer:90,desc:'Exfolia y limpia profundo los poros. Piel radiante garantizada.',img:''},
  {id:'TRG-032',name:'Aceite Vitamina E Cabello',emoji:'💧',price:54000,oldPrice:99000,cost:20000,stars:4,sold:145,units:20,timer:0,desc:'Hidrata, brilla y repara el cabello dañado naturalmente.',img:''},
  {id:'TRG-033',name:'Banda Resistencia Ejercicio',emoji:'🏋️',price:49000,oldPrice:90000,cost:17000,stars:4,sold:102,units:18,timer:60,desc:'Set de 5 bandas con distintos niveles de resistencia.',img:''},
  {id:'TRG-034',name:'Crema Pies Agrietados',emoji:'🦶',price:44000,oldPrice:82000,cost:14000,stars:5,sold:310,units:22,timer:0,desc:'Renueva la piel de los pies en 7 días, con urea y aceite de coco.',img:''},
  {id:'TRG-035',name:'Corrector Postura Espalda',emoji:'🦺',price:79000,oldPrice:148000,cost:35000,stars:4,sold:55,units:15,timer:120,desc:'Mejora tu postura desde el primer uso. Talla ajustable.',img:''},
  {id:'TRG-036',name:'Guantes Silicona Cocina',emoji:'🧤',price:44000,oldPrice:84000,cost:15000,stars:5,sold:185,units:20,timer:0,desc:'Resistentes al calor hasta 230°C, antideslizantes.',img:''},
  {id:'TRG-037',name:'Pasta Limpiadora Multifuncional',emoji:'🫧',price:39000,oldPrice:75000,cost:12000,stars:4,sold:230,units:28,timer:0,desc:'Limpia zapatos, metales, llantas y superficies en gel.',img:''},
  {id:'TRG-038',name:'Suero Vitamina C Facial',emoji:'🍊',price:69000,oldPrice:130000,cost:28000,stars:5,sold:170,units:11,timer:45,desc:'Ilumina el rostro y reduce manchas en pocas semanas.',img:''},
  {id:'TRG-039',name:'Porta Celular Auto Magnético',emoji:'🚗',price:44000,oldPrice:85000,cost:15000,stars:4,sold:290,units:22,timer:0,desc:'Soporte magnético fuerte, compatible con todos los celulares.',img:''},
  {id:'TRG-040',name:'Tapete Baño Antideslizante',emoji:'🚿',price:54000,oldPrice:98000,cost:20000,stars:4,sold:90,units:16,timer:0,desc:'Ventosas potentes, lavable en máquina, varios diseños.',img:''},
  {id:'TRG-041',name:'Limpiador Ultrasónico Joyería',emoji:'💍',price:94000,oldPrice:175000,cost:45000,stars:5,sold:42,units:8,timer:90,desc:'Limpia anillos, cadenas y aretes en minutos con ultrasonido.',img:''},
  {id:'TRG-042',name:'Almohadilla Calor Cervical',emoji:'🔥',price:74000,oldPrice:140000,cost:33000,stars:5,sold:78,units:10,timer:60,desc:'Alivia dolores musculares con calor uniforme y ajustable.',img:''},
  {id:'TRG-043',name:'Espejo Con Luz LED Maquillaje',emoji:'🪞',price:89000,oldPrice:165000,cost:42000,stars:5,sold:63,units:7,timer:30,desc:'10 aumentos, luz regulable, perfecto para maquillarse.',img:''},
  {id:'TRG-044',name:'Cuchillo Cerámico Cocina',emoji:'🔪',price:59000,oldPrice:110000,cost:24000,stars:4,sold:105,units:15,timer:0,desc:'No oxida, no transfiere sabores, filo duradero.',img:''},
  {id:'TRG-045',name:'Plancha Ropa de Vapor',emoji:'👗',price:99000,oldPrice:189000,cost:50000,stars:5,sold:48,units:9,timer:120,desc:'Elimina arrugas y bacterias en segundos con vapor potente.',img:''},
];

let reviews = JSON.parse(localStorage.getItem('trogui_reviews')||'null') || [
  {name:'Valentina Torres',loc:'Bogotá',stars:5,text:'Me llegó súper rápido, en 4 días! El producto es exactamente como lo muestran. Súper recomendado 😍',color:'#FF4500',img:''},
  {name:'Juan Camilo Paz',loc:'Medellín',stars:5,text:'Hize el pago contra entrega y todo perfecto. La calidad es muy buena para el precio que tiene. Volveré a comprar!',color:'#1a1a2e',img:''},
  {name:'Luisa Fernanda Rios',loc:'Cali',stars:4,text:'Llegó bien empacado y en buen estado. El envio demoró 5 dias pero todo bien, me gusto mucho el producto.',color:'#00C853',img:''},
  {name:'Carlos Andres Gomez',loc:'Barranquilla',stars:5,text:'Excelente producto!! Lo recomiendo a todos. Muy buena calidad y el servicio al cliente es muy atento 👌',color:'#FFB800',img:''},
  {name:'Maria Jose Vargas',loc:'Bucaramanga',stars:5,text:'Al principio tenia dudas pero me arriesgué y no me arrepiento para nada. Lo mejor que he comprado online en mucho tiempo',color:'#9c27b0',img:''},
  {name:'Andres Felipe Morales',loc:'Pereira',stars:4,text:'Buena calidad, llego puntual. Solo que el empaque podria ser un poquito mejor pero el producto en si esta muy bien.',color:'#f44336',img:''},
];

let banners = [
  {h:'🔥 Ofertas Increíbles',p:'Productos de calidad con envío GRATIS a toda Colombia',btn:'Ver Ofertas →',color:'slide1'},
  {h:'💳 Pago Contra Entrega',p:'Recibe tu pedido y paga cuando llegue a tu puerta',btn:'Comprar Ahora →',color:'slide2'},
  {h:'📦 Envío Rápido',p:'Despachamos por Interrapidísimo, Coordinadora y Enviá',btn:'Ver Productos →',color:'slide3'},
];

// ======= LOGO =======
(function setLogo(){
  const saved = localStorage.getItem('trogui_logo');
  const el = document.getElementById('logo-img');
  if(saved) { el.src = saved; return; }
  // Use encoded logo from file
  el.src = 'data:image/jpeg;base64,LOGO_B64_HERE';
})();

// ======= SLIDER =======
let slideIdx = 0;
const slidesContainer = document.getElementById('slides-container');
const dotsContainer = document.getElementById('slider-dots');
const totalSlides = 3;

function buildDots(){
  dotsContainer.innerHTML='';
  for(let i=0;i<totalSlides;i++){
    const d=document.createElement('div');
    d.className='sdot'+(i===0?' on':'');
    d.onclick=()=>goSlide(i);
    dotsContainer.appendChild(d);
  }
}
function goSlide(i){
  slideIdx=i;
  slidesContainer.style.transform=`translateX(-${(100/totalSlides)*i}%)`;
  document.querySelectorAll('.sdot').forEach((d,j)=>d.classList.toggle('on',j===i));
}
function changeSlide(dir){
  goSlide((slideIdx+dir+totalSlides)%totalSlides);
}
buildDots();
setInterval(()=>changeSlide(1),6000);

// ======= RENDER PRODUCTS =======
function renderProducts(list){
  const grid = document.getElementById('prod-grid');
  if(!list) list = products;
  grid.innerHTML = list.map(p=>productCardHTML(p)).join('');
  startTimers();
}

function productCardHTML(p){
  const starsHtml = '⭐'.repeat(p.stars||5)+(p.stars<5?'☆'.repeat(5-p.stars):'');
  const timerHtml = p.timer>0 ? `<div class="timer-chip">⏰ Oferta termina en: <span class="timer-display" data-mins="${p.timer}" data-id="${p.id}">--:--</span></div>` : '';
  const imgHtml = p.img
    ? `<img src="${p.img}" alt="${p.name}" style="width:100%;height:175px;object-fit:cover;">`
    : `<div class="prod-emoji">${p.emoji||'📦'}</div>`;
  const savedAmt = (p.oldPrice - p.price).toLocaleString('es-CO');
  const viewersN = Math.floor(Math.random()*8)+2;
  return `<div class="prod-card" onclick="openDetail('${p.id}')">
    <div class="card-badges">
      <span class="cbadge red">OFERTA</span>
      ${p.sold>=200?'<span class="cbadge yellow">TOP VENTA</span>':''}
      ${p.units<=5?'<span class="cbadge green">ÚLTIMAS</span>':''}
    </div>
    <div class="prod-img-wrap">${imgHtml}</div>
    <div class="prod-body">
      <div class="prod-id"># ${p.id}</div>
      <div class="prod-name">${p.name}</div>
      <div class="stars">${starsHtml} <span style="font-size:11px;color:#888;">(${p.sold} reseñas)</span></div>
      <div class="sold">🔥 ${p.sold} vendidos</div>
      <div class="viewers">👁️ ${viewersN} personas viendo</div>
      <div class="price-old">Antes: $${p.oldPrice.toLocaleString('es-CO')}</div>
      <div class="price-new">$${p.price.toLocaleString('es-CO')}</div>
      <div class="shipping-badge">✅ Envío GRATIS a toda Colombia</div>
      ${p.units<=10?`<div class="units">⚠️ Solo quedan ${p.units} unidades!</div>`:''}
      ${timerHtml}
      <button class="btn-comprar" onclick="event.stopPropagation();buyNow('${p.id}')">🛒 Comprar Ahora</button>
    </div>
  </div>`;
}

// ======= TIMERS =======
let timerIntervals = {};
function startTimers(){
  Object.values(timerIntervals).forEach(clearInterval);
  timerIntervals = {};
  document.querySelectorAll('.timer-display').forEach(el=>{
    const id = el.dataset.id;
    const mins = parseInt(el.dataset.mins)||120;
    let secs = mins * 60;
    const key = `timer_end_${id}`;
    let endTime = parseInt(localStorage.getItem(key)||'0');
    if(!endTime || endTime < Date.now()){
      endTime = Date.now() + secs*1000;
      localStorage.setItem(key, endTime);
    }
    function update(){
      const remaining = Math.max(0, Math.floor((endTime - Date.now())/1000));
      if(remaining===0){ el.textContent='¡EXPIRÓ!'; return; }
      const h = Math.floor(remaining/3600);
      const m = Math.floor((remaining%3600)/60);
      const s = remaining%60;
      el.textContent = (h>0?h+'h ':'')+String(m).padStart(2,'0')+':'+String(s).padStart(2,'0');
    }
    update();
    timerIntervals[id] = setInterval(update,1000);
  });
}

// ======= SEARCH =======
function handleSearch(val){
  const suggestBox = document.getElementById('suggestions');
  if(!val.trim()){ suggestBox.style.display='none'; return; }
  const norm = val.toLowerCase().replace(/[aáàä]/g,'a').replace(/[eéèë]/g,'e').replace(/[iíìï]/g,'i').replace(/[oóòö]/g,'o').replace(/[uúùü]/g,'u');
  const matches = products.filter(p=>{
    const n = p.name.toLowerCase().replace(/[aáàä]/g,'a').replace(/[eéèë]/g,'e').replace(/[iíìï]/g,'i').replace(/[oóòö]/g,'o').replace(/[uúùü]/g,'u');
    return n.includes(norm) || p.id.toLowerCase().includes(norm);
  }).slice(0,6);
  if(!matches.length){ suggestBox.style.display='none'; return; }
  suggestBox.innerHTML = matches.map(p=>`<div class="sugg-item" onclick="buyNow('${p.id}')">${p.emoji||'📦'} ${p.name} — <strong style="color:var(--orange)">$${p.price.toLocaleString('es-CO')}</strong></div>`).join('');
  suggestBox.style.display='block';
}
function doSearch(){
  const val = document.getElementById('search-input').value.trim();
  document.getElementById('suggestions').style.display='none';
  if(!val){ renderProducts(products); return; }
  const norm = val.toLowerCase().replace(/[aáàä]/g,'a').replace(/[eéèë]/g,'e').replace(/[iíìï]/g,'i').replace(/[oóòö]/g,'o').replace(/[uúùü]/g,'u');
  const res = products.filter(p=>{
    const n=(p.name+' '+p.desc).toLowerCase().replace(/[aáàä]/g,'a').replace(/[eéèë]/g,'e').replace(/[iíìï]/g,'i').replace(/[oóòö]/g,'o').replace(/[uúùü]/g,'u');
    return n.includes(norm)||p.id.toLowerCase().includes(norm);
  });
  renderProducts(res);
  document.getElementById('productos').scrollIntoView({behavior:'smooth'});
}
document.addEventListener('click',e=>{ if(!e.target.closest('.search-container')) document.getElementById('suggestions').style.display='none'; });

// ======= PRODUCT DETAIL =======
function openDetail(id){
  const p = products.find(x=>x.id===id);
  if(!p) return;
  const starsHtml = '⭐'.repeat(p.stars||5)+(p.stars<5?'☆'.repeat(5-p.stars):'');
  const imgHtml = p.img ? `<img src="${p.img}" alt="${p.name}" style="width:100%;height:200px;object-fit:cover;border-radius:12px;margin-bottom:12px;">` : `<div style="font-size:80px;text-align:center;padding:20px;">${p.emoji||'📦'}</div>`;
  document.getElementById('detail-content').innerHTML = `
    ${imgHtml}
    <div style="font-size:11px;color:#bbb;margin-bottom:4px;"># ${p.id}</div>
    <div style="font-size:19px;font-weight:900;margin-bottom:6px;font-family:Poppins,sans-serif;">${p.name}</div>
    <div style="color:var(--yellow);font-size:14px;margin-bottom:6px;">${starsHtml}</div>
    <div style="font-size:13px;color:#555;margin-bottom:10px;line-height:1.5;">${p.desc||''}</div>
    <div style="text-decoration:line-through;color:#bbb;font-size:13px;">Antes: $${p.oldPrice.toLocaleString('es-CO')}</div>
    <div style="color:var(--orange);font-size:28px;font-weight:900;font-family:Poppins,sans-serif;margin-bottom:6px;">$${p.price.toLocaleString('es-CO')}</div>
    <div style="color:var(--green);font-size:13px;font-weight:800;margin-bottom:8px;">✅ Envío GRATIS a toda Colombia</div>
    <div style="color:#0d47a1;font-size:13px;font-weight:700;background:#f0f7ff;padding:8px 12px;border-radius:8px;margin-bottom:12px;">💳 Pago Contra Entrega disponible</div>
    ${p.units<=10?`<div style="color:var(--orange);font-size:12px;font-weight:700;margin-bottom:8px;">⚠️ ¡Solo quedan ${p.units} unidades!</div>`:''}
    <button class="btn-confirm" onclick="closeOverlay('overlay-detail');buyNow('${p.id}')">🛒 Comprar Ahora</button>
  `;
  openOverlay('overlay-detail');
}

// ======= BUY / CART =======
function buyNow(id){
  const p = products.find(x=>x.id===id);
  if(!p) return;
  currentOrderProduct = p;
  const savedAmt = (p.oldPrice - p.price).toLocaleString('es-CO');
  const deliveryDate = getDeliveryDate();
  document.getElementById('order-summary').innerHTML = `
    <div class="os-name">${p.name}</div>
    <div class="os-id"># ${p.id}</div>
    <div class="os-row">
      <span class="os-old">$${p.oldPrice.toLocaleString('es-CO')}</span>
      <span class="os-new">$${p.price.toLocaleString('es-CO')}</span>
    </div>
    <div class="os-save">💰 Ahorras $${savedAmt} en este pedido</div>
  `;
  document.getElementById('delivery-est').textContent = `📅 Estimado de entrega: ${deliveryDate}`;
  openOverlay('overlay-order');
}

function getDeliveryDate(){
  const now = new Date();
  const minDays = 3, maxDays = 7;
  const days = Math.floor(Math.random()*(maxDays-minDays+1))+minDays;
  const d = new Date(now.getTime()+days*24*3600*1000);
  const months = ['enero','febrero','marzo','abril','mayo','junio','julio','agosto','septiembre','octubre','noviembre','diciembre'];
  const days2=['domingo','lunes','martes','miércoles','jueves','viernes','sábado'];
  return `${days2[d.getDay()]} ${d.getDate()} de ${months[d.getMonth()]} de ${d.getFullYear()}`;
}

function confirmOrder(){
  const p = currentOrderProduct;
  const nombre = document.getElementById('f-nombre').value.trim();
  const apellido = document.getElementById('f-apellido').value.trim();
  const ciudad = document.getElementById('f-ciudad').value.trim();
  const dir = document.getElementById('f-direccion').value.trim();
  const tel = document.getElementById('f-telefono').value.trim();
  const nota = document.getElementById('f-nota').value.trim();
  if(!nombre||!apellido||!ciudad||!dir||!tel){ showToast('⚠️ Por favor llena todos los campos obligatorios'); return; }
  const saved = (p.oldPrice-p.price).toLocaleString('es-CO');
  const msg = `🛍️ *NUEVO PEDIDO - TROGUI*\n\n📦 *Producto:* ${p.name}\n🏷️ *ID:* ${p.id}\n💰 *Precio:* $${p.price.toLocaleString('es-CO')} COP\n~~Antes: $${p.oldPrice.toLocaleString('es-CO')}~~\n💎 *Ahorro:* $${saved}\n\n👤 *Nombre:* ${nombre} ${apellido}\n🏙️ *Ciudad:* ${ciudad}\n🏠 *Dirección:* ${dir}\n📞 *Teléfono:* ${tel}\n${nota?'📝 *Nota:* '+nota+'\n':''}\n💳 *Pago:* Contra Entrega\n📅 *Entrega estimada:* ${getDeliveryDate()}`;
  const waNum = '573206572598';
  const waUrl = `https://wa.me/${waNum}?text=${encodeURIComponent(msg)}`;
  // Save order
  const order = {id:p.id,product:p.name,price:p.price,nombre,apellido,ciudad,dir,tel,nota,date:new Date().toLocaleString('es-CO')};
  orders.push(order);
  localStorage.setItem('trogui_orders',JSON.stringify(orders));
  // Clear form
  ['f-nombre','f-apellido','f-ciudad','f-direccion','f-telefono','f-nota'].forEach(id=>document.getElementById(id).value='');
  closeOverlay('overlay-order');
  window.open(waUrl,'_blank');
  showToast('✅ Pedido enviado! Abre WhatsApp para confirmar.');
}

// ======= CART =======
function openCart(){
  renderCart();
  openOverlay('overlay-cart');
}
function renderCart(){
  const el = document.getElementById('cart-items');
  const tel = document.getElementById('cart-total');
  if(!cartItems.length){ el.innerHTML='<p style="color:#999;text-align:center;padding:20px;">Tu carrito está vacío</p>'; tel.textContent=''; return; }
  el.innerHTML = cartItems.map((c,i)=>`<div style="display:flex;align-items:center;gap:12px;padding:10px 0;border-bottom:1px solid #f0f0f0;">
    <span style="font-size:28px;">${c.emoji||'📦'}</span>
    <div style="flex:1;"><div style="font-weight:800;font-size:14px;">${c.name}</div><div style="color:var(--orange);font-weight:900;">$${c.price.toLocaleString('es-CO')}</div></div>
    <button onclick="removeFromCart(${i})" style="background:none;border:none;font-size:18px;cursor:pointer;color:#e57373;">🗑️</button>
  </div>`).join('');
  const total = cartItems.reduce((a,b)=>a+b.price,0);
  tel.innerHTML = `<strong>Total: $${total.toLocaleString('es-CO')} COP</strong>`;
  document.getElementById('cart-count').textContent = cartItems.length;
}
function removeFromCart(i){ cartItems.splice(i,1); renderCart(); }
function checkoutCart(){
  if(!cartItems.length){ showToast('⚠️ Tu carrito está vacío'); return; }
  closeOverlay('overlay-cart');
  const msgs = cartItems.map(c=>`• ${c.name} — $${c.price.toLocaleString('es-CO')}`).join('\n');
  const total = cartItems.reduce((a,b)=>a+b.price,0);
  currentOrderProduct = {id:'CARRITO',name:'Pedido múltiple:\n'+msgs,price:total,oldPrice:total,emoji:'🛒'};
  document.getElementById('order-summary').innerHTML=`<div class="os-name">🛒 Pedido múltiple</div><div>${cartItems.map(c=>`<div style="font-size:13px;padding:4px 0;">• ${c.name} — $${c.price.toLocaleString('es-CO')}</div>`).join('')}</div><div class="os-new" style="margin-top:8px;">Total: $${total.toLocaleString('es-CO')}</div>`;
  document.getElementById('delivery-est').textContent=`📅 Estimado de entrega: ${getDeliveryDate()}`;
  openOverlay('overlay-order');
}

// ======= REVIEWS =======
function renderReviews(){
  const grid = document.getElementById('reviews-grid');
  grid.innerHTML = reviews.map(r=>{
    const starsHtml = '⭐'.repeat(r.stars)+(r.stars<5?'☆'.repeat(5-r.stars):'');
    const initials = r.name.split(' ').slice(0,2).map(w=>w[0]).join('');
    return `<div class="review-card">
      <div class="reviewer">
        <div class="rev-avatar" style="background:${r.color||'#FF4500'}">${initials}</div>
        <div><div class="rev-name">${r.name}</div><div class="rev-loc">📍 ${r.loc}</div></div>
      </div>
      <div class="rev-stars">${starsHtml}</div>
      <div class="rev-text">${r.text}</div>
      ${r.img?`<img src="${r.img}" class="rev-img" alt="">`:''}
    </div>`;
  }).join('');
}

// ======= OVERLAYS =======
function openOverlay(id){ document.getElementById(id).classList.add('show'); document.body.style.overflow='hidden'; }
function closeOverlay(id){ document.getElementById(id).classList.remove('show'); document.body.style.overflow=''; }
document.querySelectorAll('.overlay').forEach(o=>{ o.addEventListener('click',e=>{ if(e.target===o) closeOverlay(o.id); }); });

// ======= ADMIN =======
function askAdminPass(panel){
  pendingPanel = panel;
  document.getElementById('admin-pass-input').value='';
  openOverlay('overlay-pass');
  setTimeout(()=>document.getElementById('admin-pass-input').focus(),200);
}
function checkPass(){
  const val = document.getElementById('admin-pass-input').value;
  if(val===ADMIN_PASS){
    closeOverlay('overlay-pass');
    if(pendingPanel==='r') openAdminR();
    else if(pendingPanel==='c') openAdminC();
    else if(pendingPanel==='e') openAdminE();
  } else {
    showToast('❌ Contraseña incorrecta');
    document.getElementById('admin-pass-input').value='';
  }
}
function closeAdmin(id){ document.getElementById(id).classList.remove('show'); }

// ADMIN R
function openAdminR(){
  const list = document.getElementById('edit-list');
  list.innerHTML = products.map(p=>`<div class="edit-card">
    <div>${p.img?`<img src="${p.img}" style="width:40px;height:40px;object-fit:cover;border-radius:6px;">`:`<span class="edit-emoji">${p.emoji||'📦'}</span>`}</div>
    <div class="edit-info"><div class="edit-name">${p.name}</div><div class="edit-price">$${p.price.toLocaleString('es-CO')} | ID: ${p.id}</div></div>
    <button class="btn-edit" onclick="openEditProduct('${p.id}')">✏️ Editar</button>
    <button class="btn-edit" style="background:#e57373;" onclick="deleteProduct('${p.id}')">🗑️</button>
  </div>`).join('');
  document.getElementById('panel-r').classList.add('show');
}
function deleteProduct(id){
  if(!confirm('¿Eliminar este producto?')) return;
  products = products.filter(p=>p.id!==id);
  saveProducts();
  renderProducts();
  openAdminR();
}
function addNewProduct(){
  const newId = 'TRG-'+(products.length+1).toString().padStart(3,'0');
  const np = {id:newId,name:'Nuevo Producto',emoji:'📦',price:49000,oldPrice:89000,cost:15000,stars:5,sold:0,units:10,timer:0,desc:'Descripción del producto.',img:''};
  products.push(np);
  saveProducts();
  openEditProduct(newId);
  openAdminR();
}
function openEditProduct(id){
  const p = products.find(x=>x.id===id);
  if(!p) return;
  editingProductId = id;
  editingProductImg = p.img||null;
  document.getElementById('ep-name').value = p.name;
  document.getElementById('ep-emoji').value = p.emoji||'📦';
  document.getElementById('ep-cost').value = p.cost||0;
  document.getElementById('ep-price').value = p.price;
  document.getElementById('ep-old').value = p.oldPrice;
  document.getElementById('ep-sold').value = p.sold||0;
  document.getElementById('ep-stars').value = p.stars||5;
  document.getElementById('ep-timer').value = p.timer||0;
  document.getElementById('ep-units').value = p.units||10;
  document.getElementById('ep-desc').value = p.desc||'';
  document.getElementById('ep-img-url').value = p.img||'';
  const prev = document.getElementById('ep-img-preview');
  if(p.img){ prev.src=p.img; prev.style.display='block'; } else { prev.style.display='none'; }
  openOverlay('overlay-edit-prod');
}
function handleProductImgUpload(e){
  const file = e.target.files[0];
  if(!file) return;
  const reader = new FileReader();
  reader.onload = ev => {
    editingProductImg = ev.target.result;
    const prev = document.getElementById('ep-img-preview');
    prev.src = ev.target.result;
    prev.style.display = 'block';
    document.getElementById('ep-img-url').value = '';
  };
  reader.readAsDataURL(file);
}
function saveProductEdit(){
  const p = products.find(x=>x.id===editingProductId);
  if(!p) return;
  p.name = document.getElementById('ep-name').value;
  p.emoji = document.getElementById('ep-emoji').value;
  p.cost = parseInt(document.getElementById('ep-cost').value)||0;
  p.price = parseInt(document.getElementById('ep-price').value)||0;
  p.oldPrice = parseInt(document.getElementById('ep-old').value)||0;
  p.sold = parseInt(document.getElementById('ep-sold').value)||0;
  p.stars = parseInt(document.getElementById('ep-stars').value)||5;
  p.timer = parseInt(document.getElementById('ep-timer').value)||0;
  p.units = parseInt(document.getElementById('ep-units').value)||10;
  p.desc = document.getElementById('ep-desc').value;
  const urlInput = document.getElementById('ep-img-url').value.trim();
  p.img = urlInput || editingProductImg || '';
  saveProducts();
  renderProducts();
  openAdminR();
  closeOverlay('overlay-edit-prod');
  showToast('✅ Producto guardado');
}
function saveProducts(){ localStorage.setItem('trogui_products',JSON.stringify(products)); }

// ADMIN C
function openAdminC(){
  document.getElementById('visitors-count').textContent = visitorsCount;
  const list = document.getElementById('orders-list');
  if(!orders.length){ list.innerHTML='<div style="color:#999;text-align:center;padding:20px;">Aún no hay pedidos</div>'; }
  else {
    list.innerHTML = [...orders].reverse().map(o=>`<div class="order-row">
      <strong>📦 ${o.product}</strong>
      <span>👤 ${o.nombre} ${o.apellido} — 📍 ${o.ciudad}</span><br>
      <span>📞 ${o.tel} | 💰 $${o.price.toLocaleString('es-CO')}</span><br>
      <span style="color:#999;font-size:11px;">📅 ${o.date}</span>
    </div>`).join('');
  }
  document.getElementById('panel-c').classList.add('show');
}

// ADMIN E
function openAdminE(){
  buildBannerEditor();
  buildReviewsEditor();
  document.getElementById('panel-e').classList.add('show');
}
function switchTab(btn,tabId){
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('on'));
  document.querySelectorAll('.tcontent').forEach(t=>t.classList.remove('on'));
  btn.classList.add('on');
  document.getElementById(tabId).classList.add('on');
}
function applyPageSettings(){
  const top = document.getElementById('cfg-topbar').value;
  const mar = document.getElementById('cfg-marquee').value;
  if(top) document.querySelector('.topbar').textContent = top;
  if(mar) document.querySelector('.marquee-inner').textContent = mar;
  const ig = document.getElementById('cfg-ig').value;
  const tt = document.getElementById('cfg-tt').value;
  document.querySelectorAll('.soc-ig').forEach(a=>a.href=ig);
  document.querySelectorAll('.soc-tt').forEach(a=>a.href=tt);
  showToast('✅ Configuración guardada');
}
function changeLogoFile(e){
  const file = e.target.files[0];
  if(!file) return;
  const reader = new FileReader();
  reader.onload = ev => {
    document.getElementById('logo-img').src = ev.target.result;
    localStorage.setItem('trogui_logo', ev.target.result);
    showToast('✅ Logo actualizado');
  };
  reader.readAsDataURL(file);
}
function buildBannerEditor(){
  const el = document.getElementById('banner-editor');
  el.innerHTML = banners.map((b,i)=>`<div style="border:1.5px solid #eee;border-radius:10px;padding:12px;margin-bottom:10px;">
    <div style="font-weight:800;font-size:13px;margin-bottom:8px;">Slide ${i+1}</div>
    <input class="finput" style="margin-bottom:6px;" placeholder="Título" value="${b.h}" onchange="banners[${i}].h=this.value">
    <input class="finput" style="margin-bottom:6px;" placeholder="Subtítulo" value="${b.p}" onchange="banners[${i}].p=this.value">
    <input class="finput" placeholder="Texto botón" value="${b.btn}" onchange="banners[${i}].btn=this.value">
  </div>`).join('');
}
function saveBanners(){
  const slides = document.querySelectorAll('.slide');
  banners.forEach((b,i)=>{
    if(slides[i]){
      slides[i].querySelector('h2').textContent = b.h;
      slides[i].querySelector('p').textContent = b.p;
      slides[i].querySelector('.slide-btn').textContent = b.btn;
    }
  });
  showToast('✅ Banners actualizados');
}
function buildReviewsEditor(){
  const el = document.getElementById('reviews-editor');
  el.innerHTML = reviews.map((r,i)=>`<div style="border:1.5px solid #eee;border-radius:10px;padding:12px;margin-bottom:10px;">
    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;">
      <strong style="font-size:13px;">Reseña ${i+1}</strong>
      <button onclick="deleteReview(${i})" style="background:none;border:none;cursor:pointer;color:#e57373;font-size:16px;">🗑️</button>
    </div>
    <input class="finput" style="margin-bottom:6px;" placeholder="Nombre" value="${r.name}" onchange="reviews[${i}].name=this.value;renderReviews()">
    <input class="finput" style="margin-bottom:6px;" placeholder="Ciudad" value="${r.loc}" onchange="reviews[${i}].loc=this.value;renderReviews()">
    <input class="finput" style="margin-bottom:6px;" placeholder="Estrellas (1-5)" type="number" min="1" max="5" value="${r.stars}" onchange="reviews[${i}].stars=parseInt(this.value);renderReviews()">
    <input class="finput" style="margin-bottom:6px;" placeholder="Texto de la reseña" value="${r.text}" onchange="reviews[${i}].text=this.value;renderReviews()">
    <label class="upload-btn" style="margin-top:4px;">📷 Subir foto a reseña<input type="file" accept="image/*" style="display:none" onchange="addReviewImg(event,${i})"></label>
  </div>`).join('');
}
function addReviewImg(e,i){
  const file = e.target.files[0]; if(!file) return;
  const reader = new FileReader();
  reader.onload = ev=>{ reviews[i].img=ev.target.result; renderReviews(); buildReviewsEditor(); };
  reader.readAsDataURL(file);
}
function deleteReview(i){ reviews.splice(i,1); localStorage.setItem('trogui_reviews',JSON.stringify(reviews)); renderReviews(); buildReviewsEditor(); }
function addReview(){
  reviews.push({name:'Nueva Persona',loc:'Colombia',stars:5,text:'Excelente producto!',color:'#FF4500',img:''});
  localStorage.setItem('trogui_reviews',JSON.stringify(reviews));
  renderReviews(); buildReviewsEditor();
}

// AUDIO
function handleAudioUpload(e){
  const file = e.target.files[0]; if(!file) return;
  const reader = new FileReader();
  reader.onload = ev=>{
    const audio = document.getElementById('store-audio');
    audio.src = ev.target.result;
    audio.play().then(()=>document.getElementById('audio-status').textContent='🎵 Audio activo').catch(()=>document.getElementById('audio-status').textContent='⚠️ El navegador requiere interacción del usuario primero');
    localStorage.setItem('trogui_audio', ev.target.result);
    showToast('✅ Audio configurado');
  };
  reader.readAsDataURL(file);
}
function setAudioFromUrl(){
  const url = document.getElementById('audio-url').value.trim();
  if(!url) return;
  const audio = document.getElementById('store-audio');
  audio.src = url;
  audio.play().catch(()=>{});
  showToast('✅ Audio desde URL aplicado');
}

// ======= PURCHASE ALERT =======
const names = ['Valentina Torres','Juan Camilo Paz','Luisa Fernanda Ríos','Carlos Gómez','María José Vargas','Andrés Morales','Diana Martínez','Sebastián López','Paola Jiménez','Felipe Herrera'];
const cities = ['Bogotá','Medellín','Cali','Barranquilla','Bucaramanga','Pereira','Cartagena','Cúcuta','Manizales','Santa Marta'];
let alertShown = false;
function showPurchaseAlert(){
  const al = document.getElementById('purchase-alert');
  const n = names[Math.floor(Math.random()*names.length)];
  const c = cities[Math.floor(Math.random()*cities.length)];
  const p = products[Math.floor(Math.random()*products.length)];
  document.getElementById('alert-name').textContent = n;
  document.getElementById('alert-msg').textContent = `acaba de pedir ${p.name} para ${c} 🎉`;
  al.style.display = 'block';
  setTimeout(()=>{ al.style.display='none'; setTimeout(showPurchaseAlert, Math.random()*20000+15000); },5000);
}
setTimeout(showPurchaseAlert, 8000);

// ======= TOAST =======
function showToast(msg){
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),3000);
}

// ======= VISITORS =======
setInterval(()=>{ visitorsCount += Math.random()>0.5?1:-1; if(visitorsCount<100)visitorsCount=100; },30000);

// ======= INIT =======
(function init(){
  renderProducts();
  renderReviews();
  // Try to restore audio
  const savedAudio = localStorage.getItem('trogui_audio');
  if(savedAudio){
    const audio = document.getElementById('store-audio');
    audio.src = savedAudio;
    document.addEventListener('click',()=>{ if(audio.paused) audio.play().catch(()=>{}); },{once:true});
  }
})();
</script>
</body>
</html>
