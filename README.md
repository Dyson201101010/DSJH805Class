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
      max-width: 1000px;
      margin: 4rem auto;
      background: rgba(255, 255, 255, 0.85);
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      opacity: 0;
      transform: translateY(50px);
      transition: all 1s ease;
      overflow-x: auto;
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

    table {
      border-collapse: collapse;
      margin: 0 auto;
      margin-top: 1rem;
      min-width: 1000px;
    }

    th, td {
      border: 1px solid #999;
      padding: 10px;
      text-align: center;
      white-space: nowrap;
    }

    th {
      background-color: #f0f0f0;
    }

    ul {
      list-style: none;
      padding: 0;
      margin-top: 1.5rem;
      text-align: center;
    }

    ul li {
      margin: 0.5rem 0;
    }

    .section h2 {
      text-align: center;
      margin-bottom: 1.5rem;
    }

    .section p {
      text-align: center;
    }
  </style>
</head>
<body>
  <header>
    <h1 id="title">DSJH 705 班級網站</h1>
  </header>

  <section class="section zh" id="schedule">
    <h2>課表</h2>
    <table>
      <thead>
        <tr>
          <th>星期</th>
          <th>第一節</th>
          <th>第二節</th>
          <th>第三節</th>
          <th>第四節</th>
          <th>中午</th>
          <th>第五節</th>
          <th>第六節</th>
          <th>第七節</th>
          <th>第八節</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>星期一</td><td>閱讀</td><td>表演</td><td>國文</td><td>數學</td><td>午餐/午休</td><td>自然科學</td><td>家政</td><td>生活科技</td><td>英文複習</td></tr>
        <tr><td>星期二</td><td>健康</td><td>體育</td><td>童軍</td><td>國文</td><td>午餐/午休</td><td>音樂</td><td>作家</td><td>數學</td><td>數學複習</td></tr>
        <tr><td>星期三</td><td>閩南語</td><td>自然科學</td><td>輔導</td><td>地理</td><td>午餐/午休</td><td>視覺</td><td>國文</td><td>英文</td><td>國文複習</td></tr>
        <tr><td>星期四</td><td>國文</td><td>FUN學</td><td>數學</td><td>自然科學</td><td>午餐/午休</td><td>資訊科技</td><td>歷史</td><td>英文</td><td>自然複習</td></tr>
        <tr><td>星期五</td><td>英文</td><td>國文</td><td>公民</td><td>體育</td><td>午餐/午休</td><td>班會</td><td>數學</td><td>社團</td><td>社團</td></tr>
      </tbody>
    </table>
  </section>

  <section class="section zh" id="officers">
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
      <li>導師秘書：N/A</li>
      <li>午餐股長：5號</li>
      <li>輔導股長：10號</li>
      <li>康樂股長：18號</li>
    </ul>
  </section>

  <section class="section zh" id="important">
    <h2>重要事項</h2>
    <p>目前無內容。</p>
  </section>

  <section class="section zh" id="photos">
    <h2>班級照片</h2>
    <p>目前無內容。</p>
  </section>

  <section class="section en" style="display:none">
    <h2>Class Schedule</h2>
    <table>
      <thead>
        <tr>
          <th>Day</th>
          <th>Period 1</th>
          <th>Period 2</th>
          <th>Period 3</th>
          <th>Period 4</th>
          <th>Lunch</th>
          <th>Period 5</th>
          <th>Period 6</th>
          <th>Period 7</th>
          <th>Period 8</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Monday</td><td>Reading</td><td>Performance</td><td>Chinese</td><td>Math</td><td>Lunch Break</td><td>Science</td><td>Home Ec</td><td>Tech</td><td>English Review</td></tr>
        <tr><td>Tuesday</td><td>Health</td><td>PE</td><td>Scouts</td><td>Chinese</td><td>Lunch Break</td><td>Music</td><td>Author</td><td>Math</td><td>Math Review</td></tr>
        <tr><td>Wednesday</td><td>Min Nan</td><td>Science</td><td>Counseling</td><td>Geography</td><td>Lunch Break</td><td>Visual Arts</td><td>Chinese</td><td>English</td><td>Chinese Review</td></tr>
        <tr><td>Thursday</td><td>Chinese</td><td>FUN Learning</td><td>Math</td><td>Science</td><td>Lunch Break</td><td>IT</td><td>History</td><td>English</td><td>Science Review</td></tr>
        <tr><td>Friday</td><td>English</td><td>Chinese</td><td>Civics</td><td>PE</td><td>Lunch Break</td><td>Class Meeting</td><td>Math</td><td>Club</td><td>Club</td></tr>
      </tbody>
    </table>
  </section>

  <section class="section en" style="display:none">
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
      <li>Teacher Secretary: N/A</li>
      <li>Lunch Leader: No. 5</li>
      <li>Counseling Leader: No. 10</li>
      <li>Recreation Leader: No. 18</li>
    </ul>
  </section>

  <section class="section en" style="display:none">
    <h2>Important Announcements</h2>
    <p>No content at the moment.</p>
  </section>

  <section class="section en" style="display:none">
    <h2>Class Photos</h2>
    <p>No content at the moment.</p>
  </section>

  <footer>
    <p id="footer-text">此網站為學生自行製作，非東新國中官方製作。</p>
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
      const zhSections = document.querySelectorAll('.zh');
      const enSections = document.querySelectorAll('.en');
      const title = document.querySelector('#title');
      const footer = document.querySelector('#footer-text');

      if (currentLang === 'zh') {
        zhSections.forEach(s => s.style.display = 'none');
        enSections.forEach(s => s.style.display = 'block');
        title.textContent = 'DSJH 705 Class Website';
        footer.textContent = 'This website is created by students and not officially affiliated with Dongxin Junior High School.';
        currentLang = 'en';
      } else {
        zhSections.forEach(s => s.style.display = 'block');
        enSections.forEach(s => s.style.display = 'none');
        title.textContent = 'DSJH 705 班級網站';
        footer.textContent = '此網站為學生自行製作，非東新國中官方製作。';
        currentLang = 'zh';
      }
    }
  </script>
</body>
</html>
