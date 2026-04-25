<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Centre de Formation Mahombi Mbele</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,400&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --gold: #c9a84c;
      --gold-light: #e8d49a;
      --dark: #0d0d0d;
      --dark2: #1a1612;
      --cream: #f5f0e8;
      --text: #2a2318;
      --muted: #6b5d4a;
      --border: rgba(201,168,76,0.25);
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Jost', sans-serif;
      background: var(--dark);
      color: var(--cream);
      overflow-x: hidden;
    }

    /* ─── NAV ─── */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 100;
      padding: 1.2rem 3rem;
      display: flex; align-items: center; justify-content: space-between;
      background: rgba(13,13,13,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
      transition: all .3s;
    }
    .nav-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem; font-weight: 600; letter-spacing: .12em;
      color: var(--gold); text-transform: uppercase;
    }
    .nav-links { display: flex; gap: 2.5rem; list-style: none; }
    .nav-links a {
      color: var(--cream); text-decoration: none; font-size: .82rem;
      letter-spacing: .12em; text-transform: uppercase; font-weight: 500;
      opacity: .75; transition: opacity .2s, color .2s;
    }
    .nav-links a:hover { opacity: 1; color: var(--gold); }
    .nav-cta {
      background: transparent; border: 1px solid var(--gold);
      color: var(--gold); padding: .5rem 1.4rem; font-size: .8rem;
      letter-spacing: .12em; text-transform: uppercase; cursor: pointer;
      font-family: 'Jost', sans-serif; font-weight: 500;
      transition: background .25s, color .25s;
    }
    .nav-cta:hover { background: var(--gold); color: var(--dark); }

    /* hamburger */
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; }
    .hamburger span { width: 25px; height: 2px; background: var(--cream); transition: .3s; }

    /* ─── HERO ─── */
    #hero {
      min-height: 100vh;
      display: flex; flex-direction: column; align-items: center; justify-content: center;
      text-align: center; padding: 8rem 2rem 4rem;
      position: relative; overflow: hidden;
      background: var(--dark2);
    }
    #hero::before {
      content: '';
      position: absolute; inset: 0;
      background: radial-gradient(ellipse 80% 60% at 50% 30%, rgba(201,168,76,.12) 0%, transparent 70%);
      pointer-events: none;
    }
    .hero-ornament {
      width: 1px; height: 80px; background: linear-gradient(to bottom, transparent, var(--gold));
      margin: 0 auto 2.5rem;
      animation: fadeDown .8s ease both;
    }
    .hero-tag {
      font-size: .75rem; letter-spacing: .3em; text-transform: uppercase;
      color: var(--gold); font-weight: 500; margin-bottom: 1.5rem;
      animation: fadeUp .8s .2s ease both;
    }
    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2.8rem, 7vw, 6rem);
      font-weight: 300; line-height: 1.05;
      color: var(--cream); margin-bottom: 1.5rem;
      animation: fadeUp .9s .35s ease both;
    }
    .hero-title em { color: var(--gold); font-style: italic; }
    .hero-subtitle {
      font-size: clamp(1rem, 2vw, 1.35rem);
      font-family: 'Cormorant Garamond', serif; font-style: italic;
      color: var(--gold-light); margin-bottom: 2.5rem;
      animation: fadeUp .9s .5s ease both;
    }
    .hero-verse {
      font-size: .85rem; color: var(--muted); letter-spacing: .06em; margin-bottom: 3rem;
      max-width: 520px; line-height: 1.7;
      animation: fadeUp .9s .6s ease both;
    }
    .hero-verse strong { color: var(--gold-light); }
    .btn-primary {
      display: inline-block; background: var(--gold); color: var(--dark);
      padding: .9rem 2.8rem; font-size: .8rem; letter-spacing: .18em;
      text-transform: uppercase; text-decoration: none; font-weight: 600;
      font-family: 'Jost', sans-serif;
      transition: transform .2s, box-shadow .2s;
      animation: fadeUp .9s .75s ease both;
    }
    .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(201,168,76,.35); }

    /* ─── DIVIDER ─── */
    .section-divider {
      display: flex; align-items: center; gap: 1.5rem; margin: 0 auto 4rem;
      max-width: 200px; justify-content: center;
    }
    .section-divider::before, .section-divider::after {
      content: ''; flex: 1; height: 1px; background: var(--border);
    }
    .divider-diamond {
      width: 8px; height: 8px; background: var(--gold);
      transform: rotate(45deg); flex-shrink: 0;
    }

    /* ─── SECTIONS ─── */
    section { padding: 7rem 2rem; }
    .section-label {
      text-align: center; font-size: .72rem; letter-spacing: .3em;
      text-transform: uppercase; color: var(--gold); font-weight: 500;
      margin-bottom: 1rem;
    }
    .section-title {
      text-align: center;
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 4.5vw, 3.2rem);
      font-weight: 300; color: var(--cream); margin-bottom: 1rem;
    }
    .section-title em { color: var(--gold); font-style: italic; }

    /* ─── MISSION ─── */
    #mission { background: var(--dark); }
    .mission-grid {
      max-width: 1100px; margin: 0 auto;
      display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center;
    }
    .mission-text p {
      font-size: 1.05rem; line-height: 1.85; color: rgba(245,240,232,.75);
      margin-bottom: 1.5rem;
    }
    .mission-text .verse {
      border-left: 2px solid var(--gold); padding-left: 1.2rem;
      font-family: 'Cormorant Garamond', serif; font-style: italic;
      font-size: 1.1rem; color: var(--gold-light); line-height: 1.6;
    }
    .mission-image-frame {
      position: relative; aspect-ratio: 3/4; overflow: hidden;
    }
    .mission-image-frame img {
      width: 100%; height: 100%; object-fit: cover;
      filter: grayscale(30%) sepia(20%);
      transition: transform .6s ease;
    }
    .mission-image-frame:hover img { transform: scale(1.04); }
    .mission-image-frame::after {
      content: ''; position: absolute; inset: 0;
      background: linear-gradient(to top, rgba(13,13,13,.5) 0%, transparent 50%);
    }
    .mission-image-frame::before {
      content: ''; position: absolute;
      inset: 12px; border: 1px solid var(--border); z-index: 1; pointer-events: none;
    }

    /* placeholder image */
    .img-placeholder {
      width: 100%; height: 100%; background: var(--dark2);
      display: flex; align-items: center; justify-content: center;
      flex-direction: column; gap: .5rem; color: var(--muted);
      font-size: .75rem; letter-spacing: .1em; text-transform: uppercase;
    }
    .img-placeholder svg { width: 36px; opacity: .4; }

    /* ─── VISION ─── */
    #vision { background: var(--dark2); }
    .vision-content {
      max-width: 900px; margin: 0 auto; text-align: center;
    }
    .vision-content p {
      font-size: 1.1rem; line-height: 1.9; color: rgba(245,240,232,.78);
      margin-bottom: 2rem;
    }
    .vision-content .verse {
      border: 1px solid var(--border); padding: 1.8rem 2.5rem;
      font-family: 'Cormorant Garamond', serif; font-style: italic;
      font-size: 1.2rem; color: var(--gold-light); line-height: 1.7;
      display: inline-block;
    }
    .vision-image {
      max-width: 900px; margin: 3rem auto 0;
      aspect-ratio: 16/7; overflow: hidden; position: relative;
    }
    .vision-image img { width: 100%; height: 100%; object-fit: cover; filter: grayscale(20%) sepia(15%); }

    /* ─── EVENTS ─── */
    #events { background: var(--dark); }
    .events-grid {
      max-width: 1100px; margin: 0 auto;
      display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem;
    }
    .event-card {
      border: 1px solid var(--border); padding: 2.5rem;
      position: relative; overflow: hidden;
      transition: border-color .3s, transform .3s;
      cursor: pointer;
    }
    .event-card:hover { border-color: var(--gold); transform: translateY(-4px); }
    .event-card::before {
      content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(to right, transparent, var(--gold), transparent);
      transform: scaleX(0); transition: transform .3s;
    }
    .event-card:hover::before { transform: scaleX(1); }
    .event-number {
      font-family: 'Cormorant Garamond', serif;
      font-size: 3rem; font-weight: 300; color: var(--border);
      margin-bottom: .5rem; line-height: 1;
    }
    .event-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem; color: var(--cream); margin-bottom: .8rem;
    }
    .event-desc {
      font-size: .88rem; color: var(--muted); line-height: 1.7;
    }
    .event-link {
      display: inline-block; margin-top: 1.5rem;
      font-size: .75rem; letter-spacing: .15em; text-transform: uppercase;
      color: var(--gold); text-decoration: none; font-weight: 500;
      border-bottom: 1px solid transparent; transition: border-color .2s;
    }
    .event-link:hover { border-color: var(--gold); }

    /* ─── COMMUNITY TICKER ─── */
    .ticker-wrap {
      overflow: hidden; background: var(--gold); padding: .7rem 0;
    }
    .ticker-inner {
      display: flex; white-space: nowrap;
      animation: ticker 22s linear infinite;
    }
    .ticker-inner span {
      color: var(--dark); font-size: .78rem; letter-spacing: .15em;
      text-transform: uppercase; font-weight: 600; padding: 0 3rem;
    }
    .ticker-inner span::after { content: '✦'; padding-left: 3rem; }

    /* ─── CONTACT ─── */
    #contact { background: var(--dark2); }
    .contact-wrap {
      max-width: 1100px; margin: 0 auto;
      display: grid; grid-template-columns: 1fr 1.2fr; gap: 6rem; align-items: start;
    }
    .contact-info h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.8rem; font-weight: 300; color: var(--cream); margin-bottom: 2rem;
    }
    .contact-detail {
      display: flex; gap: 1rem; margin-bottom: 1.8rem; align-items: flex-start;
    }
    .contact-detail-icon {
      width: 32px; height: 32px; border: 1px solid var(--border);
      display: flex; align-items: center; justify-content: center; flex-shrink: 0;
    }
    .contact-detail-icon svg { width: 14px; stroke: var(--gold); fill: none; }
    .contact-detail-text p { font-size: .82rem; color: var(--muted); letter-spacing: .08em; text-transform: uppercase; margin-bottom: .25rem; }
    .contact-detail-text a, .contact-detail-text span {
      font-size: .95rem; color: var(--cream); text-decoration: none; line-height: 1.5;
    }
    .contact-detail-text a:hover { color: var(--gold); }

    /* form */
    .contact-form { display: flex; flex-direction: column; gap: 1.2rem; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }
    .form-group { display: flex; flex-direction: column; }
    .form-group label {
      font-size: .72rem; letter-spacing: .15em; text-transform: uppercase;
      color: var(--muted); margin-bottom: .5rem; font-weight: 500;
    }
    .form-group input, .form-group textarea, .form-group select {
      background: transparent; border: 1px solid var(--border);
      color: var(--cream); padding: .85rem 1rem; font-family: 'Jost', sans-serif;
      font-size: .9rem; outline: none; transition: border-color .25s;
      resize: none;
    }
    .form-group input:focus, .form-group textarea:focus, .form-group select:focus {
      border-color: var(--gold);
    }
    .form-group textarea { min-height: 120px; }
    .form-group select option { background: var(--dark2); }
    .btn-submit {
      background: var(--gold); color: var(--dark); border: none;
      padding: 1rem 2.5rem; font-size: .8rem; letter-spacing: .18em;
      text-transform: uppercase; font-family: 'Jost', sans-serif; font-weight: 600;
      cursor: pointer; align-self: flex-start;
      transition: transform .2s, box-shadow .2s;
    }
    .btn-submit:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(201,168,76,.35); }
    .form-success {
      display: none; background: rgba(201,168,76,.1); border: 1px solid var(--gold);
      padding: 1rem 1.5rem; font-size: .88rem; color: var(--gold-light);
      letter-spacing: .05em;
    }

    /* ─── FOOTER ─── */
    footer {
      background: var(--dark); border-top: 1px solid var(--border);
      padding: 4rem 2rem 2rem;
    }
    .footer-inner {
      max-width: 1100px; margin: 0 auto;
      display: grid; grid-template-columns: 1.5fr 1fr 1fr; gap: 3rem;
    }
    .footer-brand p {
      font-size: .85rem; color: var(--muted); line-height: 1.7; margin-top: 1rem; max-width: 280px;
    }
    .footer-heading {
      font-size: .72rem; letter-spacing: .25em; text-transform: uppercase;
      color: var(--gold); font-weight: 600; margin-bottom: 1.2rem;
    }
    .footer-links { list-style: none; }
    .footer-links li { margin-bottom: .7rem; }
    .footer-links a {
      color: var(--muted); text-decoration: none; font-size: .88rem;
      transition: color .2s;
    }
    .footer-links a:hover { color: var(--cream); }
    .footer-bottom {
      max-width: 1100px; margin: 3rem auto 0;
      padding-top: 1.5rem; border-top: 1px solid var(--border);
      display: flex; justify-content: space-between; align-items: center;
      font-size: .78rem; color: var(--muted);
    }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeDown {
      from { opacity: 0; transform: translateY(-20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes ticker {
      0%   { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }
    .reveal {
      opacity: 0; transform: translateY(30px);
      transition: opacity .7s ease, transform .7s ease;
    }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 900px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links, .nav-cta { display: none; }
      .hamburger { display: flex; }
      .nav-links.open {
        display: flex; flex-direction: column; position: fixed;
        top: 60px; left: 0; right: 0; background: var(--dark);
        padding: 2rem; gap: 1.5rem; border-bottom: 1px solid var(--border);
      }
      .mission-grid, .contact-wrap { grid-template-columns: 1fr; gap: 3rem; }
      .mission-image-frame { aspect-ratio: 4/3; order: -1; }
      .form-row { grid-template-columns: 1fr; }
      .footer-inner { grid-template-columns: 1fr; gap: 2rem; }
      .footer-bottom { flex-direction: column; gap: 1rem; text-align: center; }
    }
  </style>
</head>
<body>

<!-- ═══ NAV ═══ -->
<nav id="navbar">
  <div class="nav-logo">KAM · Centre de Formation</div>
  <ul class="nav-links" id="navLinks">
    <li><a href="#mission">Mission</a></li>
    <li><a href="#vision">Vision</a></li>
    <li><a href="#events">Événements</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <button class="nav-cta" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">S'inscrire</button>
  <div class="hamburger" id="hamburger" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- ═══ HERO ═══ -->
<section id="hero">
  <div class="hero-ornament"></div>
  <p class="hero-tag">Lubumbashi · République Démocratique du Congo</p>
  <h1 class="hero-title">CENTRE DE FORMATION<br><em>Mahombi Mbele</em></h1>
  <p class="hero-subtitle">Transformez votre vie chrétienne ici</p>
  <p class="hero-verse">
    Objectif : Produire des hommes spirituels aptes à transporter la zoé (la vie de Dieu)<br>
    dans tous les plans de la société.<br><br>
    <strong>Mission :</strong> Faire des disciples au moyen de la parole de vérité et de l'enseignement de l'évangile.
  </p>
  <a href="#events" class="btn-primary">Voir les événements</a>
</section>

<!-- ═══ MISSION ═══ -->
<section id="mission">
  <p class="section-label reveal">Notre fondation</p>
  <h2 class="section-title reveal">Notre <em>Mission</em></h2>
  <div class="section-divider reveal"><div class="divider-diamond"></div></div>

  <div class="mission-grid">
    <div class="mission-text reveal">
      <p>Faire des disciples au moyen de la parole de vérité et de l'enseignement de l'évangile est au cœur de tout ce que nous faisons. Chaque programme, chaque rencontre est conçu pour équiper les croyants à vivre pleinement leur foi.</p>
      <p>Nous croyons que chaque individu est appelé à porter la vie de Dieu — la zoé — dans toutes les sphères de la société : la famille, le travail, la culture et la communauté.</p>
      <p class="verse">
        « Allez, faites de toutes les nations des disciples, les baptisant au nom du Père, du Fils et du Saint-Esprit. »<br>
        <strong style="font-size:.85rem; letter-spacing:.08em;">— Matthieu 28 : 19</strong>
      </p>
    </div>
    <div class="mission-image-frame reveal">
      <!-- Remplacez ce bloc par votre image : <img src="images/mission.jpg" alt="Mission"> -->
      <div class="img-placeholder">
        <svg viewBox="0 0 24 24" stroke="currentColor" stroke-width="1"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="M21 15l-5-5L5 21"/></svg>
        <span>Ajoutez votre image ici</span>
        <span style="font-size:.65rem; opacity:.6">images/mission.jpg</span>
      </div>
    </div>
  </div>
</section>

<!-- ═══ VISION ═══ -->
<section id="vision">
  <p class="section-label reveal">Notre ambition</p>
  <h2 class="section-title reveal">Une <em>Vision</em> pour votre vie chrétienne</h2>
  <div class="section-divider reveal"><div class="divider-diamond"></div></div>

  <div class="vision-content reveal">
    <p>Atteindre la maturité, c'est-à-dire l'état mûr de notre homme intérieur, ce qui se traduit par l'unité de la foi, la connaissance parfaite du Christ et parvenir à une personnalité épanouie suivant le modèle parfait : <strong style="color:var(--gold-light)">le Christ.</strong></p>
    <div class="verse">
      « Pour le perfectionnement des saints en vue de l'œuvre du ministère<br>
      et de l'édification du corps de Christ. »<br>
      <strong style="font-size:.85rem; letter-spacing:.08em; font-style:normal;">— Éphésiens 4 : 12</strong>
    </div>
  </div>

  <div class="vision-image reveal">
    <!-- Remplacez par votre image : <img src="images/vision.jpg" alt="Vision"> -->
    <div class="img-placeholder" style="height:100%">
      <svg viewBox="0 0 24 24" stroke="currentColor" stroke-width="1"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="8.5" cy="8.5" r="1.5"/><path d="M21 15l-5-5L5 21"/></svg>
      <span>Ajoutez votre image ici</span>
      <span style="font-size:.65rem; opacity:.6">images/vision.jpg</span>
    </div>
  </div>
</section>

<!-- ═══ TICKER ═══ -->
<div class="ticker-wrap">
  <div class="ticker-inner">
    <span>Bienvenue dans la communauté Mahombi Mbele</span>
    <span>Bienvenue dans la communauté Mahombi Mbele</span>
    <span>Bienvenue dans la communauté Mahombi Mbele</span>
    <span>Bienvenue dans la communauté Mahombi Mbele</span>
    <span>Bienvenue dans la communauté Mahombi Mbele</span>
    <span>Bienvenue dans la communauté Mahombi Mbele</span>
  </div>
</div>

<!-- ═══ EVENTS ═══ -->
<section id="events">
  <p class="section-label reveal">Rejoignez-nous</p>
  <h2 class="section-title reveal">Nos <em>Événements</em></h2>
  <div class="section-divider reveal"><div class="divider-diamond"></div></div>

  <div class="events-grid">
    <div class="event-card reveal">
      <div class="event-number">01</div>
      <h3 class="event-title">Formation & Enseignement</h3>
      <p class="event-desc">Des sessions d'enseignement biblique approfondies pour équiper chaque croyant dans sa marche avec Dieu et sa compréhension des Écritures.</p>
      <a href="#contact" class="event-link">S'inscrire →</a>
    </div>
    <div class="event-card reveal">
      <div class="event-number">02</div>
      <h3 class="event-title">Réunions de Communauté</h3>
      <p class="event-desc">Des moments de rencontre, de prière et de partage pour grandir ensemble dans la foi et la fraternité chrétienne.</p>
      <a href="#contact" class="event-link">Rejoindre →</a>
    </div>
    <div class="event-card reveal">
      <div class="event-number">03</div>
      <h3 class="event-title">Conférences Spéciales</h3>
      <p class="event-desc">Des événements ponctuels avec des intervenants invités pour approfondir des thématiques spirituelles et doctrinales essentielles.</p>
      <a href="#contact" class="event-link">En savoir plus →</a>
    </div>
  </div>
</section>

<!-- ═══ CONTACT ═══ -->
<section id="contact">
  <p class="section-label reveal">Faites partie de notre famille</p>
  <h2 class="section-title reveal">Nous <em>Contacter</em></h2>
  <div class="section-divider reveal"><div class="divider-diamond"></div></div>

  <div class="contact-wrap">
    <div class="contact-info reveal">
      <h3>Venez nous rejoindre</h3>

      <div class="contact-detail">
        <div class="contact-detail-icon">
          <svg viewBox="0 0 24 24" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
        </div>
        <div class="contact-detail-text">
          <p>Email</p>
          <a href="mailto:mahombimbele@gmail.com">mahombimbele@gmail.com</a>
        </div>
      </div>

      <div class="contact-detail">
        <div class="contact-detail-icon">
          <svg viewBox="0 0 24 24" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/></svg>
        </div>
        <div class="contact-detail-text">
          <p>Téléphone</p>
          <a href="tel:+243996884060">+243 996 884 060</a>
        </div>
      </div>

      <div class="contact-detail">
        <div class="contact-detail-icon">
          <svg viewBox="0 0 24 24" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><circle cx="12" cy="11" r="3"/></svg>
        </div>
        <div class="contact-detail-text">
          <p>Adresse</p>
          <span>Nº47C Avenue des Étoiles, Quartier Kalubwe<br>Commune Lubumbashi, RDC<br>Réf. Temple Mahombi Mbele</span>
        </div>
      </div>
    </div>

    <div class="reveal">
      <form class="contact-form" onsubmit="submitForm(event)">
        <div class="form-row">
          <div class="form-group">
            <label>Prénom *</label>
            <input type="text" required placeholder="Votre prénom">
          </div>
          <div class="form-group">
            <label>Nom *</label>
            <input type="text" required placeholder="Votre nom">
          </div>
        </div>
        <div class="form-group">
          <label>Email *</label>
          <input type="email" required placeholder="votre@email.com">
        </div>
        <div class="form-group">
          <label>Sujet *</label>
          <select required>
            <option value="" disabled selected>Choisissez un sujet</option>
            <option>Inscription à une formation</option>
            <option>Renseignements généraux</option>
            <option>Événements</option>
            <option>Autre</option>
          </select>
        </div>
        <div class="form-group">
          <label>Message *</label>
          <textarea required placeholder="Votre message..."></textarea>
        </div>
        <button type="submit" class="btn-submit">Envoyer le message</button>
        <div class="form-success" id="formSuccess">
          ✓ Votre message a bien été envoyé. Nous vous répondrons rapidement.
        </div>
      </form>
    </div>
  </div>
</section>

<!-- ═══ FOOTER ═══ -->
<footer>
  <div class="footer-inner">
    <div class="footer-brand">
      <div class="nav-logo">KAM · Centre de Formation</div>
      <p>Transformez votre vie chrétienne ici. Centre de Formation Mahombi Mbele — Lubumbashi, RDC.</p>
    </div>
    <div>
      <p class="footer-heading">Navigation</p>
      <ul class="footer-links">
        <li><a href="#hero">Accueil</a></li>
        <li><a href="#mission">Mission</a></li>
        <li><a href="#vision">Vision</a></li>
        <li><a href="#events">Événements</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
    <div>
      <p class="footer-heading">Contact</p>
      <ul class="footer-links">
        <li><a href="mailto:mahombimbele@gmail.com">mahombimbele@gmail.com</a></li>
        <li><a href="tel:+243996884060">+243 996 884 060</a></li>
        <li><a href="#contact">Nº47C Avenue des Étoiles,<br>Lubumbashi, RDC</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 Centre de Formation Mahombi Mbele. Tous droits réservés.</span>
    <span style="color:var(--border)">✦</span>
  </div>
</footer>

<script>
  // Hamburger
  function toggleMenu() {
    document.getElementById('navLinks').classList.toggle('open');
  }

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
  }, { threshold: 0.12 });
  reveals.forEach(r => obs.observe(r));

  // Navbar scroll
  window.addEventListener('scroll', () => {
    document.getElementById('navbar').style.boxShadow = window.scrollY > 30 ? '0 4px 30px rgba(0,0,0,.4)' : '';
  });

  // Form submit
  function submitForm(e) {
    e.preventDefault();
    const s = document.getElementById('formSuccess');
    s.style.display = 'block';
    e.target.reset();
    setTimeout(() => s.style.display = 'none', 6000);
  }
</script>
</body>
</html>
