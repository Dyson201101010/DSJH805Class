<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>DSJH 705 班級網站</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Noto Sans TC', sans-serif;
      margin: 0;
      padding: 0;
      scroll-behavior: smooth;
    }

    body {
      background-image: url('https://images.unsplash.com/photo-1506744038136-46273834b3fb');
      background-size: cover;
      background-position: center;
      min-height: 100vh;
      color: #333;
    }

    header {
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      background-color: rgba(255, 255, 255, 0.3);
      border-radius: 16px;
      border: 1px solid rgba(255, 255, 255, 0.125);
      text-align: center;
      padding: 2rem;
      margin: 2rem;
      color: #000;
    }

    h1 {
      font-size: 2.5rem;
    }

    .section {
      max-width: 800px;
      margin: 4rem auto;
      background: rgba(255, 255, 255, 0.85);
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      opacity: 0;
      transform: translateY(50px);
      transition: all 1s ease;
    }

    .section.visible {
      opacity: 1;
      transform: translateY(0);
    }

    footer {
      text-align: center;
      padding: 2rem;
      background-color: rgba(255,255,255,0.8);
      font-size: 0.9rem;
      margin-top: 2rem;
    }

    .lang-switcher {
      background: rgba(255,255,255,0.8);
      padding: 0.5rem 1rem;
      border-radius: 8px;
      cursor: pointer;
      display: inline-block;
      margin-top: 1rem;
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title">DSJH 705 班級網站</h1>
  </header>

  <section class="section" id="leaders">
    <h2>班級幹部 / Class Leaders</h2>
    <ul>
      <li>班長 / Class Leader: 12號</li>
      <li>副班長 / Vice Leader: 2號</li>
      <li>風紀股長 / Discipline Leader: 21號</li>
      <li>副風紀股長 / Vice Discipline Leader: 3號</li>
      <li>總務股長 / General Affairs Leader: 24號</li>
      <li>副總務股長 / Vice General Affairs Leader: 23號</li>
    </ul>
  </section>

  <section class="section" id="calendar">
    <h2>班級行事曆 / Class Calendar</h2>
    <p id="calendar-text">日後將隨更新推出 / Will be released in future updates</p>
  </section>

  <footer>
    <p>此網站為學生自行製作，非東新國中官方製作。<br>This website is created by students and not officially affiliated with Dongxin Junior High School.</p>
    <div class="lang-switcher" onclick="toggleLang()">切換語言 / Switch Language</div>
  </footer>

  <script>
    const sections = document.querySelectorAll('.section');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, {
      threshold: 0.1
    });

    sections.forEach(section => {
      observer.observe(section);
    });

    let currentLang = 'zh';
    function toggleLang() {
      currentLang = currentLang === 'zh' ? 'en' : 'zh';
      document.querySelector('#title').textContent =
        currentLang === 'zh' ? 'DSJH 705 班級網站' : 'DSJH 705 Class Website';

      document.querySelector('#leaders h2').textContent =
        currentLang === 'zh' ? '班級幹部 / Class Leaders' : 'Class Leaders / 班級幹部';

      document.querySelector('#calendar h2').textContent =
        currentLang === 'zh' ? '班級行事曆 / Class Calendar' : 'Class Calendar / 班級行事曆';

      document.querySelector('#calendar-text').textContent =
        currentLang === 'zh' ? '日後將隨更新推出 / Will be released in future updates' : 'Will be released in future updates / 日後將隨更新推出';

      document.querySelector('footer p').innerHTML =
        currentLang === 'zh'
          ? '此網站為學生自行製作，非東新國中官方製作。<br>This website is created by students and not officially affiliated with Dongxin Junior High School.'
          : 'This website is created by students and not officially affiliated with Dongxin Junior High School.<br>此網站為學生自行製作，非東新國中官方製作。';
    }
  </script>
</body>
</html>
