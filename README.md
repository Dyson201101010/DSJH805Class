<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>DSJH 805 班級網站 / Class Website</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;700&display=swap" rel="stylesheet" />
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
    header, section, footer {
      opacity: 0;
      transform: translateY(50px);
      animation: fadeInUp 0.8s ease forwards;
    }
    header { animation-delay: 0.1s; }
    main > section.zh:nth-of-type(1), main > section.en:nth-of-type(1) { animation-delay: 0.3s; }
    main > section.zh:nth-of-type(2), main > section.en:nth-of-type(2) { animation-delay: 0.5s; }
    main > section.zh:nth-of-type(3), main > section.en:nth-of-type(3) { animation-delay: 0.7s; }
    main > section.zh:nth-of-type(4), main > section.en:nth-of-type(4) { animation-delay: 0.9s; }
    footer { animation-delay: 1.1s; }

    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    header {
      text-align: center;
      margin: 2rem auto 1rem;
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      background-color: rgba(255, 255, 255, 0.3);
      border-radius: 16px;
      border: 1px solid rgba(255, 255, 255, 0.125);
      padding: 1.5rem;
      max-width: 800px;
      position: relative;
    }

    main {
      max-width: 1000px;
      margin: 0 auto;
      padding: 1rem;
    }

    section {
      background: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
      margin-bottom: 2rem;
    }

    h2 {
      text-align: left;
      margin-bottom: 1rem;
    }

    footer {
      max-width: 1000px;
      margin: 2rem auto 2rem;
      text-align: center;
      padding: 1rem;
      background-color: rgba(255, 255, 255, 0.8);
      border-radius: 12px;
      font-size: 0.9rem;
      position: relative;
    }

    .hidden { display: none; }
    .lang-switcher {
      margin-top: 1rem;
      padding: 0.5rem 1rem;
      background-color: #f0f0f0;
      display: inline-block;
      border-radius: 8px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title-zh">DSJH 805 班級網站</h1>
    <h1 id="title-en" class="hidden">DSJH 805 Class Website</h1>
  </header>

  <main>
    <section class="zh" id="schedule-zh">
      <h2>課表</h2>
      <p style="text-align:center;">暫無內容</p>
    </section>
    <section class="zh" id="officers-zh">
      <h2>班級幹部</h2>
      <p style="text-align:center;">暫無內容</p>
    </section>
    <section class="zh" id="important-zh">
      <h2>重要事項</h2>
      <p style="text-align:center;">暫無內容</p>
    </section>
    <section class="zh" id="photos-zh">
      <h2>班級照片</h2>
      <p style="text-align:center;">之後將推出此功能。</p>
    </section>

    <section class="en hidden" id="schedule-en">
      <h2>Class Schedule</h2>
      <p style="text-align:center;">No content available</p>
    </section>
    <section class="en hidden" id="officers-en">
      <h2>Class Officers</h2>
      <p style="text-align:center;">No content available</p>
    </section>
    <section class="en hidden" id="important-en">
      <h2>Important Announcements</h2>
      <p style="text-align:center;">No content available</p>
    </section>
    <section class="en hidden" id="photos-en">
      <h2>Class Photos</h2>
      <p style="text-align:center;">This feature will be available soon.</p>
    </section>
  </main>

  <footer>
    <div id="footer-text-zh">此網站為學生自行製作，非東新國中官方製作。</div>
    <div id="footer-text-en" class="hidden">This website is created by students and is not officially affiliated with Dongxin Junior High School.</div>
    <div class="lang-switcher" id="lang-switcher">切換英文版 / Switch to English</div>
  </footer>

  <script>
    const langSwitcher = document.getElementById('lang-switcher');
    let currentLang = 'zh';

    function switchToEnglish() {
      document.getElementById('title-zh').classList.add('hidden');
      document.getElementById('title-en').classList.remove('hidden');

      ['schedule-zh','officers-zh','important-zh','photos-zh'].forEach(id => {
        document.getElementById(id).classList.add('hidden');
      });
      ['schedule-en','officers-en','important-en','photos-en'].forEach(id => {
        document.getElementById(id).classList.remove('hidden');
      });

      document.getElementById('footer-text-zh').classList.add('hidden');
      document.getElementById('footer-text-en').classList.remove('hidden');

      langSwitcher.textContent = '切換中文版 / Switch to Chinese';
      currentLang = 'en';
    }

    function switchToChinese() {
      document.getElementById('title-zh').classList.remove('hidden');
      document.getElementById('title-en').classList.add('hidden');

      ['schedule-zh','officers-zh','important-zh','photos-zh'].forEach(id => {
        document.getElementById(id).classList.remove('hidden');
      });
      ['schedule-en','officers-en','important-en','photos-en'].forEach(id => {
        document.getElementById(id).classList.add('hidden');
      });

      document.getElementById('footer-text-zh').classList.remove('hidden');
      document.getElementById('footer-text-en').classList.add('hidden');

      langSwitcher.textContent = '切換英文版 / Switch to English';
      currentLang = 'zh';
    }

    langSwitcher.addEventListener('click', () => {
      if (currentLang === 'zh') {
        switchToEnglish();
      } else {
        switchToChinese();
      }
    });
  </script>
</body>
</html>
