<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fiducia Domus — Importação Europeia</title>
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500;700&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@200;300;400;500;600&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

:root {
  --verde-escuro:  #3D4931;
  --verde-medio:   #88AB75;
  --off-white:     #FEF5EF;
  --vermelho:      #A22C29;
  --laranja:       #F5853F;
  --verde-hover:   #2e3824;
  --text-dark:     #1E2318;
  --text-muted:    #5A6350;
  --border:        rgba(61,73,49,.12);
}

body {
  background: var(--off-white);
  color: var(--text-dark);
  font-family: 'Jost', sans-serif;
  font-weight: 300;
  overflow-x: hidden;
}

::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--off-white); }
::-webkit-scrollbar-thumb { background: var(--verde-medio); }

/* ─── NAV ─── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 900;
  display: flex; align-items: center; justify-content: space-between;
  padding: 2rem 5rem;
  transition: background .5s, padding .4s, box-shadow .4s;
}
nav.scrolled {
  background: rgba(254,245,239,.97);
  backdrop-filter: blur(16px);
  padding: 1.1rem 5rem;
  box-shadow: 0 1px 0 var(--border);
}
.nav-logo { display: flex; align-items: center; gap: .9rem; text-decoration: none; }
.nav-logo-text { display: flex; flex-direction: column; line-height: 1.1; }
.nav-logo-text .fiducia {
  font-family: 'Cinzel', serif; font-size: .85rem; letter-spacing: .2em;
  color: var(--off-white); transition: color .4s;
}
.nav-logo-text .domus {
  font-family: 'Cinzel', serif; font-size: .85rem; letter-spacing: .2em;
  color: var(--laranja);
}
nav.scrolled .nav-logo-text .fiducia { color: var(--verde-escuro); }

.nav-links { display: flex; gap: 2.8rem; list-style: none; }
.nav-links a {
  font-size: .68rem; letter-spacing: .2em; text-transform: uppercase;
  color: rgba(254,245,239,.6); text-decoration: none; transition: color .3s;
}
nav.scrolled .nav-links a { color: var(--text-muted); }
.nav-links a:hover { color: var(--laranja); }

.nav-btn {
  font-family: 'Jost', sans-serif; font-size: .68rem; font-weight: 500;
  letter-spacing: .18em; text-transform: uppercase;
  padding: .7rem 1.8rem; background: var(--laranja); color: #fff;
  border: none; text-decoration: none; cursor: pointer;
  transition: background .3s, transform .2s; display: inline-block;
}
.nav-btn:hover { background: #e0723a; transform: translateY(-1px); }

/* ─── HERO ─── */
.hero {
  min-height: 100vh; position: relative;
  display: flex; flex-direction: column;
  justify-content: flex-end; padding: 0 5rem 9rem;
  overflow: hidden;
}
.hero-bg {
  position: absolute; inset: 0;
  background:
    linear-gradient(160deg, rgba(29,35,22,.92) 0%, rgba(40,50,30,.78) 45%, rgba(61,73,49,.5) 100%),
    url('https://images.unsplash.com/photo-1474722883778-792e7fb1bd55?w=1800&q=85') center/cover no-repeat;
}
.hero-bg::after {
  content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 35%;
  background: linear-gradient(to top, var(--off-white) 0%, transparent 100%);
}
.hero-content { position: relative; z-index: 2; max-width: 860px; }

.hero-eyebrow {
  display: flex; align-items: center; gap: 1.2rem;
  font-size: .6rem; letter-spacing: .5em; text-transform: uppercase;
  color: var(--laranja); margin-bottom: 2.2rem;
  opacity: 0; animation: fadeUp .7s .2s forwards;
}
.hero-eyebrow::before { content: ''; width: 40px; height: 1px; background: var(--laranja); }

.hero h1 {
  font-family: 'Cormorant Garamond', serif; font-weight: 300;
  font-size: clamp(3rem, 6.5vw, 5.6rem); line-height: 1.06;
  color: var(--off-white); margin-bottom: 2rem;
  opacity: 0; animation: fadeUp .9s .4s forwards;
}
.hero h1 em { font-style: italic; color: rgba(254,245,239,.45); }

