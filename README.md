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
      animation-timing-function: cubic-bezier(0.42, 0, 0.58, 1); /* iOS標準緩動函數 */
      transition-timing-function: cubic-bezier(0.42, 0, 0.58, 1);
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
      transform: translate3d(0, 0, 0);
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
      will-change: transform, opacity;
      backface-visibility: hidden;
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
      transform: translate3d(0, 50px, 0);
      animation: fadeInUp 0.8s ease forwards;
      backdrop-filter: blur(16px) saturate(180%);
      -webkit-backdrop-filter: blur(16px) saturate(180%);
      background-color: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      margin-bottom: 2rem;
      border: 1px solid rgba(255, 255, 255, 0.3);
      transition: transform 0.6s cubic-bezier(0.25, 0.1, 0.25, 1), 
                  box-shadow 0.6s ease;
      will-change: transform, opacity;
      backface-visibility: hidden;
      perspective: 1000px;
    }
    
    @keyframes fadeInUp {
      0% {
        opacity: 0;
        transform: translate3d(0, 50px, 0);
      }
      100% {
        opacity: 1;
        transform: translate3d(0, 0, 0);
      }
    }
    
    /* 流暢懸停效果 */
    section:hover {
      transform: scale(1.02) translate3d(0, 0, 0) !important;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15) !important;
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
      will-change: transform;
      backface-visibility: hidden;
    }

    /* ===================== */
    /* 漸變色按鈕新樣式 (主要修改部分) */
    /* ===================== */
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
      transition: all 0.6s cubic-bezier(0.25, 0.1, 0.25, 1);
      position: relative;
      overflow: hidden;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
      transform: translate3d(0, 0, 0);
      background-size: 200% auto;
      will-change: transform, box-shadow, background-position;
      backface-visibility: hidden;
    }
    
    .school-btn {
      background-image: linear-gradient(135deg, #2ecc71 0%, #27ae60 50%, #2ecc71 100%);
    }
    .school-btn:hover {
      background-position: right center;
      transform: translate3d(0, -3px, 0);
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }
    
    .location-btn {
      background-image: linear-gradient(135deg, #3498db 0%, #2980b9 50%, #3498db 100%);
    }
    .location-btn:hover {
      background-position: right center;
      transform: translate3d(0, -3px, 0);
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }
    
    .back-to-top {
      background-image: linear-gradient(135deg, #9b59b6 0%, #8e44ad 50%, #9b59b6 100%);
      display: none;
      opacity: 0;
      transition: opacity 0.4s ease;
    }
    .back-to-top:hover {
      background-position: right center;
      transform: translate3d(0, -3px, 0);
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }
    
    /* iOS風格點擊反饋 */
    .btn-container a:active {
      transform: translate3d(0, 1px, 0) scale(0.98);
      transition-duration: 0.1s;
    }
    
    /* 按鈕光暈效果 */
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
      opacity: 0;
      transition: opacity 0.3s;
    }
    .school-btn:hover::after, 
    .location-btn:hover::after {
      opacity: 1;
    }

    main {
      max-width: 1000px;
      margin: 0 auto;
      padding: 1rem;
      transform: translate3d(0, 0, 0);
    }

    /* 重要事項樣式 */
    .event-item {
      text-align: center;
      margin: 1rem 0;
      padding: 0.8rem;
      background: rgba(255,255,255,0.6);
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
      transition: transform 0.3s ease;
      will-change: transform;
    }
    .event-item:hover {
      transform: translate3d(0, -2px, 0);
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
      transition: all 0.6s cubic-bezier(0.25, 0.1, 0.25, 1);
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      transform: translate3d(0, 0, 0);
      will-change: transform, background;
    }
    .contact-email:hover {
      background: rgba(52, 152, 219, 0.2);
      transform: translate3d(0, -3px, 0);
      box-shadow: 0 4px 8px rgba(0,0,0,0.15);
    }

    /* 頁尾 */
    footer {
      text-align: center;
      font-size: 0.9rem;
      will-change: transform, opacity;
    }

    /* 內容居中樣式 */
    .centered-content {
      text-align: center;
      padding: 1rem 0;
    }

    /* 水波紋效果 */
    .ripple-effect {
      position: fixed;
      width: 20px;
      height: 20px;
      background: rgba(255,255,255,0.6);
      border-radius: 50%;
      transform: translate3d(-50%, -50%, 0) scale(0);
      animation: ripple 1s cubic-bezier(0.42, 0, 0.58, 1);
      pointer-events: none;
      z-index: 1000;
    }
    
    @keyframes ripple {
      to {
        transform: translate3d(-50%, -50%, 0) scale(10);
        opacity: 0;
      }
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
      
      /* 手機端減少粒子數量 */
      #particles-js .particle {
        display: none;
      }
      #particles-js .particle:nth-child(3n) {
        display: block;
      }
    }
  </style>
