<!DOCTYPE html>
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
    header, main, footer {
      opacity: 0;
      transform: translateY(50px);
      animation: fadeInUp 0.8s ease forwards;
    }
    header { animation-delay: 0.1s; }
    main { animation-delay: 0.4s; }
    footer { animation-delay: 1.4s; }
    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    header {
      text-align: center;
      margin: 2rem auto 2rem;
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
      display: flex;
      flex-direction: column;
      gap: 2.5rem;
      padding: 0 1rem 3rem;
    }
    section {
      background: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
      width: 100%;
      overflow-x: auto;
    }
    h2 {
      text-align: center;
      margin-bottom: 1rem;
    }
    table {
      border-collapse: collapse;
      width: 100%;
      min-width: 900px;
    }
    th, td {
      border: 1px solid #999;
      padding: 10px;
      text-align: center;
      white-space: nowrap;
    }
    #officers ul {
      list-style: none;
      padding: 0;
      text-align: center;
    }
    #officers li {
      margin: 0.3rem 0;
    }
    footer {
      max-width: 1000px;
      margin: 0 auto 2rem;
      text-align: center;
      padding: 1rem;
      background-color: rgba(255, 255, 255, 0.8);
      border-radius: 12px;
      font-size: 0.9rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>DSJH 705 班級網站</h1>
  </header>

  <main>
    <section id="schedule">
      <h2>課表</h2>
      <table>
        <thead>
          <tr>
            <th>星期</th><th>第一節</th><th>第二節</th><th>第三節</th><th>第四節</th><th>中午</th><th>第五節</th><th>第六節</th><th>第七節</th><th>第八節</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>星期一</td><td>閱讀</td><td>表演</td><td>國文</td><td>數學</td><td>午餐</td><td>自然</td><td>家政</td><td>科技</td><td>英文複習</td></tr>
          <tr><td>星期二</td><td>健康</td><td>體育</td><td>童軍</td><td>國文</td><td>午餐</td><td>音樂</td><td>作家</td><td>數學</td><td>數學複習</td></tr>
          <tr><td>星期三</td><td>閩南語</td><td>自然</td><td>輔導</td><td>地理</td><td>午餐</td><td>視覺</td><td>國文</td><td>英文</td><td>國文複習</td></tr>
          <tr><td>星期四</td><td>國文</td><td>FUN學</td><td>數學</td><td>自然</td><td>午餐</td><td>資訊</td><td>歷史</td><td>英文</td><td>自然複習</td></tr>
          <tr><td>星期五</td><td>英文</td><td>國文</td><td>公民</td><td>體育</td><td>午餐</td><td>班會</td><td>數學</td><td>社團</td><td>社團</td></tr>
        </tbody>
      </table>
    </section>

    <section id="officers">
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

    <section id="important">
      <h2>重要事項</h2>
      <p style="text-align:center;">目前無內容。</p>
    </section>

    <section id="photos">
      <h2>班級照片</h2>
      <p style="text-align:center;">目前無內容。</p>
    </section>
  </main>

  <footer>
    <div>此網站為學生自行製作，非東新國中官方製作。</div>
  </footer>
</body>
</html>
