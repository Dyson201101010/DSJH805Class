<!-- DSJH 805 Website with School Link & Location Button + 字體大小調整 + 玻璃效果 -->
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>DSJH 805 班級網站</title>
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
      background-attachment: fixed;
      min-height: 100vh;
      color: #333;
      font-size: medium;
    }
    header, section, footer {
      opacity: 0;
      transform: translateY(50px);
      animation: fadeInUp 0.8s ease forwards;
    }
    header { animation-delay: 0.1s; }
    section:nth-of-type(1) { animation-delay: 0.3s; }
    section:nth-of-type(2) { animation-delay: 0.5s; }
    section:nth-of-type(3) { animation-delay: 0.7s; }
    section:nth-of-type(4) { animation-delay: 0.9s; }
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

    /* 按鈕容器 */
    .btn-container {
      position: fixed;
      top: 20px;
      right: 20px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      z-index: 1000;
    }

    /* 字體調整容器 - 去除背景、陰影 */
    .font-size-wrapper {
      position: fixed;
      top: 20px;
      left: 20px;
      user-select: none;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      z-index: 1000;
      width: auto;
      /* 去除背景和陰影 */
      background: transparent;
      box-shadow: none;
      border-radius: 0;
      padding: 0;
    }

    /* 按鈕和選單共用樣式 */
    .font-size-button,
    .font-size-options button {
      font-size: 0.9rem;
      font-weight: 600;
      background-color: rgba(255,255,255,0.6);
      border: none;
      border-radius: 20px;
      padding: 8px 16px;
      cursor: pointer;
      user-select: none;
      color: #000;
      white-space: nowrap;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 36px;
      transition: background-color 0.3s ease;
      flex-shrink: 0;
      margin: 0;
    }

    /* 主按鈕 */
    .font-size-button {
      background-color: rgba(255,255,255,0.9);
      position: relative;
      z-index: 1001;
    }
    .font-size-button:hover,
    .font-size-button:focus {
      background-color: rgba(255,255,255,1);
      outline: none;
    }

    /* 選單 - 由上往下彈出，絕對定位於主按鈕正下方 */
    .font-size-options {
      position: absolute;
      top: 100%; /* 按鈕正下方 */
      left: 0;
      background: rgba(255, 255, 255, 0.25);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      border-radius: 20px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
      padding: 0.3rem 0.5rem;
      display: flex;
      flex-direction: column;
      gap: 8px;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s ease;
      white-space: nowrap;
      user-select: none;
      width: max-content;
      min-width: 120px;
      z-index: 1000;
      /* 高度自適應，變成垂直排列 */
    }

    /* hover 或 focus 時顯示選單 */
    .font-size-wrapper:hover .font-size-options,
    .font-size-wrapper:focus-within .font-size-options {
      opacity: 1;
      pointer-events: auto;
    }

    /* 選單按鈕 hover/focus */
    .font-size-options button:hover,
    .font-size-options button:focus {
      background-color: rgba(255,255,255,0.9);
      outline: none;
    }

    /* 其他按鈕樣式 */
    .school-btn, .location-btn {
      padding: 0.6rem 1.2rem;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      text-decoration: none;
      font-size: 0.9rem;
      text-align: center;
      white-space: nowrap;
      color: #fff;
      user-select: none;
    }
    .school-btn { background-color: #2ecc71; }
    .location-btn { background-color: #3498db; }

    main {
      max-width: 1000px;
      margin: 0 auto;
      padding: 1rem;
    }

    section, footer {
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      background-color: rgba(255, 255, 255, 0.3);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
      margin-bottom: 2rem;
      border: 1px solid rgba(255, 255, 255, 0.125);
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
    ul { list-style: none; text-align: center; }
    ul li { margin: 0.3rem 0; }
    h2 { text-align: left; margin-bottom: 1rem; }
    footer { text-align: center; font-size: 0.9rem; }
  </style>
</head>
<body>
  <!-- 左上角字體大小調整 按鈕 + 滑鼠靠近下方顯示選單 -->
  <div class="font-size-wrapper" id="fontSizeWrapper" tabindex="0" aria-label="字體大小調整選單">
    <button class="font-size-button" type="button" aria-haspopup="true" aria-expanded="false">字體大小調整</button>
    <div class="font-size-options" role="menu" aria-hidden="true">
      <button type="button" role="menuitem" onclick="changeFontSize('small')">小</button>
      <button type="button" role="menuitem" onclick="changeFontSize('medium')">中</button>
      <button type="button" role="menuitem" onclick="changeFontSize('large')">大</button>
      <button type="button" role="menuitem" onclick="changeFontSize('x-large')">特大</button>
    </div>
  </div>

  <!-- 右上角按鈕 -->
  <div class="btn-container">
    <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" class="school-btn" target="_blank">進入學校網站</a>
    <a href="https://www.google.com/maps?q=928屏東縣東港鎮東新路1號" class="location-btn" target="_blank">學校位置查看</a>
  </div>
  
  <header>
    <h1 id="title">DSJH 805 班級網站</h1>
  </header>

  <main>
    <section>
      <h2>課表</h2>
      <p style="text-align: center;">9/1將同步上線。</p>
    </section>

    <section id="officers">
      <h2>班級幹部</h2>
      <p style="text-align: center;">暫無內容。</p>
    </section>

    <section id="important">
      <h2>重要事項</h2>
      <p style="text-align: center; font-size: 0.85rem; color: #666;">（非即時更改）</p>
      <hr style="width: 60%; margin: 1rem auto; border: 0; border-top: 1px solid #ccc;">
      <p style="text-align:center;">📌 8/28 新生訓練</p>
      <p style="text-align:center;">📌 8/29 全校返校日</p>
      <p style="text-align:center;">📌 9/1 正式開學</p>
    </section>

    <section id="photos">
      <h2>班級照片</h2>
      <p style="text-align:center;">暫無內容。</p>
    </section>

    <section id="contact">
      <h2>作者聯絡方式</h2>
      <p style="text-align: center;">Gmail：lianyuqing169@gmail.com</p>
      <p style="text-align: center; color: #666; font-size: 0.9rem;">請聯絡時將所有事情一次打好，請勿重複傳送 Gmail。</p>
    </section>
  </main>

  <footer>
    <div id="footer-text">此網站為學生自行製作，非東新國中官方製作。</div>
  </footer>

  <script>
    function changeFontSize(size) {
      document.body.style.fontSize = size;
    }
  </script>
</body>
</html>
