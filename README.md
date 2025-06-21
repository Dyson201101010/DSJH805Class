<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>DSJH 705 班級網站</title>
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

    #photo-list img {
      max-width: 100%;
      border-radius: 8px;
      margin-top: 1rem;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 1rem;
    }

    th, td {
      border: 1px solid #999;
      padding: 8px;
      text-align: center;
    }

    th {
      background-color: #f0f0f0;
    }

    ul {
      list-style-type: disc;
      padding-left: 1.5rem;
      margin-top: 1rem;
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title">DSJH 705 班級網站</h1>
  </header>

  <section class="section" id="schedule">
    <h2>課表 / Class Schedule</h2>
    <table>
      <thead>
        <tr>
          <th>星期</th>
          <th colspan="9">課程</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>星期一</td>
          <td>閱讀</td>
          <td>表演</td>
          <td>國文</td>
          <td>數學</td>
          <td>午餐/午休</td>
          <td>自然科學</td>
          <td>家政</td>
          <td>生活科技</td>
          <td>英文複習</td>
        </tr>
        <tr>
          <td>星期二</td>
          <td>健康</td>
          <td>體育</td>
          <td>童軍</td>
          <td>國文</td>
          <td>午餐/午休</td>
          <td>音樂</td>
          <td>作家</td>
          <td>數學</td>
          <td>數學複習</td>
        </tr>
        <tr>
          <td>星期三</td>
          <td>閩南語</td>
          <td>自然科學</td>
          <td>輔導</td>
          <td>地理</td>
          <td>午餐/午休</td>
          <td>視覺</td>
          <td>國文</td>
          <td>英文</td>
          <td>國文複習</td>
        </tr>
        <tr>
          <td>星期四</td>
          <td>國文</td>
          <td>FUN學</td>
          <td>數學</td>
          <td>自然科學</td>
          <td>午餐/午休</td>
          <td>資訊科技</td>
          <td>歷史</td>
          <td>英文</td>
          <td>自然複習</td>
        </tr>
        <tr>
          <td>星期五</td>
          <td>英文</td>
          <td>國文</td>
          <td>公民</td>
          <td>體育</td>
          <td>午餐/午休</td>
          <td>班會</td>
          <td>數學</td>
          <td>社團</td>
          <td>社團</td>
        </tr>
      </tbody>
    </table>
  </section>

  <section class="section" id="leaders">
    <h2>班級幹部 / Class Leaders</h2>
    <ul>
      <li>班長 / Class Leader: 12號</li>
      <li>副班長 / Vice Leader: 2號</li>
      <li>風紀股長 / Discipline Leader: 21號</li>
      <li>副風紀股長 / Vice Discipline Leader: 3號</li>
      <li>總務股長 / General Affairs Leader: 24號</li>
      <li>副總務股長 / Vice General Affairs Leader: 23號</li>
      <li>衛生股長 / Health Leader: 17號</li>
      <li>學藝股長 / Academic Affairs Leader: 7號</li>
      <li>導師秘書 / Homeroom Secretary: N/A</li>
      <li>午餐股長 / Lunch Leader: 5號</li>
      <li>輔導股長 / Guidance Leader: 10號</li>
      <li>康樂股長 / Recreation Leader: 18號</li>
    </ul>
  </section>

  <section class="section" id="important">
    <h2>重要事項 / Important Notices</h2>
    <p>目前無內容 / No content yet</p>
  </section>

  <section class="section" id="photos">
    <h2>照片專區 / Photo Gallery</h2>
    <p>目前無內容 / No content yet</p>
  </section>

  <footer>
    <p>此網站為學生自行製作，非東新國中官方製作。<br />This website is created by students and not officially affiliated with Dongxin Junior High School.</p>
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

      document.querySelector('#important h2').textContent =
        currentLang === 'zh' ? '重要事項 / Important Notices' : 'Important Notices / 重要事項';

      document.querySelector('#important p').textContent =
        currentLang === 'zh' ? '目前無內容 / No content yet' : 'No content yet / 目前無內容';

      document.querySelector('#photos h2').textContent =
        currentLang === 'zh' ? '照片專區 / Photo Gallery' : 'Photo Gallery / 照片專區';

      document.querySelector('#photos p').textContent =
        currentLang === 'zh' ? '目前無內容 / No content yet' : 'No content yet / 目前無內容';

      document.querySelector('footer p').innerHTML =
        currentLang === 'zh'
          ? '此網站為學生自行製作，非東新國中官方製作。<br />This website is created by students and not officially affiliated with Dongxin Junior High School.'
          : 'This website is created by students and not officially affiliated with Dongxin Junior High School.<br />此網站為學生自行製作，非東新國中官方製作。';
    }
  </script>
</body>
</html>
