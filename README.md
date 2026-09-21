# velora-shop-
index.html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Velora Store | Premium Shopping</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#fffaf5;
      --card:#ffffff;
      --text:#18181b;
      --muted:#6b7280;
      --line:#f1e7df;
      --primary:#111827;
      --primary-2:#f59e0b;
      --accent:#f97316;
      --success:#16a34a;
      --shadow:0 16px 40px rgba(17,24,39,0.08);
      --radius:22px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body{
      margin:0;
      font-family:'Inter', sans-serif;
      background: linear-gradient(180deg, #fffaf5 0%, #fff 30%, #fff 100%);
      color:var(--text);
    }

    a{
      text-decoration:none;
      color:inherit;
    }

    img{
      max-width:100%;
      display:block;
    }

    button{
      font:inherit;
      cursor:pointer;
    }

    .container{
      width:min(1200px, calc(100% - 32px));
      margin:0 auto;
    }

    .topbar{
      background:#111827;
      color:white;
      font-size:13px;
      padding:10px 0;
    }

    .topbar-inner{
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:20px;
      flex-wrap:wrap;
    }

    .topbar .offers{
      opacity:.9;
      letter-spacing:.03em;
    }

    .topbar .meta{
      display:flex;
      gap:18px;
      opacity:.8;
      flex-wrap:wrap;
    }

    .nav{
      position:sticky;
      top:0;
      z-index:50;
      backdrop-filter: blur(14px);
      background: rgba(255,255,255,.8);
      border-bottom:1px solid rgba(17,24,39,.06);
    }

    .nav-inner{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:20px;
      padding:18px 0;
    }

    .brand{
      display:flex;
      align-items:center;
      gap:12px;
      font-weight:800;
      letter-spacing:.03em;
      font-size:1.35rem;
    }

    .brand-mark{
      width:42px;
      height:42px;
      border-radius:12px;
      background:linear-gradient(135deg, #111827, #f59e0b);
      display:flex;
      align-items:center;
      justify-content:center;
      color:white;
      font-weight:800;
      box-shadow:var(--shadow);
    }

    .nav-menu{
      display:flex;
      align-items:center;
      gap:32px;
      font-weight:500;
      color:#374151;
      flex-wrap:wrap;
    }

    .nav-menu a{
      position:relative;
      opacity:.9;
    }

    .nav-menu a::after{
      content:"";
      position:absolute;
      left:0;
      bottom:-8px;
      width:100%;
      height:2px;
      background:var(--accent);
      transform:scaleX(0);
      transform-origin:left;
      transition:.25s;
    }

    .nav-menu a:hover::after{
      transform:scaleX(1);
    }

    .nav-right{
      display:flex;
      align-items:center;
      gap:16px;
    }

    .search-box{
      width:260px;
      display:flex;
      align-items:center;
      gap:10px;
      background:#f4f4f5;
      border:1px solid #e5e7eb;
      border-radius:999px;
      padding:12px 16px;
      color:#6b7280;
    }

    .search-box input{
      border:none;
      background:transparent;
      flex:1;
      outline:none;
      font-size:14px;
      color:var(--text);
    }

    .cart-btn{
      position:relative;
      background: var(--primary);
      color:white;
      border:none;
      border-radius:14px;
      padding:12px 16px;
      font-weight:600;
      transition:.2s;
    }

    .cart-btn:hover{
      transform:translateY(-1px);
      box-shadow: var(--shadow);
    }

    .cart-count{
      position:absolute;
      top:-8px;
      right:-8px;
      width:22px;
      height:22px;
      border-radius:50%;
      background:var(--accent);
      display:flex;
      align-items:center;
      justify-content:center;
      font-size:11px;
      font-weight:700;
    }

    .hero{
      padding:56px 0 22px;
    }

    .hero-grid{
      display:grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap:32px;
      align-items:center;
    }

    .eyebrow{
      display:inline-flex;
      align-items:center;
      gap:10px;
      background:#fff1db;
      color:#9a5d00;
      border:1px solid #ffd9a3;
      border-radius:999px;
      padding:9px 16px;
      font-weight:600;
      font-size:13px;
      margin-bottom:20px;
    }

    .hero h1{
      font-size: clamp(2.8rem, 5vw, 5rem);
      line-height:.96;
      letter-spacing:-.06em;
      margin:0 0 18px;
      font-weight:900;
    }

    .hero h1 .highlight{
      color: var(--accent);
    }

    .hero p{
      margin:0 0 28px;
      color:var(--muted);
      font-size:1.05rem;
      line-height:1.8;
      max-width:580px;
    }

    .hero-actions{
      display:flex;
      align-items:center;
      gap:16px;
      flex-wrap:wrap;
      margin-bottom:26px;
    }

    .primary-btn, .secondary-btn{
      border:none;
      border-radius:14px;
      padding:16px 22px;
      font-weight:700;
      transition:.2s;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:10px;
    }

    .primary-btn{
      background: linear-gradient(135deg, var(--primary), #1f2937);
      color:white;
      box-shadow:0 18px 30px rgba(17,24,39,.12);
    }

    .secondary-btn{
      background:white;
      color:var(--text);
      border:1px solid var(--line);
    }

    .primary-btn:hover, .secondary-btn:hover{
      transform:translateY(-2px);
    }

    .hero-stats{
      display:flex;
      align-items:center;
      gap:32px;
      flex-wrap:wrap;
    }

    .stat{
      display:flex;
      flex-direction:column;
      gap:5px;
    }

    .stat strong{
      font-size:1.8rem;
      letter-spacing:-.05em;
    }

    .stat span{
      color:var(--muted);
      font-size:.95rem;
    }

    .hero-visual{
      position:relative;
      display:flex;
      justify-content:center;
      align-items:center;
      min-height:500px;
    }

    .product-showcase{
      position:relative;
      width:100%;
      max-width:520px;
      aspect-ratio: 1 / 1.08;
      border-radius:32px;
      background:linear-gradient(135deg,#fcede0,#fff4ca);
      box-shadow: 0 35px 80px rgba(17,24,39,0.12);
      overflow:hidden;
      border:1px solid rgba(17,24,39,.05);
    }

    .showcase-card{
      position:absolute;
      background:white;
      border-radius:24px;
      box-shadow:var(--shadow);
      padding:18px;
    }

    .card-one{
      width:210px;
      left:20px;
      top:50px;
      transform: rotate(-7deg);
    }

    .card-two{
      width:220px;
      right:15px;
      bottom:52px;
      transform: rotate(7deg);
    }

    .showcase-image{
      height:200px;
      border-radius:18px;
      overflow:hidden;
      background-size:cover;
      background-position:center;
      margin-bottom:14px;
    }

    .showcase-card h4{
      margin:0 0 8px;
      font-size:1.1rem;
    }

    .showcase-card p{
      margin:0;
      color:var(--muted);
      font-size:.9rem;
    }

    .price-row{
      margin-top:12px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
    }

    .price-row strong{
      font-size:1.1rem;
    }

    .tag{
      background:#fef3c7;
      color:#92400e;
      border-radius:999px;
      padding:7px 10px;
      font-size:12px;
      font-weight:700;
    }

    .hero-badge{
      position:absolute;
      left:20px;
      bottom:20px;
      background:#111827;
      color:white;
      padding:14px 18px;
      border-radius:16px;
      box-shadow:var(--shadow);
      display:flex;
      align-items:center;
      gap:12px;
    }

    .hero-badge .badge-icon{
      width:40px;
      height:40px;
      border-radius:12px;
      background:linear-gradient(135deg, #f59e0b, #f97316);
      display:grid;
      place-items:center;
      font-size:1.2rem;
    }

    .hero-badge small{
      display:block;
      color:rgba(255,255,255,.76);
      margin-bottom:2px;
    }

    .brands{
      padding:14px 0 22px;
    }

    .brand-row{
      display:grid;
      grid-template-columns: repeat(5, minmax(110px,1fr));
      gap:18px;
      align-items:center;
      padding:18px 20px;
      border:1px solid var(--line);
      border-radius:22px;
      background:rgba(255,255,255,.65);
      text-align:center;
      color:#9ca3af;
      font-weight:700;
      letter-spacing:.08em;
      text-transform:uppercase;
    }

    .section{
      padding:80px 0;
    }

    .section-head{
      display:flex;
      align-items:end;
      justify-content:space-between;
      gap:20px;
      margin-bottom:28px;
      flex-wrap:wrap;
    }

    .section-head h2{
      font-size: clamp(2rem, 3vw, 3rem);
      line-height:1.12;
      letter-spacing:-.05em;
      margin:0;
    }

    .section-head p{
      margin:0;
      color:var(--muted);
      font-size:1rem;
      max-width:560px;
      line-height:1.7;
    }

    .category-grid{
      display:grid;
      grid-template-columns:repeat(4, minmax(220px,1fr));
      gap:20px;
    }

    .category-card{
      background:white;
      border-radius:24px;
      padding:18px;
      border:1px solid var(--line);
      box-shadow:var(--shadow);
      transition:.2s;
    }

    .category-card:hover{
      transform:translateY(-4px);
    }

    .category-card .thumb{
      height:220px;
      border-radius:18px;
      margin-bottom:18px;
      background-size:cover;
      background-position:center;
    }

    .category-card h3{
      margin:0 0 8px;
      font-size:1.2rem;
    }

    .category-card p{
      margin:0;
      color:var(--muted);
      line-height:1.6;
    }

    .filter-bar{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:20px;
      margin:26px 0 26px;
      flex-wrap:wrap;
    }

    .filter-list{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
    }

    .filter-btn{
      padding:11px 16px;
      border:1px solid var(--line);
      background:white;
      border-radius:999px;
      color:#374151;
      font-weight:600;
      transition:.2s;
    }

    .filter-btn.active{
      background: var(--primary);
      color:white;
      border-color: var(--primary);
      box-shadow:0 12px 20px rgba(17,24,39,.12);
    }

    .filter-btn:hover{
      transform:translateY(-1px);
    }

    .sort-box{
      background:white;
      border:1px solid var(--line);
      border-radius:999px;
      padding:11px 16px;
      display:flex;
      align-items:center;
      gap:10px;
      color:#4b5563;
      font-weight:500;
    }

    .sort-box select{
      border:none;
      background:transparent;
      outline:none;
      color:var(--text);
      font:inherit;
      min-width:150px;
    }

    .product-grid{
      display:grid;
      grid-template-columns:repeat(4, minmax(230px,1fr));
      gap:22px;
    }

    .product-card{
      background:white;
      border:1px solid var(--line);
      border-radius:24px;
      overflow:hidden;
      box-shadow:0 18px 40px rgba(17,24,39,.04);
      transition:.25s;
    }

    .product-card:hover{
      transform:translateY(-6px);
      box-shadow:0 22px 50px rgba(17,24,39,.09);
    }

    .product-image{
      height:270px;
      background-size:cover;
      background-position:center;
      position:relative;
    }

    .product-badge{
      position:absolute;
      top:16px;
      left:16px;
      background:rgba(255,255,255,.9);
      border:1px solid rgba(17,24,39,.06);
      border-radius:999px;
      padding:7px 10px;
      font-size:11px;
      font-weight:700;
      color:#111827;
    }

    .product-info{
      padding:18px 18px 20px;
    }

    .product-top{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      margin-bottom:10px;
    }

    .product-name{
      margin:0;
      font-size:1.08rem;
      font-weight:700;
    }

    .fav{
      width:36px;
      height:36px;
      border-radius:50%;
      border:1px solid var(--line);
      background:var(--bg);
      display:grid;
      place-items:center;
      color:#9ca3af;
    }

    .product-meta{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      margin:16px 0 16px;
    }

    .rating{
      color:#f59e0b;
      font-weight:700;
      font-size:.92rem;
    }

    .reviews{
      color:var(--muted);
      font-size:.8rem;
    }

    .price-box{
      display:flex;
      align-items:baseline;
      gap:10px;
    }

    .new-price{
      font-size:1.35rem;
      font-weight:800;
      letter-spacing:-.05em;
    }

    .old-price{
      font-size:.9rem;
      text-decoration:line-through;
      color:var(--muted);
    }

    .add-cart{
      width:100%;
      border:none;
      background:var(--primary);
      color:white;
      border-radius:14px;
      padding:14px 16px;
      font-weight:700;
      margin-top:12px;
      transition:.2s;
    }

    .add-cart:hover{
      background:#0f172a;
      transform:translateY(-1px);
    }

    .mid-banner{
      padding:0 0 30px;
    }

    .banner{
      background:linear-gradient(135deg, #111827, #1f2937 50%, #f59e0b);
      color:white;
      border-radius:30px;
      padding:32px 36px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:20px;
      box-shadow:0 30px 60px rgba(17,24,39,.14);
    }

    .banner h3{
      margin:0 0 8px;
      font-size: clamp(1.8rem, 4vw, 3rem);
      letter-spacing:-.06em;
    }

    .banner p{
      margin:0;
      color:rgba(255,255,255,.8);
      line-height:1.7;
    }

    .promo-tag{
      display:inline-flex;
      align-items:center;
      gap:10px;
      background:rgba(255,255,255,.08);
      border:1px solid rgba(255,255,255,.14);
      border-radius:999px;
      padding:11px 16px;
      font-weight:700;
    }

    .benefits{
      display:grid;
      grid-template-columns: repeat(4, minmax(220px,1fr));
      gap:20px;
      padding-top:10px;
    }

    .benefit-card{
      background:white;
      border:1px solid var(--line);
      border-radius:24px;
      padding:24px 20px;
      box-shadow:0 16px 25px rgba(17,24,39,.04);
    }

    .benefit-icon{
      width:52px;
      height:52px;
      border-radius:16px;
      background:linear-gradient(135deg, #fff2df, #ffd7b6);
      display:grid;
      place-items:center;
      font-size:1.45rem;
      margin-bottom:18px;
    }

    .benefit-card h4{
      margin:0 0 8px;
      font-size:1.08rem;
    }

    .benefit-card p{
      margin:0;
      color:var(--muted);
      line-height:1.7;
    }

    .testimonial{
      background:#fefaf5;
      border:1px solid var(--line);
      border-radius:26px;
      padding:26px;
      box-shadow:var(--shadow);
    }

    .quotes{
      font-size:2rem;
      color:var(--accent);
      margin-bottom:12px;
    }

    .testimonial p{
      margin:0 0 18px;
      color:#374151;
      line-height:1.8;
      font-size:1rem;
    }

    .person{
      display:flex;
      align-items:center;
      gap:14px;
    }

    .avatar{
      width:52px;
      height:52px;
      border-radius:50%;
      background:linear-gradient(135deg, #fde68a, #f59e0b);
      display:grid;
      place-items:center;
      font-weight:800;
      color:#111827;
    }

    .person strong{
      display:block;
      margin-bottom:2px;
    }

    .person span{
      color:var(--muted);
      font-size:.82rem;
    }

    .testimonial-grid{
      display:grid;
      grid-template-columns: repeat(3, minmax(220px,1fr));
      gap:22px;
      margin-top:24px;
    }

    .newsletter{
      background:linear-gradient(135deg, #fff7ed, #fff);
      border:1px solid var(--line);
      border-radius:32px;
      padding:32px;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:24px;
      flex-wrap:wrap;
    }

    .newsletter h3{
      margin:0 0 8px;
      font-size: clamp(1.8rem, 4vw, 2.8rem);
      letter-spacing:-.05em;
    }

    .newsletter p{
      margin:0;
      color:var(--muted);
      line-height:1.7;
    }

    .email-box{
      display:flex;
      align-items:center;
      gap:10px;
      background:white;
      border:1px solid var(--line);
      border-radius:16px;
      padding:8px 10px 8px 16px;
      min-width:min(100%, 450px);
      box-shadow:0 10px 20px rgba(17,24,39,.03);
    }

    .email-box input{
      border:none;
      outline:none;
      flex:1;
      font:inherit;
      min-width:0;
      color:var(--text);
    }

    .subscribe{
      border:none;
      background:var(--primary);
      color:white;
      padding:14px 18px;
      border-radius:12px;
      font-weight:700;
    }

    footer{
      padding:36px 0 60px;
      color:#374151;
    }

    .footer-grid{
      display:grid;
      grid-template-columns: 1.5fr 1fr 1fr 1fr;
      gap:22px;
      padding-top:26px;
      border-top:1px solid var(--line);
    }

    .footer-brand{
      display:flex;
      align-items:center;
      gap:12px;
      font-weight:800;
      font-size:1.22rem;
      margin-bottom:14px;
    }

    .footer-brand .brand-mark{
      width:40px;
      height:40px;
      font-size:.9rem;
    }

    .footer-col p{
      margin:0;
      color:var(--muted);
      line-height:1.8;
    }

    .footer-col h4{
      margin:0 0 12px;
      font-size:1rem;
    }

    .footer-col ul{
      list-style:none;
      padding:0;
      margin:0;
      display:grid;
      gap:10px;
      color:var(--muted);
    }

    .cart-sidebar{
      position:fixed;
      top:0;
      right:-100%;
      width:min(420px, 100%);
      height:100vh;
      background:#fff;
      box-shadow:-15px 0 30px rgba(0,0,0,.1);
      border-left:1px solid var(--line);
      z-index:100;
      transition:.35s ease;
      display:flex;
      flex-direction:column;
    }

    .cart-sidebar.open{
      right:0;
    }

    .cart-head{
      display:flex;
      align-items:center;
      justify-content:space-between;
      padding:22px 22px 18px;
      border-bottom:1px solid var(--line);
      background:#fefaf5;
    }

    .cart-head h3{
      margin:0;
      font-size:1.3rem;
      letter-spacing:-.04em;
    }

    .close-cart{
      width:38px;
      height:38px;
      border:none;
      background:#fff;
      border:1px solid var(--line);
      border-radius:12px;
      font-size:1.2rem;
    }

    .cart-items{
      flex:1;
      overflow:auto;
      padding:18px 18px 0;
    }

    .empty-state{
      text-align:center;
      color:var(--muted);
      padding:50px 22px 20px;
    }

    .cart-item{
      display:flex;
      align-items:center;
      gap:14px;
      border:1px solid var(--line);
      border-radius:18px;
      padding:12px;
      margin-bottom:12px;
      background:#fff;
    }

    .cart-thumb{
      width:78px;
      height:78px;
      border-radius:14px;
      background-size:cover;
      background-position:center;
      flex-shrink:0;
    }

    .cart-item-details{
      flex:1;
    }

    .cart-item-details h4{
      margin:0 0 4px;
      font-size:1rem;
    }

    .cart-item-details p{
      margin:0;
      color:var(--muted);
      font-size:.88rem;
    }

    .qty-row{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      margin-top:12px;
    }

    .qty-controls{
      display:flex;
      align-items:center;
      gap:8px;
      background:#f5f5f5;
      border:1px solid var(--line);
      border-radius:10px;
      padding:4px;
    }

    .qty-controls button{
      width:24px;
      height:24px;
      border:none;
      background:transparent;
      color:var(--text);
      font-size:1.1rem;
      border-radius:8px;
    }

    .qty-controls span{
      width:22px;
      text-align:center;
      font-weight:600;
  