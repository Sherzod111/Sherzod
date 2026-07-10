!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yaqeen Group — Ishonchli qurilish</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1b2430;
    --ink-soft: #2c3648;
    --paper: #ede9e2;
    --paper-soft: #f5f3ee;
    --gold: #c89b3c;
    --steel: #3c5b6f;
    --line: rgba(27,36,48,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--paper);
    color: var(--ink);
    font-family: 'Inter', sans-serif;
    overflow-x: hidden;
  }

  .display {
    font-family: 'Space Grotesk', sans-serif;
    letter-spacing: -0.01em;
  }

  a { color: inherit; }

  /* ===== NAV ===== */
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 22px 6%;
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    background: rgba(237,233,226,0.9);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--line);
  }

  .logo {
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 700;
    font-size: 20px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .logo .mark {
    width: 10px; height: 10px;
    background: var(--gold);
  }

  .nav-links { display: flex; align-items: center; }
  nav a.nav-link {
    text-decoration: none;
    font-weight: 500;
    font-size: 14px;
    margin-left: 30px;
  }
  .nav-cta {
    background: var(--ink);
    color: var(--paper) !important;
    padding: 10px 20px;
    font-size: 13px;
    font-weight: 600;
    margin-left: 30px;
  }

  @media (max-width: 820px) {
    nav a.nav-link:not(.nav-cta) { display: none; }
  }

  /* ===== HERO ===== */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 6%;
    position: relative;
    background-image:
      linear-gradient(var(--line) 1px, transparent 1px),
      linear-gradient(90deg, var(--line) 1px, transparent 1px);
    background-size: 48px 48px;
  }

  .plot-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    border: 1px dashed var(--steel);
    padding: 6px 14px;
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.06em;
    color: var(--steel);
    width: fit-content;
    margin-bottom: 24px;
  }
  .plot-tag::before { content: "◆"; color: var(--gold); }

  .hero h1 {
    font-size: clamp(40px, 7.5vw, 96px);
    line-height: 1.02;
    font-weight: 700;
    max-width: 900px;
  }
  .hero h1 em {
    font-style: normal;
    color: var(--gold);
  }

  .hero p {
    max-width: 520px;
    color: var(--ink-soft);
    font-size: 18px;
    line-height: 1.6;
    margin: 24px 0 36px;
  }

  .btn-row { display: flex; gap: 16px; flex-wrap: wrap; }
  .btn {
    font-weight: 600;
    font-size: 14px;
    padding: 15px 30px;
    text-decoration: none;
    display: inline-block;
    transition: transform 0.2s ease, background 0.2s ease;
  }
  .btn:hover { transform: translateY(-2px); }
  .btn-primary { background: var(--ink); color: var(--paper); }
  .btn-ghost { border: 1px solid var(--ink); color: var(--ink); }

  /* ===== STRIP STATS ===== */
  .strip {
    display: flex;
    flex-wrap: wrap;
    border-top: 1px solid var(--line);
    border-bottom: 1px solid var(--line);
  }
  .strip-item {
    flex: 1;
    min-width: 160px;
    padding: 28px 6%;
    border-right: 1px solid var(--line);
  }
  .strip-item:last-child { border-right: none; }
  .strip-item h3 {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 32px;
    color: var(--gold);
  }
  .strip-item p {
    font-size: 13px;
    color: var(--ink-soft);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    font-weight: 600;
    margin-top: 4px;
  }

  /* ===== SECTION SHARED ===== */
  section { padding: 100px 6%; }
  .section-head {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 48px;
    flex-wrap: wrap;
    gap: 16px;
  }
  .eyebrow {
    color: var(--gold);
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .section-title {
    font-size: clamp(28px, 4.5vw, 48px);
    font-weight: 700;
  }
  .section-sub { color: var(--ink-soft); max-width: 460px; }

  /* ===== PROJECTS (uylar) ===== */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
  }
  .project-card {
    background: var(--paper-soft);
    border: 1px solid var(--line);
    padding: 28px;
  }
  .project-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 18px;
  }
  .plot-num {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 12px;
    font-weight: 700;
    color: var(--steel);
    border: 1px dashed var(--steel);
    padding: 4px 10px;
  }
  .status-tag {
    font-size: 12px;
    font-weight: 700;
    color: var(--gold);
  }
  .project-card h3 {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 22px;
    margin-bottom: 8px;
  }
  .project-card p {
    color: var(--ink-soft);
    font-size: 14px;
    margin-bottom: 20px;
  }
  .progress-track {
    height: 6px;
    background: var(--line);
    position: relative;
  }
  .progress-fill {
    height: 100%;
    background: var(--gold);
  }
  .progress-label {
    display: flex;
    justify-content: space-between;
    font-size: 12px;
    color: var(--ink-soft);
    margin-top: 8px;
    font-weight: 600;
  }

  /* ===== YAQEEN SHAHARCHASI (featured) ===== */
  .feature {
    background: var(--ink);
    color: var(--paper);
    padding: 100px 6%;
    position: relative;
    overflow: hidden;
  }
  .feature::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(237,233,226,0.06) 1px, transparent 1px),
      linear-gradient(90deg, rgba(237,233,226,0.06) 1px, transparent 1px);
    background-size: 60px 60px;
  }
  .feature-inner { position: relative; z-index: 2; max-width: 640px; }
  .feature .eyebrow { color: var(--gold); }
  .feature h2 {
    font-family: 'Space Grotesk', sans-serif;
    font-size: clamp(32px, 6vw, 64px);
    font-weight: 700;
    line-height: 1.05;
    margin-bottom: 20px;
  }
  .feature p {
    color: #c9cdd4;
    font-size: 17px;
    line-height: 1.7;
    margin-bottom: 32px;
  }
  .feature-stats {
    display: flex;
    gap: 40px;
    margin-bottom: 36px;
    flex-wrap: wrap;
  }
  .feature-stats div h4 {
    font-family: 'Space Grotesk', sans-serif;
    color: var(--gold);
    font-size: 26px;
  }
  .feature-stats div p {
    color: #9aa0ab;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    margin: 0;
  }
  .feature .btn-primary { background: var(--gold); color: var(--ink); }

  /* ===== NEWS ===== */
  .news-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1px;
    background: var(--line);
    border: 1px solid var(--line);
  }
  .news-card {
    background: var(--paper-soft);
    padding: 26px;
  }
  .news-date {
    font-size: 12px;
    font-weight: 700;
    color: var(--steel);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 10px;
  }
  .news-card h3 {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 19px;
    margin-bottom: 8px;
    line-height: 1.3;
  }
  .news-card p { color: var(--ink-soft); font-size: 14px; }

  /* ===== KONKURSLAR ===== */
  .contest-box {
    border: 1px dashed var(--steel);
    padding: 48px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 24px;
    flex-wrap: wrap;
  }
  .contest-box h3 {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 26px;
    margin-bottom: 10px;
  }
  .contest-box p { color: var(--ink-soft); max-width: 420px; }

  /* ===== FOOTER ===== */
  footer {
    background: var(--ink);
    color: #9aa0ab;
    padding: 48px 6% 28px;
  }
  .footer-top {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 32px;
    padding-bottom: 32px;
    border-bottom: 1px solid rgba(237,233,226,0.1);
    margin-bottom: 20px;
  }
  .footer-top .logo { color: var(--paper); }
  footer .cols { display: flex; gap: 60px; flex-wrap: wrap; }
  footer .cols h5 {
    color: var(--paper);
    font-size: 13px;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 14px;
  }
  footer .cols a { display: block; font-size: 14px; margin-bottom: 8px; text-decoration: none; color: #9aa0ab; }
  .footer-bottom { display: flex; justify-content: space-between; font-size: 13px; flex-wrap: wrap; gap: 8px; }
</style>
</head>
<body>

<nav>
  <div class="logo"><span class="mark"></span>YAQEEN GROUP</div>
  <div class="nav-links">
    <a class="nav-link" href="#loyihalar">Loyihalar</a>
    <a class="nav-link" href="#shaharcha">Yaqeen Shaharchasi</a>
    <a class="nav-link" href="#yangiliklar">Yangiliklar</a>
    <a class="nav-link" href="#konkurs">Konkurslar</a>
    <a class="nav-link nav-cta" href="#aloqa">Bog'lanish</a>
  </div>
</nav>

<section class="hero">
  <div class="plot-tag">ANDIJON VILOYATI · 2009 YILDAN BUYON</div>
  <h1 class="display">Ishonchli devor —<br><em>Yaqeen</em> imzosi bilan</h1>
  <p>Andijonda zamonaviy turar-joy majmualarini quramiz va Bobur shahrida yangi "Yaqeen shaharchasi" loyihasini amalga oshirmoqdamiz. Har bir uchastka — rejalashtirilgan, nazorat qilingan va shaffof.</p>
  <div class="btn-row">
    <a href="#loyihalar" class="btn btn-primary">Qurilayotgan uylarni ko'rish</a>
    <a href="#shaharcha" class="btn btn-ghost">Yaqeen Shaharchasi haqida</a>
  </div>
</section>

<div class="strip">
  <div class="strip-item"><h3>17</h3><p>Faol loyiha</p></div>
  <div class="strip-item"><h3>340+</h3><p>Topshirilgan uy</p></div>
  <div class="strip-item"><h3>16</h3><p>Yillik tajriba</p></div>
  <div class="strip-item"><h3>1</h3><p>Yangi shaharcha</p></div>
</div>

<section id="loyihalar">
  <div class="section-head">
    <div>
      <div class="eyebrow">Joriy qurilishlar</div>
      <div class="section-title display">Andijonda qurilayotgan uylar</div>
    </div>
    <p class="section-sub">Har bir loyiha bosqichi haqida real vaqtda ma'lumot beramiz — yashirin kechikish yo'q.</p>
  </div>

  <div class="projects-grid">
    <div class="project-card">
      <div class="project-top">
        <span class="plot-num">UCH-014</span>
        <span class="status-tag">QURILMOQDA</span>
      </div>
      <h3 class="display">Bog'ishamol massivi</h3>
      <p>48 xonadonli, 4 qavatli turar-joy binosi. Markazga yaqin joylashuv.</p>
      <div class="progress-track"><div class="progress-fill" style="width:68%"></div></div>
      <div class="progress-label"><span>Bajarildi</span><span>68%</span></div>
    </div>

    <div class="project-card">
      <div class="project-top">
        <span class="plot-num">UCH-021</span>
        <span class="status-tag">QURILMOQDA</span>
      </div>
      <h3 class="display">Marg'ilon ko'chasi uylari</h3>
      <p>Xususiy hovlili, 2 qavatli 12 ta uy majmuasi.</p>
      <div class="progress-track"><div class="progress-fill" style="width:42%"></div></div>
      <div class="progress-label"><span>Bajarildi</span><span>42%</span></div>
    </div>

    <div class="project-card">
      <div class="project-top">
        <span class="plot-num">UCH-009</span>
        <span class="status-tag" style="color:var(--steel)">TOPSHIRILDI</span>
      </div>
      <h3 class="display">Namuna turar-joy majmuasi</h3>
      <p>60 xonadonli majmua, barcha xonadonlar sotilgan.</p>
      <div class="progress-track"><div class="progress-fill" style="width:100%"></div></div>
      <div class="progress-label"><span>Bajarildi</span><span>100%</span></div>
    </div>
  </div>
</section>

<section class="feature" id="shaharcha">
  <div class="feature-inner">
    <div class="eyebrow">Yangi loyiha</div>
    <h2 class="display">Yaqeen Shaharchasi, Bobur shahri</h2>
    <p>Bobur shahrida qurilishi rejalashtirilgan yangi zamonaviy shaharcha — maktab, bog'cha, park va savdo maydonchalari bilan to'liq jihozlangan yashash muhiti. Loyiha bosqichma-bosqich amalga oshiriladi, har bir bosqich haqida saytimizda yangilanib boriladi.</p>
    <div class="feature-stats">
      <div><h4>1200</h4><p>Rejalashtirilgan uy</p></div>
      <div><h4>3</h4><p>Qurilish bosqichi</p></div>
      <div><h4>2027</h4><p>1-bosqich topshirish</p></div>
    </div>
    <a href="#" class="btn btn-primary">Loyiha rejasini ko'rish</a>
  </div>
</section>

<section id="yangiliklar">
  <div class="section-head">
    <div>
      <div class="eyebrow">Yangiliklar</div>
      <div class="section-title display">So'nggi yangilanishlar</div>
    </div>
    <p class="section-sub">Qurilish jarayoni va kompaniya yangiliklaridan xabardor bo'ling.</p>
  </div>

  <div class="news-grid">
    <div class="news-card">
      <div class="news-date">2026-yil, 3-iyul</div>
      <h3 class="display">Yaqeen Shaharchasi 1-bosqichi uchun yer ishlari boshlandi</h3>
      <p>Bobur shahridagi maydonda dastlabki tayyorgarlik ishlari yakunlandi.</p>
    </div>
    <div class="news-card">
      <div class="news-date">2026-yil, 22-iyun</div>
      <h3 class="display">Bog'ishamol massividagi bino qurilishi 68% ga yetdi</h3>
      <p>Fasad ishlari boshlanadi, topshirish muddati o'zgarishsiz qoladi.</p>
    </div>
    <div class="news-card">
      <div class="news-date">2026-yil, 10-iyun</div>
      <h3 class="display">Yangi bo'lib-to'lash shartlari joriy qilindi</h3>
      <p>Mijozlar uchun 24 oygacha muddatli to'lov imkoniyati qo'shildi.</p>
    </div>
  </div>
</section>

<section id="konkurs">
  <div class="section-head">
    <div>
      <div class="eyebrow">Konkurslar</div>
      <div class="section-title display">Faol tanlovlar</div>
    </div>
  </div>

  <div class="contest-box">
    <div>
      <h3 class="display">"Eng yaxshi hovli dizayni" tanlovi</h3>
      <p>Yaqeen shaharchasi uchun hovli dizayni g'oyasini yuboring — g'olib g'oya loyihada qo'llaniladi va sovrin beriladi.</p>
    </div>
    <a href="#" class="btn btn-primary">Tanlovga qatnashish</a>
  </div>
</section>

<section id="aloqa" style="padding-top:0">
  <div class="contest-box" style="border-color: var(--gold)">
    <div>
      <h3 class="display">Savolingiz bormi?</h3>
      <p>Uy tanlash yoki uchastka bron qilish bo'yicha mutaxassislarimiz bilan bog'laning.</p>
    </div>
    <a href="tel:+998712001122" class="btn btn-primary">+998 71 200 11 22</a>
  </div>
</section>

<footer>
  <div class="footer-top">
    <div class="logo"><span class="mark"></span>YAQEEN GROUP</div>
    <div class="cols">
      <div>
        <h5>Sahifalar</h5>
        <a href="#loyihalar">Loyihalar</a>
        <a href="#shaharcha">Yaqeen Shaharchasi</a>
        <a href="#yangiliklar">Yangiliklar</a>
        <a href="#konkurs">Konkurslar</a>
      </div>
      <div>
        <h5>Aloqa</h5>
        <a href="tel:+998712001122">+998 71 200 11 22</a>
        <a href="mailto:info@yaqeen.uz">info@yaqeen.uz</a>
        <a href="#">Andijon shahri, Bobur shoh ko'chasi</a>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 Yaqeen Group. Barcha huquqlar himoyalangan.</span>
    <span>ИНН 310892563</span>
  </div>
</footer>

</body>
</html>