<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>DSJH 705 班級網站 / Class Website</title>
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
    main > section:nth-of-type(1) { animation-delay: 0.3s; }
    main > section:nth-of-type(2) { animation-delay: 0.5s; }
    main > section:nth-of-type(3) { animation-delay: 0.7s; }
    main > section:nth-of-type(4) { animation-delay: 0.9s; }
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

    .schedule-wrapper { overflow-x: auto; }
    table {
      border-collapse: collapse;
      width: 100%;
      min-width: 950px;
    }
    th, td {
      border: 1px solid #999;
      padding: 10px;
      text-align: center;
      white-space: nowrap;
    }
    ul {
      list-style: none;
      padding: 0;
      text-align: center;
    }
    ul li { margin: 0.3rem 0; }
    h2 {
      text-align: left;
      margin-bottom: 1rem;
    }
    /* 重要事項標題下方的非即時更改說明 */
    #important p.note {
      text-align: right;
      font-size: 0.85rem;
      color: #666;
      margin-top: 0.5rem;
      margin-bottom: 1rem;
    }
    #important hr {
      width: 60%;
      margin: 0 auto 1.5rem auto;
      border: 0;
      border-top: 1px solid #ccc;
    }

    #important p.content {
      text-align: center;
      margin: 0.5rem 0;
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

    /* 語言切換按鈕 */
    #lang-switcher {
      position: fixed;
      bottom: 3.5rem;
      right: 2rem;
      background: rgba(255,255,255,0.9);
      border-radius: 8px;
      padding: 0.5rem 1rem;
      cursor: pointer;
      box-shadow: 0 2px 6px rgba(0,0,0,0.2);
      z-index: 1000;
      user-select: none;
      font-weight: 700;
    }

    /* 語言切換按鈕與版權文字區隔 */
    #footer-text {
      margin-bottom: 2rem;
    }

    /* 隱藏所有中文區塊時 */
    .hidden {
      display: none !important;
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title-zh">DSJH 705 班級網站</h1>
    <h1 id="title-en" class="hidden">DSJH 705 Class Website</h1>
  </header>

  <main>
    <!-- 中文版 -->
    <section id="schedule-zh">
      <h2>課表</h2>
      <div class="schedule-wrapper">
        <table>
          <thead>
            <tr><th>星期</th><th>第一節</th><th>第二節</th><th>第三節</th><th>第四節</th><th>中午</th><th>第五節</th><th>第六節</th><th>第七節</th><th>第八節</th></tr>
          </thead>
          <tbody>
            <tr><td>星期一</td><td>閱讀</td><td>表演</td><td>國文</td><td>數學</td><td>午餐</td><td>自然</td><td>家政</td><td>科技</td><td>英文複習</td></tr>
            <tr><td>星期二</td><td>健康</td><td>體育</td><td>童軍</td><td>國文</td><td>午餐</td><td>音樂</td><td>作家</td><td>數學</td><td>數學複習</td></tr>
            <tr><td>星期三</td><td>閩南語</td><td>自然科學</td><td>輔導</td><td>地理</td><td>午餐</td><td>視覺</td><td>國文</td><td>英文</td><td>國文複習</td></tr>
            <tr><td>星期四</td><td>國文</td><td>FUN學</td><td>數學</td><td>自然科學</td><td>午餐</td><td>資訊科技</td><td>歷史</td><td>英文</td><td>自然複習</td></tr>
            <tr><td>星期五</td><td>英文</td><td>國文</td><td>公民</td><td>體育</td><td>午餐</td><td>班會</td><td>數學</td><td>社團</td><td>社團</td></tr>
          </tbody>
        </table>
      </div>
    </section>

    <section id="officers-zh">
      <h2>班級幹部</h2>
      <ul>
        <li>班長：12號</li>
        <li>副班長：2號</li>
        <li>風紀股長：21號</li>
        <li>副風紀股長：3號</li>
        <li>總務股長：24號</li>
        <li>副總務股長：23號</li>
        <li>衛生股長：17號</li>
        <li>學藝股長：7號</li>
        <li>導師秘書：14號</li>
        <li>午餐股長：5號</li>
        <li>輔導股長：10號</li>
        <li>康樂股長：18號</li>
      </ul>
    </section>

    <section id="important-zh" style="padding-bottom: 2.5rem;">
      <h2>重要事項</h2>
      <p class="note">（非即時更改）</p>
      <hr />
      <p class="content">📌 6/26-6/27段考</p>
      <p class="content">📌 6/30休業式</p>
    </section>

    <section id="photos-zh">
      <h2>班級照片</h2>
      <p style="text-align:center;">之後將推出此功能。</p>
    </section>

    <!-- 英文版 -->
    <section id="schedule-en" class="hidden">
      <h2>Class Schedule</h2>
      <div class="schedule-wrapper">
        <table>
          <thead>
            <tr><th>Day</th><th>Period 1</th><th>Period 2</th><th>Period 3</th><th>Period 4</th><th>Lunch</th><th>Period 5</th><th>Period 6</th><th>Period 7</th><th>Period 8</th></tr>
          </thead>
          <tbody>
            <tr><td>Monday</td><td>Reading</td><td>Performance</td><td>Chinese</td><td>Math</td><td>Lunch</td><td>Science</td><td>Home Ec</td><td>Tech</td><td>English Review</td></tr>
            <tr><td>Tuesday</td><td>Health</td><td>PE</td><td>Scouts</td><td>Chinese</td><td>Lunch</td><td>Music</td><td>Author</td><td>Math</td><td>Math Review</td></tr>
            <tr><td>Wednesday</td><td>Min Nan</td><td>Science</td><td>Counseling</td><td>Geography</td><td>Lunch</td><td>Visual Arts</td><td>Chinese</td><td>English</td><td>Chinese Review</td></tr>
            <tr><td>Thursday</td><td>Chinese</td><td>FUN Learning</td><td>Math</td><td>Science</td><td>Lunch</td><td>IT</td><td>History</td><td>English</td><td>Science Review</td></tr>
            <tr><td>Friday</td><td>English</td><td>Chinese</td><td>Civics</td><td>PE</td><td>Lunch</td><td>Class Meeting</td><td>Math</td><td>Club</td><td>Club</td></tr>
          </tbody>
        </table>
      </div>
    </section>

    <section id="officers-en" class="hidden">
      <h2>Class Officers</h2>
      <ul>
        <li>Class Leader: No. 12</li>
        <li>Vice Leader: No. 2</li>
        <li>Discipline Leader: No. 21</li>
        <li>Vice Discipline: No. 3</li>
        <li>General Affairs Leader: No. 24</li>
        <li>Vice General Affairs: No. 23</li>
        <li>Health Leader: No. 17</li>
        <li>Arts Leader: No. 7</li>
        <li>Teacher Secretary: No. 14</li>
        <li>Lunch Leader: No. 5</li>
        <li>Counseling Leader: No. 10</li>
        <li>Recreation Leader: No. 18</li>
      </ul>
    </section>

    <section id="important-en" class="hidden" style="padding-bottom: 2.5rem;">
      <h2>Important Announcements</h2>
      <p class="note">(* Not real-time updates)</p>
      <hr />
      <p class="content">📌 Exams on June 26-27</p>
      <p class="content">📌 School Closing Ceremony on June 30</p>
    </section>

    <section id="photos-en" class="hidden">
      <h2>Class Photos</h2>
      <p style="text-align:center;">This feature will be available soon.</p>
    </section>
  </main>

  <footer>
    <div id="footer-text-zh">此網站為學生自行製作，非東新國中官方製作。</div>
    <div id="footer-text-en" class="hidden">This website is created by students and not officially affiliated with Dongxin Junior High School.</div>
  </footer>

  <div id="lang-switcher">切換英文版 / Switch to English</div>

  <script>
    const langSwitcher = document.getElementById('lang-switcher');
    let currentLang = 'zh';

    function switchToEnglish() {
      // 隱藏中文區塊，顯示英文區塊
      document.getElementById('title-zh').classList.add('hidden');
      document.getElementById('title-en').classList.remove('hidden');

      ['schedule-zh', 'officers-zh', 'important-zh', 'photos-zh'].forEach(id => {
        document.getElementById(id).classList.add('hidden');
      });
      ['schedule-en', 'officers-en', 'important-en', 'photos-en'].forEach(id => {
        document.getElementById(id).classList.remove('hidden');
      });

      document.getElementById('footer-text-zh').classList.add('hidden');
      document.getElementById('footer-text-en').classList.remove('hidden');

      langSwitcher.textContent = '切換中文版 / Switch to Chinese';
      currentLang = 'en';
    }

    function switchToChinese() {
      // 顯示中文區塊，隱藏英文區塊
      document.getElementById('title-zh').classList.remove('hidden');
      document.getElementById('title-en').classList.add('hidden');

      ['schedule-zh', 'officers-zh', 'important-zh', 'photos-zh'].forEach(id => {
        document.getElementById(id).classList.remove('hidden');
      });
      ['schedule-en', 'officers-en', 'important-en', 'photos-en'].forEach(id => {
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