.hero-sub {
  font-size: 1rem; font-weight: 300; line-height: 1.85;
  color: rgba(254,245,239,.55); max-width: 540px; margin-bottom: 3.5rem;
  opacity: 0; animation: fadeUp .9s .6s forwards;
}
.hero-cta {
  display: inline-flex; align-items: center; gap: 1.2rem;
  padding: 1.1rem 2.6rem; background: var(--laranja); color: #fff;
  font-size: .72rem; font-weight: 500; letter-spacing: .2em; text-transform: uppercase;
  text-decoration: none; transition: background .3s, transform .3s;
  opacity: 0; animation: fadeUp .9s .8s forwards;
}
.hero-cta:hover { background: #e0723a; transform: translateY(-2px); }
.hero-cta .arr { transition: transform .3s; }
.hero-cta:hover .arr { transform: translateX(5px); }

/* ─── SECTION BASE ─── */
section { padding: 8rem 5rem; }
.sec-tag {
  display: inline-flex; align-items: center; gap: .8rem;
  font-size: .6rem; letter-spacing: .45em; text-transform: uppercase;
  color: var(--laranja); margin-bottom: 1.6rem;
}
.sec-tag::before { content: ''; width: 28px; height: 1px; background: var(--laranja); }

/* ─── QUEM SOMOS ─── */
.quem-somos { background: var(--off-white); }
.qs-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 7rem; align-items: center; }
.qs-text h2 {
  font-family: 'Cormorant Garamond', serif; font-size: clamp(2.2rem, 4vw, 3.6rem);
  font-weight: 400; line-height: 1.12; color: var(--verde-escuro); margin-bottom: 2.5rem;
}
.qs-text h2 em { font-style: italic; color: var(--vermelho); }
.qs-text p { font-size: .95rem; line-height: 1.9; color: var(--text-muted); margin-bottom: 1.4rem; }
.qs-text p strong { color: var(--text-dark); font-weight: 400; }

.qs-visual { position: relative; }
.qs-photo {
  width: 88%; height: 520px;
  background: url('https://images.unsplash.com/photo-1510812431401-41d2bd2722f3?w=900&q=85') center/cover;
  filter: saturate(.8) contrast(1.05); display: block;
}
.qs-badge {
  position: absolute; right: 0; bottom: -2.5rem;
  width: 160px; height: 160px; background: var(--vermelho);
  display: flex; flex-direction: column; align-items: center; justify-content: center; text-align: center; padding: 1.5rem;
}
.qs-badge .big { font-family: 'Cormorant Garamond', serif; font-size: 2.8rem; font-weight: 300; color: var(--off-white); line-height: 1; }
.qs-badge .small { font-size: .6rem; letter-spacing: .2em; text-transform: uppercase; color: rgba(254,245,239,.65); margin-top: .4rem; }

/* ─── EUROPA ─── */
.europa { background: var(--verde-escuro); position: relative; overflow: hidden; }
.europa-wm {
  position: absolute; right: -2rem; top: 50%; transform: translateY(-50%);
  font-family: 'Cinzel', serif; font-size: clamp(8rem, 15vw, 14rem); font-weight: 700;
  color: rgba(255,255,255,.028); letter-spacing: -.03em; white-space: nowrap;
  pointer-events: none; user-select: none;
}
.europa-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 7rem; align-items: center; position: relative; z-index: 1; }
.europa-text .sec-tag { color: var(--laranja); }
.europa-text .sec-tag::before { background: var(--laranja); }
.europa-text h2 {
  font-family: 'Cormorant Garamond', serif; font-size: clamp(2.2rem, 4vw, 3.4rem);
  font-weight: 400; line-height: 1.15; color: var(--off-white); margin-bottom: 2rem;
}
.europa-text h2 em { font-style: italic; color: var(--laranja); }
.europa-text p { font-size: .95rem; line-height: 1.9; color: rgba(254,245,239,.5); margin-bottom: 1.2rem; }

.pillars { display: flex; flex-direction: column; gap: 1px; }
.pillar {
  display: flex; align-items: flex-start; gap: 1.5rem; padding: 1.8rem 2rem;
  border-left: 2px solid rgba(254,245,239,.07); transition: border-color .3s, background .3s;
}
.pillar:hover { border-left-color: var(--laranja); background: rgba(245,133,63,.04); }
.pillar-ico { color: var(--laranja); flex-shrink: 0; margin-top: .1rem; }
.pillar h4 { font-family: 'Cinzel', serif; font-size: .7rem; letter-spacing: .12em; color: var(--off-white); margin-bottom: .4rem; }
.pillar p { font-size: .82rem; line-height: 1.7; color: rgba(254,245,239,.4); }

