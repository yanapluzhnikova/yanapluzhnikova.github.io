<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Яна Плужникова</title>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Geist:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #f8fafd;
    --white: #ffffff;
    --blue: #2563eb;
    --blue-light: #eff4ff;
    --blue-mid: #bfcfee;
    --text: #0f172a;
    --muted: #94a3b8;
    --border: #e2e9f5;
    --subtle: #f1f5fb;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Geist', sans-serif;
    font-weight: 300;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  .page {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 2rem 6rem;
  }

  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2rem 0;
    border-bottom: 1px solid var(--border);
  }

  .nav-logo {
    font-family: 'Instrument Serif', serif;
    font-size: 1.1rem;
    color: var(--blue);
  }

  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a { font-size: 0.8rem; color: var(--muted); text-decoration: none; letter-spacing: 0.03em; transition: color 0.2s; }
  .nav-links a:hover { color: var(--blue); }

  /* HERO */
  .hero { padding: 5rem 0 4rem; border-bottom: 1px solid var(--border); }

  .hero-eyebrow {
    font-size: 0.72rem; letter-spacing: 0.18em; text-transform: uppercase;
    color: var(--blue); margin-bottom: 1.5rem;
    opacity: 0; animation: up 0.6s 0.1s ease forwards;
  }

  .hero-name {
    font-family: 'Instrument Serif', serif;
    font-size: clamp(3rem, 7vw, 5.5rem);
    font-weight: 400; line-height: 1.05; letter-spacing: -0.02em;
    margin-bottom: 1.8rem;
    opacity: 0; animation: up 0.7s 0.25s ease forwards;
  }
  .hero-name span { color: var(--blue); font-style: italic; }

  .hero-desc {
    font-size: 1.05rem; color: #475569; max-width: 500px; line-height: 1.75; margin-bottom: 2.5rem;
    opacity: 0; animation: up 0.7s 0.4s ease forwards;
  }

  .hero-contacts {
    display: flex; flex-wrap: wrap; gap: 0.5rem;
    opacity: 0; animation: up 0.7s 0.55s ease forwards;
  }

  .chip {
    display: inline-flex; align-items: center; gap: 0.4rem;
    background: var(--white); border: 1px solid var(--border); color: #475569;
    padding: 0.35em 0.9em; font-size: 0.8rem; border-radius: 100px;
    text-decoration: none; transition: border-color 0.2s, color 0.2s;
  }
  .chip:hover { border-color: var(--blue); color: var(--blue); }
  .chip-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--blue); opacity: 0.5; }

  /* SECTIONS */
  section { padding: 4rem 0; border-bottom: 1px solid var(--border); }

  .sec-header { display: flex; align-items: center; gap: 1rem; margin-bottom: 2.5rem; }
  .sec-label { font-size: 0.68rem; letter-spacing: 0.2em; text-transform: uppercase; color: var(--blue); white-space: nowrap; }
  .sec-line { flex: 1; height: 1px; background: var(--border); }

  /* ABOUT */
  .about-cols { display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 4rem; align-items: start; }

  .about-text { font-family: 'Instrument Serif', serif; font-size: 1.25rem; line-height: 1.75; color: #1e293b; }
  .about-text em { color: var(--blue); font-style: italic; }

  .skills-wrap { margin-top: 2rem; }
  .mini-label { font-size: 0.65rem; letter-spacing: 0.18em; text-transform: uppercase; color: var(--muted); margin-bottom: 0.8rem; }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .stag { background: var(--blue-light); color: var(--blue); border: 1px solid var(--blue-mid); padding: 0.25em 0.75em; font-size: 0.78rem; border-radius: 4px; }

  .lang-rows { display: flex; flex-direction: column; }
  .lang-row { display: flex; justify-content: space-between; align-items: center; padding: 0.75rem 0; border-bottom: 1px solid var(--border); font-size: 0.9rem; }
  .lang-row:last-child { border-bottom: none; }
  .lang-level { font-size: 0.72rem; letter-spacing: 0.1em; text-transform: uppercase; color: var(--blue); background: var(--blue-light); padding: 0.2em 0.65em; border-radius: 100px; }

  /* EXPERIENCE */
  .exp-item { display: grid; grid-template-columns: 180px 1fr; gap: 2.5rem; padding: 2.2rem 0; border-bottom: 1px solid var(--border); }
  .exp-item:last-child { border-bottom: none; }

  .exp-period { font-size: 0.75rem; color: var(--muted); margin-bottom: 0.25rem; }
  .exp-company { font-size: 0.85rem; font-weight: 500; color: var(--blue); }
  .exp-role { font-family: 'Instrument Serif', serif; font-size: 1.2rem; margin-bottom: 0.2rem; line-height: 1.3; }
  .exp-sub { font-size: 0.78rem; color: var(--muted); margin-bottom: 1rem; }

  .exp-points { list-style: none; display: flex; flex-direction: column; gap: 0.45rem; }
  .exp-points li { font-size: 0.86rem; color: #475569; display: flex; gap: 0.6rem; line-height: 1.55; }
  .exp-points li::before { content: '·'; color: var(--blue); flex-shrink: 0; font-size: 1.1rem; line-height: 1.4; }

  /* EDUCATION */
  .edu-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 8px; overflow: hidden; margin-bottom: 2.5rem;
  }
  .edu-card { background: var(--white); padding: 1.8rem; transition: background 0.2s; }
  .edu-card:hover { background: var(--blue-light); }
  .edu-period { font-size: 0.7rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--blue); margin-bottom: 0.4rem; }
  .edu-place { font-family: 'Instrument Serif', serif; font-size: 1.05rem; margin-bottom: 0.3rem; }
  .edu-prog { font-size: 0.8rem; color: var(--muted); line-height: 1.5; }

  /* EXTRA EDUCATION */
  .extra-item { display: grid; grid-template-columns: 180px 1fr; gap: 2.5rem; padding: 1.6rem 0; border-bottom: 1px solid var(--border); }
  .extra-item:last-child { border-bottom: none; }
  .extra-period { font-size: 0.72rem; color: var(--muted); margin-bottom: 0.2rem; }
  .extra-org { font-size: 0.85rem; font-weight: 500; color: var(--blue); }
  .extra-course { font-weight: 500; font-size: 0.9rem; color: var(--text); margin-bottom: 0.3rem; }
  .extra-points { list-style: none; display: flex; flex-direction: column; gap: 0.3rem; margin-top: 0.4rem; }
  .extra-points li { font-size: 0.82rem; color: #475569; display: flex; gap: 0.5rem; line-height: 1.5; }
  .extra-points li::before { content: '·'; color: var(--blue); flex-shrink: 0; font-size: 1.1rem; line-height: 1.3; }

  /* CONFERENCES */
  .conf-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .conf-card { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 1.5rem; transition: border-color 0.2s, box-shadow 0.2s; }
  .conf-card:hover { border-color: var(--blue-mid); box-shadow: 0 4px 20px rgba(37,99,235,0.07); }
  .conf-year { font-size: 0.7rem; letter-spacing: 0.15em; text-transform: uppercase; color: var(--blue); margin-bottom: 0.5rem; }
  .conf-title { font-family: 'Instrument Serif', serif; font-size: 0.98rem; line-height: 1.5; margin-bottom: 0.4rem; }
  .conf-note { font-size: 0.76rem; color: var(--muted); }
  .conf-badge { display: inline-block; margin-top: 0.6rem; font-size: 0.68rem; background: var(--blue-light); color: var(--blue); padding: 0.2em 0.7em; border-radius: 100px; }

  /* VOLUNTEER */
  .vol-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; align-items: start; }
  .vol-block p { font-size: 0.88rem; color: #475569; line-height: 1.7; margin-bottom: 0.7rem; }
  .vol-block p:last-child { margin-bottom: 0; }

  .award-box { background: var(--blue-light); border: 1px solid var(--blue-mid); border-radius: 8px; padding: 1.4rem; display: flex; flex-direction: column; gap: 1rem; }
  .award-item { display: flex; gap: 0.8rem; align-items: flex-start; }
  .award-icon { font-size: 1.2rem; flex-shrink: 0; margin-top: 0.1rem; }
  .award-text { font-size: 0.84rem; color: #1e3a8a; line-height: 1.5; }

  /* FOOTER */
  footer { padding: 3rem 0 0; display: flex; justify-content: space-between; align-items: center; }
  .foot-name { font-family: 'Instrument Serif', serif; font-size: 1.1rem; }
  .foot-note { font-size: 0.78rem; color: var(--muted); }

  /* REVEAL */
  .reveal { opacity: 0; transform: translateY(18px); transition: opacity 0.55s ease, transform 0.55s ease; }
  .reveal.in { opacity: 1; transform: none; }

  @keyframes up { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: translateY(0); } }

  @media (max-width: 700px) {
    .about-cols, .edu-grid, .conf-grid, .vol-grid { grid-template-columns: 1fr; }
    .exp-item, .extra-item { grid-template-columns: 1fr; gap: 0.3rem; }
    .nav-links { display: none; }
    footer { flex-direction: column; gap: 0.5rem; text-align: center; }
  }
</style>
</head>
<body>
<div class="page">

  <nav>
    <div class="nav-logo">Яна Плужникова</div>
    <ul class="nav-links">
      <li><a href="#exp">Опыт</a></li>
      <li><a href="#edu">Образование</a></li>
      <li><a href="#conf">Конференции</a></li>
      <li><a href="#vol">Активности</a></li>
    </ul>
  </nav>

  <div class="hero">
    <div class="hero-eyebrow">Маркетинг · Аналитика · Продукт</div>
    <h1 class="hero-name">Яна<br><span>Плужникова</span></h1>
    <p class="hero-desc">Маркетинговый аналитик и контент-продюсер в Яндексе. Увлечена маркетингом, продуктовым менеджментом и межкультурной коммуникацией.</p>
    <div class="hero-contacts">
      <a href="tel:+79133784073" class="chip"><span class="chip-dot"></span>+7-913-378-40-73</a>
      <a href="mailto:pluga3@inbox.ru" class="chip"><span class="chip-dot"></span>pluga3@inbox.ru</a>
      <a href="https://t.me/yana_ply" class="chip"><span class="chip-dot"></span>@yana_ply</a>
      <span class="chip"><span class="chip-dot"></span>Москва</span>
    </div>
  </div>

  <!-- ABOUT -->
  <section>
    <div class="sec-header"><span class="sec-label">Обо мне</span><div class="sec-line"></div></div>
    <div class="about-cols reveal">
      <div>
        <p class="about-text">Открытость помогает мне <em>находить общий язык</em> с новыми людьми и вести команды к высоким результатам. Всегда рада развитию и освоению новых навыков.</p>
        <div class="skills-wrap">
          <div class="mini-label">Инструменты и навыки</div>
          <div class="skill-tags">
            <span class="stag">Excel / Word / PPT</span>
            <span class="stag">Python</span>
            <span class="stag">Figma</span>
            <span class="stag">Canva</span>
            <span class="stag">Capcut</span>
            <span class="stag">Tilda</span>
            <span class="stag">Unisender</span>
            <span class="stag">Маркетинговая аналитика</span>
            <span class="stag">SMM-стратегии</span>
            <span class="stag">Контент-продюсирование</span>
            <span class="stag">Data-driven подход</span>
          </div>
        </div>
      </div>
      <div>
        <div class="mini-label">Языки</div>
        <div class="lang-rows">
          <div class="lang-row"><span>Русский</span><span class="lang-level">Родной</span></div>
          <div class="lang-row"><span>Английский</span><span class="lang-level">C1</span></div>
          <div class="lang-row"><span>Французский</span><span class="lang-level">B1</span></div>
          <div class="lang-row"><span>Шведский</span><span class="lang-level">B1</span></div>
          <div class="lang-row"><span>Итальянский</span><span class="lang-level">A2</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- EXPERIENCE -->
  <section id="exp">
    <div class="sec-header"><span class="sec-label">Опыт работы</span><div class="sec-line"></div></div>

    <div class="exp-item reveal">
      <div><div class="exp-period">2025 — н.в.</div><div class="exp-company">Яндекс</div></div>
      <div>
        <div class="exp-role">Маркетинговый аналитик, контент-продюсер</div>
        <div class="exp-sub">HR-маркетинг и бренд работодателя</div>
        <ul class="exp-points">
          <li>Глубокий анализ аудитории Telegram-каналов и эффективности контента на основе метрик</li>
          <li>Тестирование гипотез для оптимизации форматов, времени публикации и вовлечённости</li>
          <li>Подготовка регулярных отчётов и дашбордов, формулировка data-driven рекомендаций</li>
          <li>Разработка и внедрение SMM-стратегий, планирование контент-планов</li>
          <li>Контроль полного цикла производства контента и координация команды</li>
        </ul>
      </div>
    </div>

    <div class="exp-item reveal">
      <div><div class="exp-period">2025</div><div class="exp-company">Formatta</div></div>
      <div>
        <div class="exp-role">Стажёр-маркетолог</div>
        <ul class="exp-points">
          <li>Написание текстов для соцсетей, создание и дизайн обложек</li>
          <li>Создание страниц сайта, презентаций, гайдов и чек-листов</li>
          <li>Создание email-рассылок</li>
        </ul>
      </div>
    </div>

    <div class="exp-item reveal">
      <div><div class="exp-period">2024 — н.в.</div><div class="exp-company">НИУ ВШЭ</div></div>
      <div>
        <div class="exp-role">Медиапродвижение Школы иностранных языков</div>
        <ul class="exp-points">
          <li>Написание вовлекающих текстов, адаптированных к цифровым платформам</li>
          <li>Поиск и создание визуальных материалов</li>
          <li>Создание контент-плана и согласование форматов с командой</li>
          <li>Исследование аналитических инструментов для повышения эффективности публикаций</li>
        </ul>
      </div>
    </div>

    <div class="exp-item reveal">
      <div><div class="exp-period">2023 — 2024</div><div class="exp-company">НИУ ВШЭ</div></div>
      <div>
        <div class="exp-role">Цифровой ассистент</div>
        <ul class="exp-points">
          <li>Адаптация упражнений для углублённого освоения тем</li>
          <li>Цифровизация учебного процесса и перенос модулей на e-learning платформы</li>
          <li>Техническая координация внедрения новых цифровых инструментов</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- EDUCATION -->
  <section id="edu">
    <div class="sec-header"><span class="sec-label">Образование</span><div class="sec-line"></div></div>
    <div class="edu-grid reveal">
      <div class="edu-card">
        <div class="edu-period">2022 — 2026</div>
        <div class="edu-place">НИУ Высшая школа экономики</div>
        <div class="edu-prog">Иностранные языки и межкультурная коммуникация · Москва</div>
      </div>
      <div class="edu-card">
        <div class="edu-period">Сент. 2024 — Февр. 2025</div>
        <div class="edu-place">Ca'Foscari University of Venice</div>
        <div class="edu-prog">Международная академическая мобильность · Венеция, Италия</div>
      </div>
    </div>

    <div class="sec-header"><span class="sec-label" style="color:var(--muted)">Дополнительное образование</span><div class="sec-line"></div></div>

    <div class="extra-item reveal">
      <div><div class="extra-period">2026</div><div class="extra-org">PM Club</div></div>
      <div><div class="extra-course">Курс «Проджект-менеджер 101»</div></div>
    </div>

    <div class="extra-item reveal">
      <div><div class="extra-period">2026</div><div class="extra-org">Центральный Университет</div></div>
      <div>
        <div class="extra-course">Интенсив «AI в Продакт-менеджменте»</div>
        <ul class="extra-points">
          <li>В составе команды за 2 дня разработала стратегию и MVP для AI-travel ассистента</li>
          <li>Провела и проанализировала глубинные интервью, сегментировала ЦА, заложила основы УТП</li>
          <li>Провела анализ рынка и построила конкурентную карту</li>
          <li>Реализовала запуск MVP в сжатые сроки</li>
        </ul>
      </div>
    </div>

    <div class="extra-item reveal">
      <div><div class="extra-period">2023 — 2025</div><div class="extra-org">НИУ ВШЭ</div></div>
      <div>
        <div class="extra-course">Майнор: Мировая экономика и международный бизнес</div>
        <ul class="extra-points">
          <li>Introduction to World Economy and Global Business Environment — оценка 10</li>
          <li>International Strategic Management — оценка 10</li>
          <li>International Marketing · Financial Decisions in International Companies</li>
        </ul>
      </div>
    </div>

    <div class="extra-item reveal">
      <div><div class="extra-period">2023 — н.в.</div><div class="extra-org">Нетология</div></div>
      <div>
        <div class="extra-course">Маркетинг & Продукт</div>
        <ul class="extra-points">
          <li>Маркетинговая воронка · Контент-менеджер · Основы интернет-маркетинга</li>
          <li>Product-менеджер: первые навыки · Менеджер бизнес-процессов</li>
        </ul>
      </div>
    </div>

    <div class="extra-item reveal">
      <div><div class="extra-period">2025</div><div class="extra-org">ВК / МГТУ / НИУ ВШЭ</div></div>
      <div>
        <div class="extra-course">Продакт, Digital & Data</div>
        <ul class="extra-points">
          <li>Профессия: Продакт-менеджер · Новые медиа: SMM и digital-маркетинг — ВК</li>
          <li>Системная аналитика — МГТУ им. Баумана</li>
          <li>Быстрое создание MVP в Data Science — НИУ ВШЭ, оценка 9</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- CONFERENCES -->
  <section id="conf">
    <div class="sec-header"><span class="sec-label">Конференции и публикации</span><div class="sec-line"></div></div>
    <div class="conf-grid reveal">
      <div class="conf-card">
        <div class="conf-year">2023</div>
        <div class="conf-title">Ономастическое пространство художественного текста: Переводческий аспект</div>
        <div class="conf-note">VIII межвузовская онлайн-конференция молодых учёных</div>
        <div class="conf-badge">🏆 Лучший доклад секции</div>
      </div>
      <div class="conf-card">
        <div class="conf-year">2024</div>
        <div class="conf-title">Influence de la culture française sur la russe moderne</div>
        <div class="conf-note">XIX Международная конференция «La France et la Francophonie»</div>
        <div class="conf-badge">🏆 Лучший доклад секции</div>
      </div>
      <div class="conf-card">
        <div class="conf-year">2025</div>
        <div class="conf-title">Marketing transnational: localisation linguoculturelle d'entreprises américaines en France</div>
        <div class="conf-note">XX Международная конференция «La France et la Francophonie»</div>
        <div class="conf-badge">🏆 Лучший доклад секции</div>
      </div>
      <div class="conf-card">
        <div class="conf-year">2025</div>
        <div class="conf-title">Оценка применимости модели культурных изменений Хофстеде в корпоративном пространстве</div>
        <div class="conf-note">XIII международная конференция молодых учёных</div>
        <div class="conf-badge">🏆 Лучший доклад секции</div>
      </div>
    </div>
  </section>

  <!-- VOLUNTEER -->
  <section id="vol">
    <div class="sec-header"><span class="sec-label">Волонтёрство и активности</span><div class="sec-line"></div></div>
    <div class="vol-grid reveal">
      <div class="vol-block">
        <p>С 2022 года участвую в волонтёрской деятельности НИУ ВШЭ: «День карьеры», конференция LED Conference, дни открытых дверей Школы иностранных языков, Олимпиада «Высшая проба».</p>
        <p>С 2023 года — куратор первокурсников: помогаю адаптироваться в университетской среде на протяжении всего учебного года.</p>
        <p>2022–2023 — Студенческий совет: решение дисциплинарных вопросов, помощь в организации мероприятий.</p>
      </div>
      <div>
        <div class="award-box">
          <div class="award-item">
            <span class="award-icon">🤺</span>
            <span class="award-text">Кандидат в мастера спорта по фехтованию на саблях</span>
          </div>
          <div class="award-item">
            <span class="award-icon">🎖</span>
            <span class="award-text">Благодарность от Школы Иностранных Языков НИУ ВШЭ за активное участие во внеучебной деятельности</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div>
      <div class="foot-name">Яна Плужникова</div>
      <div class="foot-note" style="margin-top:0.2rem">Открыта к новым возможностям</div>
    </div>
    <div class="foot-note">pluga3@inbox.ru · @yana_ply</div>
  </footer>

</div>

<script>
  const els = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); } });
  }, { threshold: 0.08, rootMargin: '0px 0px -30px 0px' });
  els.forEach(el => io.observe(el));
</script>
</body>
</html>