</head>
<body>
  <!-- 高性能粒子背景 -->
  <div id="particles-js"></div>
  
  <!-- 右上角漸變色按鈕 -->
  <div class="btn-container">
    <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" class="school-btn" target="_blank">進入學校網站</a>
    <a href="https://www.google.com/maps?q=928屏東縣東港鎮東新路1號" class="location-btn" target="_blank">學校位置查看</a>
  </div>
  
  <!-- 漸變色返回頂部按鈕 -->
  <a href="#" class="back-to-top">↑ 返回頂部</a>

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
    // 高性能粒子系統
    class ParticleSystem {
      constructor() {
        this.particles = [];
        this.container = document.getElementById('particles-js');
        this.resizeObserver = new ResizeObserver(() => this.resize());
        this.resizeObserver.observe(document.body);
        this.init();
        this.animate();
      }

      init() {
        this.container.innerHTML = '';
        const count = Math.min(window.innerWidth / 3, 150);
        
        for (let i = 0; i < count; i++) {
          const particle = document.createElement('div');
          particle.className = 'particle';
          
          // 初始屬性
          const size = Math.random() * 3 + 1;
          const opacity = Math.random() * 0.4 + 0.1;
          
          Object.assign(particle.style, {
            width: `${size}px`,
            height: `${size}px`,
            left: `${Math.random() * 100}vw`,
            top: `${Math.random() * 100}vh`,
            opacity: opacity,
            position: 'absolute',
            'border-radius': '50%',
            'pointer-events': 'none',
            'background-color': 'rgba(255,255,255,0.6)',
            'transform': 'translateZ(0)',
            'will-change': 'transform'
          });
          
          this.particles.push({
            el: particle,
            x: Math.random() * window.innerWidth,
            y: Math.random() * window.innerHeight,
            speedX: (Math.random() - 0.5) * 0.3,
            speedY: (Math.random() - 0.5) * 0.3
          });
          
          this.container.appendChild(particle);
        }
      }

      animate() {
        const update = () => {
          for (const p of this.particles) {
            p.x += p.speedX;
            p.y += p.speedY;
            
            // 邊界檢查
            if (p.x > window.innerWidth) p.x = 0;
            if (p.x < 0) p.x = window.innerWidth;
            if (p.y > window.innerHeight) p.y = 0;
            if (p.y < 0) p.y = window.innerHeight;
            
            p.el.style.transform = `translate3d(${p.x}px, ${p.y}px, 0)`;
          }
          requestAnimationFrame(update);
        };
        update();
      }

      resize() {
        this.init();
      }
    }

    // 滾動動畫控制器
    class ScrollAnimator {
      constructor() {
        this.lastScrollY = 0;
        this.ticking = false;
        this.backToTop = document.querySelector('.back-to-top');
        this.sections = document.querySelectorAll('section, footer');
        
        window.addEventListener('scroll', () => this.requestTick(), { passive: true });
        window.addEventListener('resize', () => this.requestTick(), { passive: true });
        
        // 初始動畫觸發
        this.requestTick();
      }
      
      requestTick() {
        if (!this.ticking) {
          requestAnimationFrame(() => this.update());
          this.ticking = true;
        }
      }
      
      update() {
        const scrollY = window.scrollY;
        
        // 返回頂部按鈕
        this.backToTop.style.display = scrollY > 300 ? 'block' : 'none';
        this.backToTop.style.opacity = Math.min(scrollY / 300, 1);
        
        // 視差效果
        const parallaxFactor = 0.3;
        document.getElementById('particles-js').style.transform = 
          `translate3d(0, ${scrollY * parallaxFactor}px, 0)`;
        
        // 區塊動畫
        this.sections.forEach(section => {
          const rect = section.getBoundingClientRect();
          const viewportHeight = window.innerHeight;
          
          if (rect.top < viewportHeight * 0.75) {
            section.style.opacity = 1;
            section.style.transform = 'translate3d(0, 0, 0)';
          }
        });
        
        this.ticking = false;
      }
    }

    // 動畫性能監控
    class AnimationMonitor {
      constructor() {
        this.frames = [];
        this.lastTime = performance.now();
        this.monitor();
      }
      
      monitor() {
        const now = performance.now();
        const delta = now - this.lastTime;
        this.lastTime = now;
        
        this.frames.push(delta);
        if (this.frames.length > 60) this.frames.shift();
        
        const avg = this.frames.reduce((a, b) => a + b) / this.frames.length;
        const fps = 1000 / avg;
        
        if (fps < 50) {
          console.warn(`動畫性能下降: ${fps.toFixed(1)} FPS`);
        }
        
        requestAnimationFrame(() => this.monitor());
      }
    }

    // 高性能初始化
    document.addEventListener('DOMContentLoaded', () => {
      // 使用微任務優化初始渲染
      setTimeout(() => {
        new ParticleSystem();
        new ScrollAnimator();
        
        // 預加載關鍵資源
        const preload = () => {
          const img = new Image();
          img.src = 'https://images.unsplash.com/photo-1506744038136-46273834b3fb';
        };
        
        if ('requestIdleCallback' in window) {
          requestIdleCallback(preload);
        } else {
          setTimeout(preload, 500);
        }

        // 在開發環境啟用性能監控
        if (process.env.NODE_ENV === 'development') {
          new AnimationMonitor();
        }
      }, 0);
      
      // 平滑滾動到錨點
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
          e.preventDefault();
          const target = document.querySelector(this.getAttribute('href'));
          if (target) {
            target.scrollIntoView({
              behavior: 'smooth',
              block: 'start'
            });
          }
        });
      });

      // 點擊水波紋效果
      document.addEventListener('click', (e) => {
        const ripple = document.createElement('div');
        ripple.className = 'ripple-effect';
        ripple.style.left = `${e.clientX}px`;
        ripple.style.top = `${e.clientY}px`;
        document.body.appendChild(ripple);
        setTimeout(() => ripple.remove(), 1000);
      });
    });
  </script>
</body>
</html>