/* ─── PORTFOLIO ─── */
.portfolio { background: var(--off-white); }
.portfolio h2 {
  font-family: 'Cormorant Garamond', serif; font-size: clamp(2.2rem, 4vw, 3.4rem);
  font-weight: 400; line-height: 1.12; color: var(--verde-escuro); margin-bottom: 1rem;
}
.portfolio-intro { font-size: .95rem; line-height: 1.85; color: var(--text-muted); max-width: 600px; margin-bottom: 4rem; }
.pgrid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.5rem; margin-bottom: 2rem; }
.pcard { position: relative; overflow: hidden; aspect-ratio: 3/4; background: var(--verde-escuro); }
.pcard-bg {
  position: absolute; inset: 0; background-size: cover; background-position: center;
  transition: transform .6s cubic-bezier(.25,.46,.45,.94), filter .6s; filter: saturate(.7);
}
.pcard:hover .pcard-bg { transform: scale(1.06); filter: saturate(.95); }
.pcard-ov {
  position: absolute; inset: 0;
  background: linear-gradient(to top, rgba(29,35,22,.93) 0%, rgba(29,35,22,.15) 60%, transparent 100%);
}
.pcard-txt { position: absolute; bottom: 0; left: 0; right: 0; padding: 1.8rem 1.6rem; }
.pcard-cat { font-size: .58rem; letter-spacing: .35em; text-transform: uppercase; color: var(--laranja); display: block; margin-bottom: .5rem; }
.pcard h3 { font-family: 'Cormorant Garamond', serif; font-size: 1.3rem; font-weight: 400; color: var(--off-white); line-height: 1.2; }
.pcard p {
  font-size: .78rem; color: rgba(254,245,239,.5); line-height: 1.6; margin-top: .5rem;
  max-height: 0; overflow: hidden; transition: max-height .4s, opacity .4s; opacity: 0;
}
.pcard:hover p { max-height: 60px; opacity: 1; }
.portfolio-note {
  font-size: .78rem; color: var(--text-muted); font-style: italic; letter-spacing: .04em;
  padding-left: 1rem; border-left: 2px solid var(--verde-medio);
}

