<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>DSJH 805 班級網站</title>
  <meta name="description" content="東新國中805班官方網站，提供課表、公告與聯絡資訊">
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
      background-color: rgba(255, 255, 255, 0.85);
      border-radius: 16px;
      border: 1px solid rgba(255, 255, 255, 0.3);
      padding: 1.5rem;
      max-width: 800px;
      position: relative;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
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

    /* 按鈕懸停效果 */
    .school-btn, .location-btn, .back-to-top {
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
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }
    .school-btn { 
      background-color: #2ecc71; 
    }
    .school-btn:hover { 
      background-color: #27ae60;
      transform: translateY(-2px);
    }
    .location-btn { 
      background-color: #3498db; 
    }
    .location-btn:hover { 
      background-color: #2980b9;
      transform: translateY(-2px);
    }
    .school-btn::after, .location-btn::after {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: linear-gradient(
        to bottom right,
        rgba(255,255,255,0.3) 0%,
        rgba(255,255,255,0) 60%
      );
      transform: rotate(30deg);
    }
    .back-to-top {
      background-color: #9b59b6;
      position: fixed;
      bottom: 20px;
      right: 20px;
      display: none;
    }
    .back-to-top:hover {
      background-color: #8e44ad;
      transform: translateY(-2px);
    }

    main {
      max-width: 1000px;
      margin: 0 auto;
      padding: 1rem;
    }

    section, footer {
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      background-color: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      margin-bottom: 2rem;
      border: 1px solid rgba(255, 255, 255, 0.3);
    }

    /* 動態公告區塊 */
    .live-badge {
      background: #e74c3c;
      color: white;
      padding: 0.2rem 0.5rem;
      border-radius: 4px;
      font-size: 0.8rem;
      animation: pulse 1.5s infinite;
    }
    .announcement-container {
      max-height: 300px;
      overflow-y: auto;
      padding-right: 10px;
    }
    .announcement-item {
      background: rgba(255,255,255,0.7);
      border-left: 3px solid #3498db;
      padding: 0.8rem;
      margin-bottom: 0.8rem;
      border-radius: 0 8px 8px 0;
      transition: all 0.3s;
    }
    .announcement-item:hover {
      transform: translateX(5px);
      box-shadow: 2px 2px 10px rgba(0,0,0,0.1);
    }
    .announcement-date {
      font-size: 0.8rem;
      color: #7f8c8d;
      margin-bottom: 0.3rem;
    }
    .urgent {
      border-left-color: #e74c3c !important;
      background: rgba(231, 76, 60, 0.1) !important;
    }
    @keyframes pulse {
      0% { opacity: 0.6; }
      50% { opacity: 1; }
      100% { opacity: 0.6; }
    }

    /* 重要事項樣式 */
    .event-item {
      text-align: center;
      margin: 1rem 0;
      padding: 0.8rem;
      background: rgba(255,255,255,0.6);
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }

    /* 聯絡方式 */
    .contact-container {
      text-align: center;
      margin-top: 1rem;
    }
    .contact-email {
      display: inline-block;
      background: rgba(255,255,255,0.7);
      padding: 0.8rem 1.5rem;
      border-radius: 30px;
      margin: 0.5rem auto;
      color: #3498db;
      text-decoration: none;
      transition: all 0.3s;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .contact-email:hover {
      background: rgba(52, 152, 219, 0.2);
      transform: translateY(-2px);
      box-shadow: 0 4px 8px rgba(0,0,0,0.15);
    }

    /* 頁尾 */
    footer {
      text-align: center;
      font-size: 0.9rem;
    }

    /* 內容居中樣式 */
    .centered-content {
      text-align: center;
      padding: 1rem 0;
    }

    /* 載入狀態 */
    .loading, .no-data, .error {
      text-align: center;
      padding: 1rem;
      color: #7f8c8d;
    }

    /* RWD 響應式設計 */
    @media (max-width: 768px) {
      header, section {
        margin: 1rem;
      }
      .btn-container {
        top: 10px;
        right: 10px;
      }
    }
  </style>
</head>
<body>
  <!-- 右上角按鈕 -->
  <div class="btn-container">
    <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" class="school-btn" target="_blank">進入學校網站</a>
    <a href="https://www.google.com/maps?q=928屏東縣東港鎮東新路1號" class="location-btn" target="_blank">學校位置查看</a>
  </div>
  
  <!-- 返回頂部按鈕 -->
  <a href="#" class="back-to-top">↑ 返回頂部</a>

  <header>
    <h1 id="title">DSJH 805 班級網站</h1>
  </header>

  <main>
    <!-- 動態公告區塊 -->
    <section id="announcements">
      <h2>最新公告 <span class="live-badge">LIVE</span></h2>
      <div class="announcement-container" id="announcement-list">
        <div class="loading">載入中...</div>
      </div>
    </section>

    <section>
      <h2>課表</h2>
      <p class="centered-content">暫無內容顯示。</p>
    </section>

    <section id="officers">
      <h2>班級幹部</h2>
      <p class="centered-content">暫無內容顯示。</p>
    </section>

    <section id="important">
      <h2>重要事項</h2>
      <p style="text-align: center; font-size: 0.85rem; color: #666;">（非即時更改）</p>
      <hr style="width: 60%; margin: 1rem auto; border: 0; border-top: 1px solid rgba(0,0,0,0.1);">
      <div class="event-item">📌 8/28 新生訓練</div>
      <div class="event-item">📌 8/29 全校返校日</div>
      <div class="event-item">📌 9/1 正式開學</div>
    </section>

    <section id="photos">
      <h2>班級照片</h2>
      <p class="centered-content">暫無內容顯示。</p>
    </section>

    <section id="contact">
      <h2>作者聯絡方式</h2>
      <div class="contact-container">
        <a href="mailto:lianyuqing169@gmail.com" class="contact-email">lianyuqing169@gmail.com</a>
      </div>
      <p style="text-align: center; color: #666; font-size: 0.9rem; margin-top: 1rem;">
        請聯絡時將所有事情一次打好，請勿重複傳送 Gmail。
      </p>
    </section>
  </main>

  <footer>
    <div id="footer-text">此網站為學生自行製作，非東新國中官方製作。</div>
  </footer>

  <script>
    // 返回頂部按鈕顯示/隱藏
    window.addEventListener('scroll', function() {
      const backToTop = document.querySelector('.back-to-top');
      if (window.pageYOffset > 300) {
        backToTop.style.display = 'block';
      } else {
        backToTop.style.display = 'none';
      }
    });

    // 動態載入公告 (使用 Google Sheets 作為後端)
    async function loadAnnouncements() {
      try {
        // ★ 請替換成你的 Google Sheets ID ★
        const sheetId = '1sz54ecuwgSz6QvbR5GrtyugznuYxKDfZOBo-GnYz_94';
        const sheetUrl = `https://docs.google.com/spreadsheets/d/${sheetId}/gviz/tq?tqx=out:json`;
        
        const response = await fetch(sheetUrl);
        const data = await response.text();
        const json = JSON.parse(data.substr(47).slice(0, -2));
        
        let html = '';
        json.table.rows.forEach(row => {
          const [date, title, content, isUrgent] = row.c;
          const urgentClass = (isUrgent && isUrgent.v === '是') ? 'urgent' : '';
          
          html += `
            <div class="announcement-item ${urgentClass}">
              <div class="announcement-date">${date.v}</div>
              <h3>${title.v}</h3>
              <p>${content.v}</p>
            </div>
          `;
        });
        
        document.getElementById('announcement-list').innerHTML = html || 
          '<div class="no-data">暫無公告</div>';
      } catch (error) {
        console.error('公告載入失敗:', error);
        document.getElementById('announcement-list').innerHTML = 
          '<div class="error">公告載入失敗，請稍後再試</div>';
      }
    }

    // 每5分鐘自動刷新公告
    loadAnnouncements();
    setInterval(loadAnnouncements, 5 * 60 * 1000);

    // 點擊水波紋效果
    document.addEventListener('click', (e) => {
      const ripple = document.createElement('div');
      ripple.className = 'ripple-effect';
      ripple.style.left = `${e.clientX}px`;
      ripple.style.top = `${e.clientY}px`;
      document.body.appendChild(ripple);
      setTimeout(() => ripple.remove(), 1000);
    });
  </script>

  <style>
    /* 點擊水波紋效果 */
    .ripple-effect {
      position: fixed;
      width: 20px;
      height: 20px;
      background: rgba(255,255,255,0.6);
      border-radius: 50%;
      transform: translate(-50%, -50%) scale(0);
      animation: ripple 1s ease-out;
      pointer-events: none;
    }
    @keyframes ripple {
      to { transform: translate(-50%, -50%) scale(10); opacity: 0; }
    }
  </style>
</body>
</html>
