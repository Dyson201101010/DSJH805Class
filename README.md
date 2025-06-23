<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
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
    header, section.block, footer {
      opacity: 0;
      transform: translateY(50px);
      animation: fadeInUp 0.8s ease forwards;
    }
    header { animation-delay: 0.1s; }
    section.block:nth-of-type(1) { animation-delay: 0.3s; }
    section.block:nth-of-type(2) { animation-delay: 0.5s; }
    section.block:nth-of-type(3) { animation-delay: 0.7s; }
    section.block:nth-of-type(4) { animation-delay: 0.9s; }
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
    }

    main {
      max-width: 1000px;
      margin: 0 auto;
      padding: 1rem;
    }

    section.block {
      background: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
      margin-bottom: 2rem;
    }

    .schedule-wrapper {
      overflow-x: auto;
    }
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
    ul li {
      margin: 0.3rem 0;
    }
    h2 {
      text-align: left;
      margin-bottom: 1rem;
      font-weight: 700;
    }
    /* 重要事項條目置中 */
    #important-zh p,
    #important-en p {
      text-align: center;
      margin-top: 0.5rem;
    }
    /* 重要事項標題下的非即時更改 */
    .note {
      text-align: right;
      font-size: 0.85rem;
      color: #666;
      margin-top: 0.5rem;
    }
    .separator {
      width: 60%;
      margin: 0.5rem auto 1rem;
      border: 0;
      border-top: 1px solid #ccc;
    }
    footer {
      max-width: 1000px;
      margin: 2rem auto 2rem;
      text-align: center;
      padding: 1rem;
      background-color: rgba(255, 255, 255, 0.8);
      border-radius: 12px;
      font-size: 0.9rem;
      /* 新增按鈕與文字間隔 */
      display: flex;
      flex-direction: column;
      gap: 1rem;
      align-items: center;
    }

    footer button {
      padding: 0.5rem 1.5rem;
      font-size: 1rem;
      cursor: pointer;
      border-radius: 8px;
      border: 1px solid #333;
      background-color: #fff;
      transition: background-color 0.3s ease;
    }
    footer button:hover {
      background-color: #eee;
    }

    /* 語言切換用active類別 */
    .zh {
      display: block;
    }
    .en {
      display: none;
    }
    .active {
      display: block !important;
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title" class="zh active">DSJH 705 班級網站</h1>
    <h1 id="title-en" class="en">DSJH 705 Class Website</h1>
  </header>

  <main>
    <!-- 中文版區塊 -->
    <section id="schedule-zh" class="block zh active">
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

    <section id="officers-zh" class="block zh active">
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

    <section id="important-zh" class="block zh active" style="padding-bottom: 2.5rem;">
      <h2>重要事項</h2>
      <p class="note">（非即時更改）</p>
      <hr class="separator" />
      <p>📌 6/26-6/27段考</p>
      <p>📌 6/30休業式</p>
    </section>

    <section id="photos-zh" class="block zh active">
      <h2>班級照片</h2>
      <p>之後將推出此功能。</p>
    </section>

    <!-- 英文版區塊 -->
    <section id="schedule-en" class="block en">
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

    <section id="officers-en" class="block en">
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

    <section id="important-en" class="block en" style="padding-bottom: 2.5rem;">
      <h2>Important Announcements</h2>
      <p class="note">(Not real-time updates)</p>
      <hr class="separator" />
      <p>📌 June 26-27 Exams</p>
      <p>📌 June 30 Closing Ceremony</p>
    </section>

    <section id="photos-en" class="block en">
      <h2>Class Photos</h2>
      <p>Coming soon.</p>
    </section>
  </main>

  <footer>
    <button id="lang-toggle-btn">Switch to English</button>
    <div id="footer-text-zh" class="zh active">此網站為學生自行製作，非東新國中官方製作。</div>
    <div id="footer-text-en" class="en">This website is created by students and not officially affiliated with Dongxin Junior High School.</div>
  </footer>

  <script>
    const btn = document.getElementById('lang-toggle-btn');
    const zhElements = document.querySelectorAll('.zh');
    const enElements = document.querySelectorAll('.en');

    let isChinese = true; // 初始為中文版顯示

    function setLanguage(chinese) {
      if (chinese) {
        zhElements.forEach(el => {
          el.classList.add('active');
          el.style.display = ''; // 確保正確顯示
        });
        enElements.forEach(el => {
          el.classList.remove('active');
          el.style.display = 'none';
        });
        btn.textContent = 'Switch to English';
      } else {
        enElements.forEach(el => {
          el.classList.add('active');
          el.style.display = '';
        });
        zhElements.forEach(el => {
          el.classList.remove('active');
          el.style.display = 'none';
        });
        btn.textContent = '切換回中文';
      }
      // 重置動畫
      const blocks = document.querySelectorAll('section.block, header, footer');
      blocks.forEach((block, i) => {
        block.style.animation = 'none';
        block.offsetHeight; // trigger reflow
        block.style.animation = `fadeInUp 0.8s ease forwards`;
        block.style.animationDelay = `${0.1 + i * 0.2}s`;
      });
    }

    btn.addEventListener('click', () => {
      isChinese = !isChinese;
      setLanguage(isChinese);
    });

    // 初始化
    setLanguage(isChinese);
  </script>
</body>
</html>