/* ─── OPERACAO ─── */
.operacao { background: #F6EDE4; }
.operacao h2 {
  font-family: 'Cormorant Garamond', serif; font-size: clamp(2rem, 3.5vw, 3.2rem);
  font-weight: 400; line-height: 1.12; color: var(--verde-escuro); margin-bottom: .8rem;
}
.operacao .sub { font-size: .9rem; color: var(--text-muted); margin-bottom: 4.5rem; line-height: 1.7; }
.steps { display: grid; grid-template-columns: repeat(4, 1fr); gap: 0; border-top: 1px solid var(--border); }
.step {
  padding: 3rem 2rem 2.5rem; border-right: 1px solid var(--border);
  transition: background .3s;
}
.step:last-child { border-right: none; }
.step:hover { background: rgba(61,73,49,.04); }
.step-n { font-family: 'Cormorant Garamond', serif; font-size: 4rem; font-weight: 300; color: var(--verde-medio); opacity: .35; line-height: 1; margin-bottom: 1.5rem; display: block; }
.step h4 { font-family: 'Cinzel', serif; font-size: .7rem; letter-spacing: .15em; color: var(--verde-escuro); margin-bottom: .8rem; }
.step p { font-size: .85rem; line-height: 1.75; color: var(--text-muted); }
.step-tag { display: inline-block; margin-top: 1.2rem; font-size: .6rem; letter-spacing: .25em; text-transform: uppercase; color: var(--laranja); padding: .3rem .8rem; border: 1px solid rgba(245,133,63,.25); }

/* ─── CONTATO ─── */
.contato {
  background: var(--verde-escuro);
  display: grid; grid-template-columns: 1fr 1fr; gap: 7rem; align-items: start;
}
.contato-txt .sec-tag { color: var(--laranja); }
.contato-txt .sec-tag::before { background: var(--laranja); }
.contato-txt h2 {
  font-family: 'Cormorant Garamond', serif; font-size: clamp(2.2rem, 4vw, 3.2rem);
  font-weight: 400; line-height: 1.15; color: var(--off-white); margin-bottom: 1.5rem;
}
.contato-txt h2 em { font-style: italic; color: var(--laranja); }
.contato-txt p { font-size: .95rem; line-height: 1.9; color: rgba(254,245,239,.5); margin-bottom: 1.2rem; }
.contato-txt .note { font-size: .82rem; font-style: italic; color: rgba(254,245,239,.28); }

.cform { display: flex; flex-direction: column; gap: 1.2rem; }
.fg { display: flex; flex-direction: column; gap: .45rem; }
.fg label { font-size: .6rem; letter-spacing: .3em; text-transform: uppercase; color: rgba(254,245,239,.35); }
.fg input, .fg textarea, .fg select {
  background: rgba(254,245,239,.05); border: 1px solid rgba(254,245,239,.1);
  color: var(--off-white); font-family: 'Jost', sans-serif; font-size: .9rem; font-weight: 300;
  padding: .9rem 1.2rem; outline: none; resize: none; appearance: none;
  transition: border-color .3s, background .3s;
}
.fg select option { background: var(--verde-escuro); color: var(--off-white); }
.fg input:focus, .fg textarea:focus, .fg select:focus { border-color: var(--laranja); background: rgba(245,133,63,.05); }
.fg input::placeholder, .fg textarea::placeholder { color: rgba(254,245,239,.2); }
.frow { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }
.fbtn {
  display: inline-flex; align-items: center; gap: 1rem; padding: 1.1rem 2.4rem;
  background: var(--laranja); color: #fff; font-family: 'Jost', sans-serif;
  font-size: .72rem; font-weight: 500; letter-spacing: .2em; text-transform: uppercase;
  border: none; cursor: pointer; transition: background .3s, transform .2s;
  margin-top: .5rem; align-self: flex-start;
}
.fbtn:hover { background: #e0723a; transform: translateY(-2px); }

/* ─── FOOTER ─── */
footer {
  background: var(--verde-hover); padding: 3.5rem 5rem;
  display: flex; align-items: center; justify-content: space-between;
  border-top: 1px solid rgba(254,245,239,.06);
}
.footer-brand { font-family: 'Cinzel', serif; font-size: .78rem; letter-spacing: .22em; line-height: 1.5; }
.footer-brand .f { color: var(--off-white); display: block; }
.footer-brand .d { color: var(--laranja); display: block; }
.footer-copy { font-size: .65rem; letter-spacing: .08em; color: rgba(254,245,239,.22); }
.footer-links { display: flex; gap: 2rem; }
.footer-links a { font-size: .62rem; letter-spacing: .18em; text-transform: uppercase; color: rgba(254,245,239,.28); text-decoration: none; transition: color .3s; }
.footer-links a:hover { color: var(--laranja); }

/* ─── ANIMATIONS ─── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(22px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

.reveal { opacity: 0; transform: translateY(28px); transition: opacity .8s cubic-bezier(.25,.46,.45,.94), transform .8s cubic-bezier(.25,.46,.45,.94); }
.reveal.visible { opacity: 1; transform: none; }
.d1 { transition-delay: .1s; }
.d2 { transition-delay: .2s; }
.d3 { transition-delay: .3s; }
.d4 { transition-delay: .4s; }

/* ─── RESPONSIVE ─── */
@media (max-width: 1024px) {
  nav, nav.scrolled { padding-left: 2.5rem; padding-right: 2.5rem; }
  .hero { padding: 0 2.5rem 7rem; }
  section { padding: 6rem 2.5rem; }
  .qs-inner, .europa-inner, .contato { grid-template-columns: 1fr; gap: 4rem; }
  .pgrid { grid-template-columns: repeat(2, 1fr); }
  .steps { grid-template-columns: repeat(2, 1fr); }
  .step:nth-child(2) { border-right: none; }
  footer { flex-direction: column; gap: 1.5rem; text-align: center; }
}
@media (max-width: 640px) {
  .nav-links { display: none; }
  .hero h1 { font-size: 2.6rem; }
  .pgrid { grid-template-columns: 1fr; }
  .steps { grid-template-columns: 1fr; }
  .frow { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
  <a href="#" class="nav-logo">
    <!-- Logo SVG recriado vetorialmente -->
    <svg width="36" height="36" viewBox="0 0 100 110" fill="none" xmlns="http://www.w3.org/2000/svg">
      <!-- Hexágono/escudo externo -->
      <path d="M50 4 L88 24 L88 68 Q88 92 50 106 Q12 92 12 68 L12 24 Z" fill="none" stroke="#FEF5EF" stroke-width="3.5" opacity="0.7"/>
      <!-- Escudo interno -->
      <path d="M50 15 L78 30 L78 65 Q78 84 50 96 Q22 84 22 65 L22 30 Z" fill="none" stroke="#FEF5EF" stroke-width="2" opacity="0.3"/>
      <!-- Letra D estilizada -->
      <path d="M38 38 L38 72 L53 72 Q67 72 67 55 Q67 38 53 38 Z" fill="none" stroke="#FEF5EF" stroke-width="3" stroke-linejoin="round"/>
      <!-- Pé do D -->
      <line x1="50" y1="72" x2="50" y2="76" stroke="#FEF5EF" stroke-width="2" opacity="0.5"/>
      <!-- Estrelas -->
      <polygon points="33,8 34.2,11.7 38,11.7 35,13.8 36.2,17.5 33,15.4 29.8,17.5 31,13.8 28,11.7 31.8,11.7" fill="#F5853F"/>
      <polygon points="50,5 51.2,8.7 55,8.7 52,10.8 53.2,14.5 50,12.4 46.8,14.5 48,10.8 45,8.7 48.8,8.7" fill="#F5853F"/>
      <polygon points="67,8 68.2,11.7 72,11.7 69,13.8 70.2,17.5 67,15.4 63.8,17.5 65,13.8 62,11.7 65.8,11.7" fill="#F5853F"/>
    </svg>
    <span class="nav-logo-text">
      <span class="fiducia">FIDUCIA</span>
      <span class="domus">DOMUS</span>
    </span>
  </a>
  <ul class="nav-links">
    <li><a href="#quem-somos">Quem Somos</a></li>
    <li><a href="#portfolio">Portfólio</a></li>
    <li><a href="#operacao">Operação</a></li>
    <li><a href="#contato">Contato</a></li>
  </ul>
  <a href="#contato" class="nav-btn">Entre em Contato</a>
</nav>

<!-- HERO -->
<div class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">Importação Europeia · Brasil</div>
    <h1>Produtos do<br>Velho Mundo.<br><em>Distribuídos no Brasil</em><br>por quem entende<br>o que está trazendo.</h1>
    <p class="hero-sub">A Fiducia Domus seleciona, importa e distribui produtos europeus de qualidade para atacadistas, restaurantes e empresas em todo o Brasil.</p>
    <a href="#contato" class="hero-cta">Entre em contato <span class="arr">→</span></a>
  </div>
</div>

<!-- QUEM SOMOS -->
<section class="quem-somos" id="quem-somos">
  <div class="qs-inner">
    <div class="qs-text reveal">
      <div class="sec-tag">Quem Somos</div>
      <h2>Não intermediamos.<br><em>Nós escolhemos.</em></h2>
      <p>A Fiducia Domus <strong>não é uma trading</strong>. Não esperamos pedido para buscar produto. Não trabalhamos com qualquer fornecedor, nem com qualquer mercadoria.</p>
      <p>Nós identificamos produtos europeus com real potencial para o mercado brasileiro, <strong>desenvolvemos o relacionamento com os fornecedores</strong>, estruturamos a importação e vendemos no Brasil.</p>
      <p>É uma postura diferente. E ela reflete diretamente no que chegamos ao mercado.</p>
    </div>
    <div class="qs-visual reveal d2">
      <div class="qs-photo"></div>
      <div class="qs-badge">
        <span class="big">100%</span>
        <span class="small">Origem<br>Europeia</span>
      </div>
    </div>
  </div>
</section>

<!-- EUROPA É CRITÉRIO -->
<section class="europa" id="europa">
  <div class="europa-wm">EUROPA</div>
  <div class="europa-inner">
    <div class="europa-text reveal">
      <div class="sec-tag">O Que Nos Move</div>
      <h2>Europa não é<br>só origem.<br><em>É critério.</em></h2>
      <p>Existe uma razão pela qual produtos do Velho Mundo carregam uma reputação que nenhum rótulo genérico consegue imitar. Séculos de técnica, terroir, cultura produtiva.</p>
      <p>Não trabalhamos com volume por volume. Trabalhamos com produtos que têm história, qualidade e mercado — e que o Brasil ainda não acessa da forma que merece.</p>
    </div>
    <div class="pillars reveal d2">
      <div class="pillar">
        <span class="pillar-ico">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 2a14.5 14.5 0 0 0 0 20 14.5 14.5 0 0 0 0-20"/><path d="M2 12h20"/></svg>
        </span>
        <div>
          <h4>Curadoria com Critério</h4>
          <p>Não trazemos qualquer produto. Trazemos o que tem mercado, história e procedência verificada.</p>
        </div>
      </div>
      <div class="pillar">
        <span class="pillar-ico">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
        </span>
        <div>
          <h4>Operação Sem Gaps</h4>
          <p>Da negociação ao desembaraço, a cadeia está nas nossas mãos. Sem terceiros invisíveis.</p>
        </div>
      </div>
      <div class="pillar">
        <span class="pillar-ico">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
        </span>
        <div>
          <h4>Rede de Distribuição Ativa</h4>
          <p>Não esperamos pedido. Construímos demanda com atacadistas, restaurantes e empresas.</p>
        </div>
      </div>
      <div class="pillar">
        <span class="pillar-ico">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
        </span>
        <div>
          <h4>Inteligência de Mercado Local</h4>
          <p>Sabemos onde, como e para quem colocar cada produto no mercado brasileiro.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PORTFÓLIO -->
<section class="portfolio" id="portfolio">
  <div class="sec-tag reveal">Portfólio</div>
  <h2 class="reveal">O que trazemos.</h2>
  <p class="portfolio-intro reveal">Começamos com categorias onde a origem europeia faz toda a diferença — e onde o mercado brasileiro ainda é mal abastecido por quem realmente entende o produto.</p>
  <div class="pgrid">
    <div class="pcard reveal">
      <div class="pcard-bg" style="background-image:url('https://images.unsplash.com/photo-1510812431401-41d2bd2722f3?w=600&q=85')"></div>
      <div class="pcard-ov"></div>
      <div class="pcard-txt">
        <span class="pcard-cat">Europa · Portfólio</span>
        <h3>Vinhos Europeus</h3>
        <p>Seleção criteriosa de vinhedos com terroir e procedência verificada.</p>
      </div>
    </div>
    <div class="pcard reveal d1">
      <div class="pcard-bg" style="background-image:url('https://images.unsplash.com/photo-1474979266404-7eaacbcd87c5?w=600&q=85')"></div>
      <div class="pcard-ov"></div>
      <div class="pcard-txt">
        <span class="pcard-cat">Europa · Portfólio</span>
        <h3>Azeites & Gourmet</h3>
        <p>Azeites, conservas e produtos gastronômicos de origem controlada.</p>
      </div>
    </div>
    <div class="pcard reveal d2">
      <div class="pcard-bg" style="background-image:url('https://images.unsplash.com/photo-1506354666786-959d6d497f1a?w=600&q=85')"></div>
      <div class="pcard-ov"></div>
      <div class="pcard-txt">
        <span class="pcard-cat">Europa · Portfólio</span>
        <h3>Produtos Gourmet</h3>
        <p>O melhor da tradição alimentar europeia para o paladar brasileiro.</p>
      </div>
    </div>
    <div class="pcard reveal d3">
      <div class="pcard-bg" style="background-image:url('https://images.unsplash.com/photo-1555041469-a586c61ea9bc?w=600&q=85')"></div>
      <div class="pcard-ov"></div>
      <div class="pcard-txt">
        <span class="pcard-cat">Europa · Portfólio</span>
        <h3>Lifestyle & Decoração</h3>
        <p>Itens com design e procedência que comunicam mais do que qualquer rótulo nacional.</p>
      </div>
    </div>
  </div>
  <p class="portfolio-note reveal">O portfólio cresce com critério. Novas categorias incorporadas conforme desenvolvemos fornecedores que atendem ao nosso padrão.</p>
</section>

<!-- OPERAÇÃO -->
<section class="operacao" id="operacao">
  <div class="sec-tag reveal">Operação</div>
  <h2 class="reveal">Da Europa ao seu estoque.<br>Com responsabilidade em cada etapa.</h2>
  <p class="sub reveal">Quatro etapas. Uma operação integrada. Sem intermediários ocultos.</p>
  <div class="steps">
    <div class="step reveal">
      <span class="step-n">01</span>
      <h4>Seleção</h4>
      <p>Identificamos e desenvolvemos fornecedores europeus com produto de qualidade comprovada.</p>
      <span class="step-tag">Europa</span>
    </div>
    <div class="step reveal d1">
      <span class="step-n">02</span>
      <h4>Importação</h4>
      <p>Gerenciamos todo o processo: negociação, logística internacional e desembaraço no Brasil.</p>
      <span class="step-tag">Operação</span>
    </div>
    <div class="step reveal d2">
      <span class="step-n">03</span>
      <h4>Distribuição & Venda</h4>
      <p>Entregamos para atacadistas, restaurantes e empresas com fornecimento estruturado e pontos de venda próprios.</p>
      <span class="step-tag">Brasil</span>
    </div>
    <div class="step reveal d3">
      <span class="step-n">04</span>
      <h4>Expansão de Portfólio</h4>
      <p>Continuamos desenvolvendo novas categorias com o mesmo critério. O portfólio nunca para — mas nunca abre mão do padrão.</p>
      <span class="step-tag">Crescimento</span>
    </div>
  </div>
</section>

<!-- CONTATO -->
<section class="contato" id="contato">
  <div class="contato-txt reveal">
    <div class="sec-tag">Parceria</div>
    <h2>Quer distribuir produtos europeus <em>de qualidade?</em></h2>
    <p>Se você tem uma rede de distribuição, um restaurante, uma adega ou uma empresa que valoriza o que oferece ao cliente, vamos conversar.</p>
    <p class="note">A Fiducia Domus trabalha com parceiros que entendem que produto bom não precisa de argumento — precisa de acesso.</p>
  </div>
  <div class="reveal d2">
    <form class="cform" onsubmit="return false;">
      <div class="frow">
        <div class="fg"><label>Nome</label><input type="text" placeholder="Seu nome completo"></div>
        <div class="fg"><label>Empresa</label><input type="text" placeholder="Nome da empresa"></div>
      </div>
      <div class="frow">
        <div class="fg"><label>E-mail</label><input type="email" placeholder="contato@empresa.com.br"></div>
        <div class="fg"><label>Telefone</label><input type="tel" placeholder="(11) 00000-0000"></div>
      </div>
      <div class="fg">
        <label>Perfil</label>
        <select>
          <option value="" disabled selected>Como você se encaixa?</option>
          <option>Atacadista / Distribuidor</option>
          <option>Restaurante / Adega / Empório</option>
          <option>Rede varejista</option>
          <option>Empresa (outro segmento)</option>
        </select>
      </div>
      <div class="fg"><label>Mensagem</label><textarea rows="4" placeholder="Conte brevemente o que você está buscando..."></textarea></div>
      <button class="fbtn" type="submit">Enviar mensagem →</button>
    </form>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div style="display:flex;align-items:center;gap:.8rem;">
    <svg width="24" height="26" viewBox="0 0 100 110" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M50 4 L88 24 L88 68 Q88 92 50 106 Q12 92 12 68 L12 24 Z" fill="none" stroke="#FEF5EF" stroke-width="3.5" opacity="0.4"/>
      <path d="M38 38 L38 72 L53 72 Q67 72 67 55 Q67 38 53 38 Z" fill="none" stroke="#F5853F" stroke-width="3" stroke-linejoin="round"/>
    </svg>
    <div class="footer-brand">
      <span class="f">FIDUCIA</span>
      <span class="d">DOMUS</span>
    </div>
  </div>
  <p class="footer-copy">© 2024 Fiducia Domus. Importação & Distribuição Europeia.</p>
  <div class="footer-links">
    <a href="#quem-somos">Quem Somos</a>
    <a href="#portfolio">Portfólio</a>
    <a href="#contato">Contato</a>
  </div>
</footer>

<script>
// Nav scroll
const nav = document.getElementById('nav');
window.addEventListener('scroll', () => nav.classList.toggle('scrolled', scrollY > 60));

// Reveal on scroll
const els = document.querySelectorAll('.reveal');
const io = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); io.unobserve(e.target); } });
}, { threshold: 0.1, rootMargin: '0px 0px -40px 0px' });
els.forEach(el => io.observe(el));

// Smooth scroll
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    e.preventDefault();
    const t = document.querySelector(a.getAttribute('href'));
    if (t) t.scrollIntoView({ behavior: 'smooth', block: 'start' });
  });
});
</script>
</body>
</html>
