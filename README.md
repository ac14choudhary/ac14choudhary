<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Ayush Choudhary</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=IBM+Plex+Mono:wght@300;400;500&family=Lora:ital,wght@0,400;1,300&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:      #111110;
    --surface: #191917;
    --ink:     #e8e4dc;
    --muted:   #5a5850;
    --soft:    #8a8578;
    --accent:  #d4956a;
    --rule:    #222220;
    --serif:   'DM Serif Display', Georgia, serif;
    --mono:    'IBM Plex Mono', monospace;
    --lora:    'Lora', Georgia, serif;
  }

  html { font-size: 16px; }

  body {
    font-family: var(--mono);
    background: var(--bg);
    color: var(--ink);
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
  }

  .page {
    max-width: 720px;
    margin: 0 auto;
    padding: 80px 32px 100px;
  }

  .reveal {
    opacity: 0;
    transform: translateY(10px);
    animation: up 0.7s cubic-bezier(0.22,1,0.36,1) forwards;
  }
  @keyframes up {
    to { opacity: 1; transform: none; }
  }

  .masthead {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: end;
    gap: 24px;
    padding-bottom: 28px;
    border-bottom: 1px solid var(--ink);
  }

  .name {
    font-family: var(--serif);
    font-size: clamp(44px, 9vw, 80px);
    line-height: 0.92;
    letter-spacing: -0.02em;
    color: var(--ink);
  }

  .name em {
    font-style: italic;
    color: var(--accent);
  }

  .index-col { text-align: right; }

  .index-no {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    line-height: 2.2;
  }

  .index-no.live { color: var(--accent); }

  .meta-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 0;
    border-bottom: 1px solid var(--rule);
    flex-wrap: wrap;
    gap: 8px;
  }

  .meta-item {
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
  }

  .meta-item strong { color: var(--ink); font-weight: 500; }

  .byline {
    font-family: var(--lora);
    font-style: italic;
    font-size: 18px;
    color: var(--soft);
    font-weight: 300;
    padding: 28px 0 0;
    min-height: 30px;
  }

  .cursor { color: var(--accent); animation: blink 0.9s step-end infinite; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .roles {
    display: flex;
    flex-wrap: wrap;
    padding: 32px 0;
    border-bottom: 1px solid var(--rule);
  }

  .role {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 20px 10px 0;
    margin-right: 20px;
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--soft);
    position: relative;
    cursor: default;
    transition: color 0.2s;
  }

  .role::after {
    content: '';
    position: absolute;
    bottom: 8px; left: 0; right: 20px;
    height: 1px;
    background: var(--accent);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.35s cubic-bezier(0.22,1,0.36,1);
  }

  .role:hover { color: var(--ink); }
  .role:hover::after { transform: scaleX(1); }

  .role-num {
    font-size: 9px;
    color: var(--accent);
    font-weight: 500;
    letter-spacing: 0.1em;
    align-self: flex-start;
    padding-top: 1px;
  }

  .section {
    padding: 36px 0;
    border-bottom: 1px solid var(--rule);
  }

  .section-head {
    display: flex;
    align-items: baseline;
    gap: 16px;
    margin-bottom: 24px;
  }

  .section-title {
    font-size: 10px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--muted);
    flex-shrink: 0;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--rule);
  }

  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tech-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 7px 14px;
    border: 1px solid var(--rule);
    font-size: 11px;
    letter-spacing: 0.08em;
    color: var(--muted);
    transition: all 0.2s ease;
    cursor: default;
    text-decoration: none;
    font-family: var(--mono);
  }

  .tech-tag img {
    width: 14px; height: 14px;
    object-fit: contain;
    opacity: 0.4;
    transition: opacity 0.2s;
    filter: invert(1);
  }

  .tech-tag img.keep-color { filter: none; opacity: 0.5; }

  .tech-tag:hover {
    border-color: var(--soft);
    color: var(--ink);
  }
  .tech-tag:hover img { opacity: 0.85; }
  .tech-tag:hover img.keep-color { opacity: 1; }

  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .stat-card {
    border: 1px solid var(--rule);
    overflow: hidden;
    transition: border-color 0.2s;
    background: var(--surface);
  }

  .stat-card:hover { border-color: var(--soft); }
  .stat-card img { width: 100%; display: block; }
  .stat-wide { grid-column: 1 / -1; }

  .connect-list { display: flex; flex-direction: column; }

  .connect-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 15px 0;
    border-bottom: 1px solid var(--rule);
    text-decoration: none;
    color: var(--soft);
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .connect-item::before {
    content: '';
    position: absolute;
    left: -100%; top: 0; bottom: 0; width: 100%;
    background: var(--ink);
    transition: left 0.38s cubic-bezier(0.22,1,0.36,1);
    z-index: 0;
  }

  .connect-item:hover { color: var(--bg); }
  .connect-item:hover::before { left: 0; }

  .connect-item span,
  .connect-item svg { position: relative; z-index: 1; }

  .connect-item svg {
    width: 13px; height: 13px;
    stroke: currentColor;
    fill: none;
    stroke-width: 1.5;
    transition: transform 0.2s;
  }

  .connect-item:hover svg { transform: translate(3px, -3px); }

  .footer {
    padding-top: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
  }

  .footer-note {
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .footer-note a {
    color: var(--accent);
    text-decoration: none;
  }

  @media (max-width: 540px) {
    .masthead { grid-template-columns: 1fr; }
    .stats-grid { grid-template-columns: 1fr; }
    .stat-wide { grid-column: auto; }
    .role { margin-right: 8px; }
  }
</style>
</head>
<body>
<main class="page">

  <header class="masthead reveal" style="animation-delay:0s">
    <h1 class="name">Ayush<br><em>Choudhary</em></h1>
    <div class="index-col">
      <p class="index-no">ac14choudhary</p>
      <p class="index-no">Portfolio — 2025</p>
    </div>
  </header>

  <div class="meta-row reveal" style="animation-delay:0.07s">
    <span class="meta-item">Based in <strong>India</strong></span>
    <span class="meta-item">Design <strong>+</strong> Engineering</span>
    <span class="meta-item">
      <img src="https://komarev.com/ghpvc/?username=ac14choudhary&color=d4956a&style=flat-square&label=views" alt="views" style="height:18px;vertical-align:middle;"/>
    </span>
  </div>

  <p class="byline reveal" style="animation-delay:0.14s">
    <span id="typed"></span><span class="cursor">|</span>
  </p>

  <div class="roles reveal" style="animation-delay:0.21s">
    <div class="role"><span class="role-num">01</span>UI / UX Designer</div>
    <div class="role"><span class="role-num">02</span>Developer</div>
    <div class="role"><span class="role-num">03</span>Leader</div>
    <div class="role"><span class="role-num">04</span>VFX Designer</div>
  </div>

  <section class="section reveal" style="animation-delay:0.28s">
    <div class="section-head">
      <span class="section-title">Stack</span>
      <div class="section-line"></div>
    </div>
    <div class="tech-grid">
      <a class="tech-tag" href="https://www.cprogramming.com/" target="_blank">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt=""/> C
      </a>
      <a class="tech-tag" href="https://www.w3schools.com/cpp/" target="_blank">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt=""/> C++
      </a>
      <a class="tech-tag" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank">
        <img class="keep-color" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt=""/> JavaScript
      </a>
      <a class="tech-tag" href="https://reactnative.dev/" target="_blank">
        <img class="keep-color" src="https://reactnative.dev/img/header_logo.svg" alt=""/> React Native
      </a>
      <a class="tech-tag" href="https://redux.js.org" target="_blank">
        <img class="keep-color" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/redux/redux-original.svg" alt=""/> Redux
      </a>
      <a class="tech-tag" href="https://www.mysql.com/" target="_blank">
        <img class="keep-color" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt=""/> MySQL
      </a>
      <a class="tech-tag" href="https://www.figma.com/" target="_blank">
        <img class="keep-color" src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt=""/> Figma
      </a>
      <a class="tech-tag" href="https://www.adobe.com/products/xd.html" target="_blank">
        <img class="keep-color" src="https://cdn.worldvectorlogo.com/logos/adobe-xd.svg" alt=""/> Adobe XD
      </a>
      <a class="tech-tag" href="https://www.photoshop.com/en" target="_blank">
        <img class="keep-color" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt=""/> Photoshop
      </a>
      <a class="tech-tag" href="https://www.adobe.com/in/products/illustrator.html" target="_blank">
        <img class="keep-color" src="https://www.vectorlogo.zone/logos/adobe_illustrator/adobe_illustrator-icon.svg" alt=""/> Illustrator
      </a>
    </div>
  </section>

  <section class="section reveal" style="animation-delay:0.35s">
    <div class="section-head">
      <span class="section-title">GitHub</span>
      <div class="section-line"></div>
    </div>
    <div class="stats-grid">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=ac14choudhary&show_icons=true&hide_border=true&bg_color=191917&title_color=e8e4dc&icon_color=d4956a&text_color=5a5850&count_private=true" alt="stats"/>
      </div>
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ac14choudhary&layout=compact&hide_border=true&bg_color=191917&title_color=e8e4dc&text_color=5a5850" alt="languages"/>
      </div>
      <div class="stat-card stat-wide">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=ac14choudhary&hide_border=true&background=191917&ring=d4956a&fire=d4956a&currStreakLabel=e8e4dc&sideLabels=5a5850&dates=5a5850&stroke=222220" alt="streak"/>
      </div>
    </div>
  </section>

  <section class="section reveal" style="animation-delay:0.42s">
    <div class="section-head">
      <span class="section-title">Connect</span>
      <div class="section-line"></div>
    </div>
    <div class="connect-list">
      <a href="https://linkedin.com/in/ayush-choudhary-857244190" target="_blank" class="connect-item">
        <span>LinkedIn</span>
        <svg viewBox="0 0 24 24"><path d="M7 17L17 7M17 7H7M17 7v10" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </a>
      <a href="https://www.behance.net/ayushchoudhary4" target="_blank" class="connect-item">
        <span>Behance</span>
        <svg viewBox="0 0 24 24"><path d="M7 17L17 7M17 7H7M17 7v10" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </a>
      <a href="https://www.hackerrank.com/ra1811029010044" target="_blank" class="connect-item">
        <span>HackerRank</span>
        <svg viewBox="0 0 24 24"><path d="M7 17L17 7M17 7H7M17 7v10" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </a>
      <a href="https://instagram.com/ac14choudhary" target="_blank" class="connect-item">
        <span>Instagram</span>
        <svg viewBox="0 0 24 24"><path d="M7 17L17 7M17 7H7M17 7v10" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </a>
      <a href="mailto:choudharyayush891@gmail.com" class="connect-item">
        <span>choudharyayush891@gmail.com</span>
        <svg viewBox="0 0 24 24"><path d="M7 17L17 7M17 7H7M17 7v10" stroke-linecap="round" stroke-linejoin="round"/></svg>
      </a>
    </div>
  </section>

  <footer class="footer reveal" style="animation-delay:0.49s">
    <p class="footer-note">Designed &amp; built by <a href="https://github.com/ac14choudhary">Ayush Choudhary</a></p>
    <p class="footer-note">UI/UX · Dev · VFX — 2025</p>
  </footer>

</main>

<script>
  const lines = [
    'designing interfaces that breathe.',
    'writing code that speaks for itself.',
    'leading teams, building dreams.',
    'always learning, always shipping.'
  ];
  let li = 0, ci = 0, del = false;
  const el = document.getElementById('typed');
  function tick() {
    const cur = lines[li];
    el.textContent = del ? cur.slice(0, --ci) : cur.slice(0, ++ci);
    if (!del && ci === cur.length) { del = true; setTimeout(tick, 2200); return; }
    if (del && ci === 0) { del = false; li = (li + 1) % lines.length; }
    setTimeout(tick, del ? 35 : 65);
  }
  tick();
</script>
</body>
</html>
