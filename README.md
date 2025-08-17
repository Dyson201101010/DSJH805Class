<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>DSJH 805 班級網站</title>
  <meta name="description" content="東新國中805班官方網站，提供課表、公告與聯絡資訊">
  
  <!-- 效能優化：預載字體 -->
  <link rel="preload" href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;700&display=swap" as="style">
  <link rel="preconnect" href="https://fonts.gstatic.com">
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
      overflow-x: hidden;
    }
    
    /* 高性能粒子背景 */
    #particles-js {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      pointer-events: none;
      transform: translateZ(0);
      will-change: transform;
    }
    
    /* 標題置中修正 */
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
    
    header h1 {
      text-align: center;
      width: 100%;
      margin: 0 auto;
      padding: 0;
    }

    /* 原有區塊樣式 + 流暢優化 */
    section, footer {
      opacity: 0;
      transform: translateY(50px) translateZ(0);
      animation: fadeInUp 0.8s ease forwards;
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      background-color: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      margin-bottom: 2rem;
      border: 1px solid rgba(255, 255, 255, 0.3);
      transition: transform 0.3s cubic-bezier(0.25, 0.1, 0.25, 1), 
                  box-shadow 0.3s ease;
      will-change: transform;
    }
    
    /* 流暢懸停效果 */
    section:hover {
      transform: scale(1.02) translateZ(0) !important;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15) !important;
    }
    
    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0) translateZ(0);
      }
    }
    
    header { animation-delay: 0.1s; }
    section:nth-of-type(1) { animation-delay: 0.3s; }
    section:nth-of-type(2) { animation-delay: 0.5s; }
    section:nth-of-type(3) { animation-delay: 0.7s; }
    footer { animation-delay: 0.9s; }

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
      transform: translateZ(0);
    }
    .school-btn { 
      background-color: #2ecc71; 
    }
    .school-btn:hover { 
      background-color: #27ae60;
      transform: translateY(-2px) translateZ(0);
    }
    .location-btn { 
      background-color: #3498db; 
    }
    .location-btn:hover { 
      background-color: #2980b9;
      transform: translateY(-2px) translateZ(0);
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
      transform: translateY(-2px) translateZ(0);
    }

    main {
      max-width: 1000px;
      margin: 0 auto;
      padding: 1rem;
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
      transform: translateZ(0);
    }
    .contact-email:hover {
      background: rgba(52, 152, 219, 0.2);
      transform: translateY(-2px) translateZ(0);
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

    /* RWD 響應式設計 */
    @media (max-width: 768px) {
      header, section {
        margin: 1rem;
      }
      .btn-container {
        top: 10px;
        right: 10px;
      }
      
      /* 手機端減弱動畫 */
      section:hover {
        transform: none !important;
      }
    }
  </style>
</head>
<body>
  <!-- 高性能粒子背景 -->
  <div id="particles-js"></div>
  
  <!-- 右上角按鈕 -->
  <div class="btn-container">
    <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" class="school-btn" target="_blank">進入學校網站</a>
    <a href="https://www.google.com/maps?q=928屏東縣東港鎮東新路1號" class="location-btn" target="_blank">學校位置查看</a>
  </div>
  
  <!-- 返回頂部按鈕 -->
  <a href="#" class="back-to-top">↑ 返回頂部</a>

  <!-- 已修正標題置中 -->
  <header>
    <h1 id="title">DSJH 805 班級網站</h1>
  </header>

  <main>
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
    // ===== 高性能粒子系統 =====
    function initParticles() {
      const container = document.getElementById('particles-js');
      const particleCount = Math.min(window.innerWidth / 5, 100); // 根據寬度自動調整數量
      
      // 清空容器
      container.innerHTML = '';
      
      for (let i = 0; i < particleCount; i++) {
        const particle = document.createElement('div');
        particle.className = 'particle';
        
        // 初始隨機樣式
        const size = Math.random() * 3 + 1;
        const opacity = Math.random() * 0.4 + 0.1;
        
        Object.assign(particle.style, {
          width: `${size}px`,
          height: `${size}px`,
          left: `${Math.random() * 100}vw`,
          top: `${Math.random() * 100}vh`,
          opacity: opacity,
          transform: 'translateZ(0)',
          position: 'absolute',
          'border-radius': '50%',
          'pointer-events': 'none',
          'background-color': 'rgba(255,255,255,0.6)'
        });
        
        container.appendChild(particle);
        animateParticle(particle);
      }
    }
    
    // 流暢粒子動畫
    function animateParticle(el) {
      let x = Math.random() * window.innerWidth;
      let y = Math.random() * window.innerHeight;
      const speedX = Math.random() * 0.5 - 0.25;
      const speedY = Math.random() * 0.5 - 0.25;
      
      function update() {
        x += speedX;
        y += speedY;
        
        // 邊界檢查
        if (x > window.innerWidth) x = 0;
        if (x < 0) x = window.innerWidth;
        if (y > window.innerHeight) y = 0;
        if (y < 0) y = window.innerHeight;
        
        el.style.transform = `translate(${x}px, ${y}px) translateZ(0)`;
        requestAnimationFrame(update);
      }
      
      update();
    }

    // ===== 頁面初始化 =====
    document.addEventListener('DOMContentLoaded', () => {
      // 初始化粒子系統
      initParticles();
      
      // 返回頂部按鈕
      window.addEventListener('scroll', () => {
        document.querySelector('.back-to-top').style.display = 
          window.scrollY > 300 ? 'block' : 'none';
      }, { passive: true });
      
      // 點擊水波紋效果
      document.addEventListener('click', (e) => {
        const ripple = document.createElement('div');
        ripple.className = 'ripple-effect';
        ripple.style.cssText = `
          position: fixed;
          width: 20px;
          height: 20px;
          background: rgba(255,255,255,0.6);
          border-radius: 50%;
          transform: translate(-50%, -50%) scale(0);
          animation: ripple 1s ease-out;
          pointer-events: none;
          left: ${e.clientX}px;
          top: ${e.clientY}px;
          z-index: 1000;
        `;
        document.body.appendChild(ripple);
        setTimeout(() => ripple.remove(), 1000);
      });
    });

    // 響應式調整
    window.addEventListener('resize', () => {
      initParticles();
    });
  </script>
</body>
</html>
