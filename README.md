<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Carmel Coffee — Tân Sơn Nhì, Hồ Chí Minh</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,450;0,9..144,600;1,9..144,450&family=Be+Vietnam+Pro:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --green-deep:#1c2b20;
    --green-mid:#2c4030;
    --paper:#f2ecdd;
    --paper-warm:#e9e0c9;
    --brass:#b3893f;
    --jasmine:#eadfc4;
    --ink:#1c2b20;
    --ink-soft:#3f4f42;
  }
  *{box-sizing:border-box;margin:0;padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--paper);
    color:var(--ink);
    font-family:'Be Vietnam Pro', sans-serif;
    font-weight:400;
    overflow-x:hidden;
  }
  h1,h2,h3{font-family:'Fraunces', serif;font-weight:450;letter-spacing:-0.01em;}
  .eyebrow{
    font-family:'JetBrains Mono', monospace;
    font-size:0.72rem;
    letter-spacing:0.18em;
    text-transform:uppercase;
    color:var(--brass);
  }
  a{color:inherit;}
  img{max-width:100%;display:block;}

  /* ---------- NAV ---------- */
  nav{
    position:fixed;top:0;left:0;right:0;z-index:50;
    display:flex;justify-content:space-between;align-items:center;
    padding:1.1rem clamp(1.2rem,4vw,3rem);
    background:rgba(28,43,32,0.92);
    backdrop-filter:blur(6px);
    color:var(--jasmine);
  }
  .brand{font-family:'Fraunces',serif;font-size:1.15rem;letter-spacing:0.02em;}
  .navlinks{display:flex;gap:clamp(1rem,3vw,2.2rem);font-size:0.85rem;}
  .navlinks a{opacity:0.85;text-decoration:none;transition:opacity .2s;}
  .navlinks a:hover{opacity:1;}
  .navlinks a:focus-visible, .brand:focus-visible{outline:2px solid var(--brass);outline-offset:4px;}

  /* ---------- HERO ---------- */
  .hero{
    min-height:100svh;
    background:radial-gradient(120% 100% at 15% 0%, var(--green-mid) 0%, var(--green-deep) 55%);
    color:var(--paper);
    display:flex;
    flex-direction:column;
    justify-content:center;
    padding:clamp(6rem,10vw,3rem) clamp(1.4rem,6vw,4rem) 4rem;
    position:relative;
  }
  .hero-grid{
    display:grid;
    grid-template-columns:1.15fr 0.85fr;
    gap:clamp(2rem,5vw,4rem);
    align-items:center;
    max-width:1180px;
    margin:0 auto;
    width:100%;
  }
  .hero h1{
    font-size:clamp(2.6rem,6vw,4.6rem);
    line-height:1.02;
    color:var(--jasmine);
    margin:0.9rem 0 1.3rem;
  }
  .hero h1 em{font-style:italic;color:var(--brass);}
  .hero p.lede{
    font-size:1.08rem;
    line-height:1.6;
    color:#cdd8c9;
    max-width:38ch;
    margin-bottom:2rem;
  }
  .hero-cta{display:flex;gap:0.9rem;flex-wrap:wrap;}
  .btn{
    display:inline-flex;align-items:center;gap:0.5rem;
    padding:0.85rem 1.5rem;
    border-radius:2px;
    font-size:0.9rem;
    text-decoration:none;
    border:1px solid var(--brass);
    transition:transform .18s ease, background .18s ease;
  }
  .btn-solid{background:var(--brass);color:var(--green-deep);}
  .btn-solid:hover{transform:translateY(-2px);}
  .btn-ghost{color:var(--jasmine);}
  .btn-ghost:hover{background:rgba(234,223,196,0.08);}

  /* ---------- DRIP SIGNATURE ---------- */
  .drip-wrap{
    position:relative;
    display:flex;
    justify-content:center;
  }
  .drip-scene{width:min(280px,80%);}
  .cup-steam{
    position:absolute;
    animation:steam 4s ease-in-out infinite;
    opacity:0.5;
  }
  @keyframes steam{
    0%{transform:translateY(0) scaleX(1);opacity:0.15;}
    50%{transform:translateY(-14px) scaleX(1.3);opacity:0.5;}
    100%{transform:translateY(-26px) scaleX(0.9);opacity:0;}
  }
  .drop{
    animation:drip 2.2s cubic-bezier(.55,0,.85,.35) infinite;
  }
  .drop:nth-child(2){animation-delay:1.1s;}
  @keyframes drip{
    0%{transform:translateY(0);opacity:0;}
    8%{opacity:1;}
    55%{transform:translateY(46px);opacity:1;}
    62%{transform:translateY(50px);opacity:0;}
    100%{transform:translateY(50px);opacity:0;}
  }
  .ripple{
    transform-origin:center;
    animation:ripple 2.2s ease-out infinite;
    opacity:0;
  }
  .ripple2{animation-delay:1.1s;}
  @keyframes ripple{
    0%,50%{opacity:0;transform:scale(0.3);}
    58%{opacity:0.7;transform:scale(0.5);}
    78%{opacity:0;transform:scale(1.15);}
    100%{opacity:0;}
  }
  @media (prefers-reduced-motion: reduce){
    .drop,.ripple,.cup-steam{animation:none !important;}
  }

  /* ---------- SECTIONS ---------- */
  section{padding:clamp(4rem,8vw,6.5rem) clamp(1.4rem,6vw,4rem);}
  .wrap{max-width:1180px;margin:0 auto;}

  .about{
    display:grid;
    grid-template-columns:0.9fr 1.1fr;
    gap:clamp(2.5rem,6vw,5rem);
    align-items:start;
  }
  .about h2{font-size:clamp(1.9rem,3.4vw,2.6rem);margin:0.6rem 0 1.2rem;}
  .about p{color:var(--ink-soft);line-height:1.75;font-size:1.02rem;margin-bottom:1rem;max-width:56ch;}
  .stat-row{display:flex;gap:2.2rem;margin-top:2rem;flex-wrap:wrap;}
  .stat b{font-family:'Fraunces',serif;font-size:2rem;display:block;color:var(--green-deep);}
  .stat span{font-size:0.8rem;color:var(--ink-soft);text-transform:uppercase;letter-spacing:0.06em;}

  .quotebox{
    background:var(--paper-warm);
    border-left:3px solid var(--brass);
    padding:1.4rem 1.6rem;
    font-family:'Fraunces',serif;
    font-style:italic;
    font-size:1.08rem;
    line-height:1.6;
    color:var(--green-deep);
  }
  .quotebox cite{
    display:block;
    font-family:'JetBrains Mono',monospace;
    font-style:normal;
    font-size:0.72rem;
    letter-spacing:0.08em;
    text-transform:uppercase;
    color:var(--brass);
    margin-top:0.8rem;
  }

  /* ---------- MENU ---------- */
  .menu{background:var(--green-deep);color:var(--jasmine);}
  .menu .eyebrow{color:var(--brass);}
  .menu h2{font-size:clamp(1.9rem,3.4vw,2.6rem);margin:0.6rem 0 2.5rem;color:var(--jasmine);}
  .menu-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(230px,1fr));
    gap:1px;
    background:rgba(234,223,196,0.14);
    border:1px solid rgba(234,223,196,0.14);
  }
  .menu-item{
    background:var(--green-deep);
    padding:1.6rem 1.5rem;
  }
  .menu-item .tag{
    font-family:'JetBrains Mono',monospace;
    font-size:0.68rem;
    letter-spacing:0.1em;
    text-transform:uppercase;
    color:var(--brass);
  }
  .menu-item h3{font-size:1.25rem;margin:0.5rem 0 0.4rem;color:var(--paper);}
  .menu-item p{font-size:0.92rem;color:#b9c4b5;line-height:1.55;}

  /* ---------- VISIT ---------- */
  .visit{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:clamp(2.5rem,6vw,5rem);
  }
  .visit h2{font-size:clamp(1.9rem,3.4vw,2.6rem);margin:0.6rem 0 1.4rem;}
  .info-line{
    display:flex;
    justify-content:space-between;
    gap:1rem;
    padding:0.9rem 0;
    border-bottom:1px solid rgba(28,43,32,0.14);
    font-size:0.95rem;
  }
  .info-line .k{color:var(--ink-soft);font-family:'JetBrains Mono',monospace;font-size:0.78rem;letter-spacing:0.04em;text-transform:uppercase;padding-top:0.15rem;}
  .info-line .v{text-align:right;max-width:60%;}
  .map-frame{
    border:1px solid rgba(28,43,32,0.16);
    height:100%;
    min-height:280px;
    background:var(--paper-warm) url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cpath d='M0 0L120 120M120 0L0 120' stroke='%23b3893f' stroke-opacity='0.08' stroke-width='1'/%3E%3C/svg%3E");
    display:flex;
    align-items:center;
    justify-content:center;
    padding:2rem;
    text-align:center;
  }
  .map-frame a{
    font-family:'Fraunces',serif;
    font-style:italic;
    color:var(--green-deep);
    text-decoration:none;
    border-bottom:1px solid var(--brass);
    padding-bottom:2px;
  }

  footer{
    padding:2.2rem clamp(1.4rem,6vw,4rem);
    background:var(--green-deep);
    color:#8fa189;
    display:flex;
    justify-content:space-between;
    flex-wrap:wrap;
    gap:0.6rem;
    font-size:0.8rem;
    font-family:'JetBrains Mono',monospace;
  }

  @media (max-width:820px){
    .hero-grid, .about, .visit{grid-template-columns:1fr;}
    .drip-wrap{order:-1;margin-bottom:1rem;}
    .hero p.lede{max-width:none;}
    .navlinks{display:none;}
  }
</style>
</head>
<body>

<nav>
  <a class="brand" href="#top">Carmel Coffee</a>
  <div class="navlinks">
    <a href="#about">Quán</a>
    <a href="#menu">Thức uống</a>
    <a href="#visit">Ghé quán</a>
  </div>
</nav>

<header class="hero" id="top">
  <div class="hero-grid">
    <div>
      <p class="eyebrow">Tân Sơn Nhì · Hồ Chí Minh</p>
      <h1>Small cup,<br><em>slow</em> afternoon.</h1>
      <p class="lede">A tucked-away corner café on Đỗ Nhuận — two air conditioners, a handful of tables, and drinks poured by people who remember how you take your tea. No rush here.</p>
      <div class="hero-cta">
        <a class="btn btn-solid" href="#visit">Find the door</a>
        <a class="btn btn-ghost" href="tel:+84908944347">Call ahead</a>
      </div>
    </div>
    <div class="drip-wrap">
      <svg class="drip-scene" viewBox="0 0 240 300" fill="none" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Illustration of a phin coffee filter dripping into a cup">
        <!-- phin filter -->
        <ellipse cx="120" cy="60" rx="46" ry="10" stroke="#eadfc4" stroke-width="2"/>
        <path d="M74 60 L86 92 L154 92 L166 60" stroke="#eadfc4" stroke-width="2" fill="none"/>
        <ellipse cx="120" cy="92" rx="34" ry="7" stroke="#eadfc4" stroke-width="2"/>
        <rect x="112" y="30" width="16" height="18" rx="2" stroke="#eadfc4" stroke-width="2"/>
        <!-- steam -->
        <path class="cup-steam" d="M100 150 C 96 140, 106 136, 102 126" stroke="#cdd8c9" stroke-width="2" fill="none" stroke-linecap="round"/>
        <path class="cup-steam" d="M124 150 C 120 140, 130 136, 126 126" stroke="#cdd8c9" stroke-width="2" fill="none" stroke-linecap="round" style="animation-delay:1.3s"/>
        <!-- drops -->
        <path class="drop" d="M120 98 q4 6 0 11 q-4 -5 0 -11 Z" fill="#b3893f"/>
        <path class="drop" d="M120 98 q4 6 0 11 q-4 -5 0 -11 Z" fill="#b3893f"/>
        <!-- cup -->
        <path d="M78 170 L84 230 Q120 244 156 230 L162 170 Z" stroke="#eadfc4" stroke-width="2" fill="#233828"/>
        <path d="M162 180 Q188 180 186 200 Q184 218 160 216" stroke="#eadfc4" stroke-width="2" fill="none"/>
        <ellipse class="ripple" cx="120" cy="176" rx="26" ry="5" stroke="#b3893f" stroke-width="1.5" fill="none"/>
        <ellipse class="ripple ripple2" cx="120" cy="176" rx="26" ry="5" stroke="#b3893f" stroke-width="1.5" fill="none"/>
        <!-- saucer -->
        <ellipse cx="120" cy="246" rx="66" ry="9" stroke="#eadfc4" stroke-width="2" fill="none"/>
      </svg>
    </div>
  </div>
</header>

<section class="about" id="about">
  <div>
    <p class="eyebrow">The quán</p>
    <h2>Nhỏ mà chill — small, but chill.</h2>
    <div class="stat-row">
      <div class="stat"><b>5.0</b><span>Google rating</span></div>
      <div class="stat"><b>41</b><span>reviews</span></div>
      <div class="stat"><b>6:30–22:00</b><span>open daily</span></div>
    </div>
  </div>
  <div>
    <p>Regulars describe Carmel Coffee the same way, over and over: small space, strong AC, big welcome. It's the kind of café where the owner notices your bottle is empty before you do, and a staff member catches your eye the moment you need something — a charging cable, a water refill, a lower sugar level on your next round.</p>
    <p>It won't fit a crowd, and it isn't trying to. It's built for one good conversation, one slow drink, one cool hour off the street.</p>
    <div class="quotebox">
      "The space is small but neat and charming — the tea is full of flavor, perfect for a small gathering."
      <cite>— Google review</cite>
    </div>
  </div>
</section>

<section class="menu" id="menu">
  <div class="wrap">
    <p class="eyebrow">On the menu</p>
    <h2>What regulars order</h2>
    <div class="menu-grid">
      <div class="menu-item">
        <p class="tag">Signature</p>
        <h3>Jasmine milk tea</h3>
        <p>The house favorite. Ask for it less sweet if you like your tea to lead.</p>
      </div>
      <div class="menu-item">
        <p class="tag">Signature</p>
        <h3>Jasmine matcha</h3>
        <p>Named in review after review as the reason people come back.</p>
      </div>
      <div class="menu-item">
        <p class="tag">Classic</p>
        <h3>Cà phê phin</h3>
        <p>Slow-dripped black or with condensed milk, the traditional way.</p>
      </div>
      <div class="menu-item">
        <p class="tag">Classic</p>
        <h3>Cà phê muối</h3>
        <p>Salted coffee cream, cold over ice — a Huế-born favorite gone national.</p>
      </div>
    </div>
  </div>
</section>

<section class="visit" id="visit">
  <div>
    <p class="eyebrow">Ghé quán</p>
    <h2>Find your seat</h2>
    <div class="info-line"><span class="k">Address</span><span class="v">30/49 Đỗ Nhuận, Tân Sơn Nhì, Hồ Chí Minh</span></div>
    <div class="info-line"><span class="k">Hours</span><span class="v">6:30 AM – 10:00 PM, every day</span></div>
    <div class="info-line"><span class="k">Phone</span><span class="v"><a href="tel:+84908944347">+84 90 894 43 47</a></span></div>
    <div class="info-line"><span class="k">Price</span><span class="v">$ — easygoing, everyday prices</span></div>
  </div>
  <div class="map-frame">
    <a href="https://maps.app.goo.gl/9cNis8C9ujfS1dn18" target="_blank" rel="noopener">Open in Google Maps →</a>
  </div>
</section>

<footer>
  <span>Carmel Coffee — Tân Sơn Nhì</span>
  <span>Fan-made site, unofficial</span>
</footer>

</body>
</html>
