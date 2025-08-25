<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DSJH 805 班級網站</title>
    <meta name="description" content="東新國中805班官方網站，提供課表、公告與聯絡資訊">
    <meta name="keywords" content="東新國中,805班,班級網站,課表,班級公告">
    <meta property="og:title" content="東新國中805班級官方網站">
    <meta property="og:description" content="東新國中805班的官方網站，提供最新課表、班級公告和聯絡資訊">
    <style>
        /* ===================== 全局設定 ===================== */
        :root {
            --primary-color: #3498db;
            --secondary-color: #2ecc71;
            --accent-color: #ff7e5f;
            --text-color: #333;
            --light-bg: rgba(255, 255, 255, 0.85);
            --shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }
        
        * { 
            box-sizing: border-box; 
            margin: 0; 
            padding: 0; 
            scroll-behavior: smooth; 
        }
        
        body {
            background-color: #f2f2f2;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            font-size: 16px;
            color: var(--text-color);
            overflow-x: hidden;
            min-height: 100vh;
            padding-bottom: 4rem;
        }

        /* ===================== 歡迎介面 ===================== */
        #welcome-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            z-index: 2000;
            color: #fff;
            transition: opacity 1.2s cubic-bezier(0.23, 1, 0.32, 1);
        }

        #welcome-screen h1 {
            font-size: 2.8rem;
            margin-bottom: 2.5rem;
            animation: slideDown 1.2s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            opacity: 0;
            transform: translateY(-40px);
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }

        #welcome-screen #enter-btn {
            padding: 1.2rem 3.5rem;
            font-size: 1.3rem;
            border: none;
            border-radius: 35px;
            cursor: pointer;
            background: rgba(255, 255, 255, 0.95);
            color: var(--primary-color);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            animation: buttonPulse 2s infinite alternate;
            margin-bottom: 3.5rem;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            font-weight: 600;
            letter-spacing: 1px;
        }

        #welcome-screen #enter-btn:hover {
            transform: scale(1.12) translateY(-3px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
        }

        #welcome-screen .btn-container {
            position: absolute;
            top: 25px;
            right: 25px;
            display: flex;
            flex-direction: column;
            gap: 12px;
            opacity: 0;
            transform: translateX(60px);
            transition: all 1s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        
        #welcome-screen .school-btn, 
        #welcome-screen .location-btn {
            padding: 0.8rem 1.5rem;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            text-decoration: none;
            font-size: 1rem;
            text-align: center;
            color: #fff;
            user-select: none;
            position: relative;
            overflow: hidden;
            box-shadow: 0 5px 18px rgba(0, 0, 0, 0.2);
            transform: translate3d(0, 0, 0);
            background-size: 200% auto;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            font-weight: 500;
        }
        
        #welcome-screen .school-btn { 
            background-image: linear-gradient(135deg, #2ecc71, #27ae60, #2ecc71);
        }
        
        #welcome-screen .school-btn:hover { 
            background-position: right center; 
            transform: translate3d(0, -4px, 0); 
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.25);
        }
        
        #welcome-screen .location-btn { 
            background-image: linear-gradient(135deg, #3498db, #2980b9, #3498db);
        }
        
        #welcome-screen .location-btn:hover { 
            background-position: right center; 
            transform: translate3d(0, -4px, 0); 
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.25);
        }

        #welcome-screen .transparent-footer {
            position: absolute;
            bottom: 15px;
            opacity: 0.4;
            font-size: 0.9rem;
        }

        /* ===================== 進入動畫 ===================== */
        @keyframes slideDown { 
            from { 
                transform: translateY(-40px); 
                opacity: 0; 
            } 
            to { 
                transform: translateY(0); 
                opacity: 1; 
            } 
        }
        
        @keyframes buttonPulse { 
            from { 
                transform: scale(1); 
                box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            } 
            to { 
                transform: scale(1.08); 
                box-shadow: 0 12px 30px rgba(0, 0, 0, 0.25);
            } 
        }

        /* ===================== 頁首 ===================== */
        header {
            text-align: center;
            margin: 2.5rem auto 1.5rem;
            backdrop-filter: blur(16px) saturate(180%);
            -webkit-backdrop-filter: blur(16px) saturate(180%);
            background-color: var(--light-bg);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 2rem;
            max-width: 800px;
            position: relative;
            box-shadow: var(--shadow);
            will-change: transform, opacity;
            backface-visibility: hidden;
            opacity: 0;
            transform: translateY(-40px);
            transition: all 1.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        
        header h1 {
            font-size: 2.5rem;
            color: var(--primary-color);
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        /* ===================== 粒子背景 ===================== */
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
            opacity: 0.7;
        }

        /* ===================== 主要內容區 ===================== */
        #main-content { 
            max-width: 1000px; 
            margin: 0 auto; 
            padding: 1.5rem; 
            transform: translate3d(0, 0, 0); 
            opacity: 0; 
            transition: opacity 1.2s cubic-bezier(0.175, 0.885, 0.32, 1.275); 
            display: none; 
        }

        /* ===================== Section 動畫效果 ===================== */
        section {
            opacity: 0;
            transform: translate3d(0, 50px, 0);
            backdrop-filter: blur(16px) saturate(180%);
            -webkit-backdrop-filter: blur(16px) saturate(180%);
            background-color: var(--light-bg);
            border-radius: 16px;
            padding: 2rem;
            box-shadow: var(--shadow);
            margin-bottom: 2.5rem;
            border: 1px solid rgba(255, 255, 255, 0.3);
            transition: transform 1s cubic-bezier(0.175, 0.885, 0.32, 1.275), 
                        box-shadow 0.8s ease, 
                        opacity 1s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            will-change: transform, opacity;
            backface-visibility: hidden;
            position: relative;
            overflow: hidden;
        }

        /* 區塊漸層光影 */
        section::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at var(--gradient-x) var(--gradient-y), 
                        rgba(52, 152, 219, 0.15), rgba(255, 255, 255, 0));
            opacity: var(--gradient-opacity);
            transition: opacity 0.8s ease;
            pointer-events: none;
            z-index: -1;
        }

        section:hover { 
            transform: scale(1.02) translateZ(0); 
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.15); 
        }

        section h2 {
            color: var(--primary-color);
            margin-bottom: 1.5rem;
            text-align: center;
            font-size: 1.8rem;
            position: relative;
            padding-bottom: 0.5rem;
        }

        section h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            border-radius: 3px;
        }

        /* ===================== 即將上線樣式 ===================== */
        .coming-soon {
            text-align: center;
            padding: 3rem 2rem;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 12px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
            transition: all 0.5s ease;
        }

        .coming-soon:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.08);
        }

        .coming-soon-icon {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            display: block;
            color: var(--accent-color);
            animation: float 3s ease-in-out infinite;
        }

        .coming-soon-text {
            font-size: 1.5rem;
            color: #555;
            margin-bottom: 1rem;
            font-weight: 500;
        }

        .coming-soon-date {
            font-size: 1.2rem;
            color: var(--primary-color);
            background: rgba(52, 152, 219, 0.1);
            display: inline-block;
            padding: 0.5rem 1.2rem;
            border-radius: 20px;
            font-weight: 600;
        }

        /* ===================== 班級活動 ===================== */
        .event-item {
            text-align: center;
            margin: 1.2rem 0;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 10px;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.05);
            transition: transform 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            will-change: transform;
        }
        
        .event-item:hover { 
            transform: translate3d(0, -5px, 0); 
        }

        /* ===================== 聯絡方式 ===================== */
        .contact-container {
            text-align: center;
            margin-top: 1.5rem;
        }
        
        .contact-email {
            display: inline-block;
            background: rgba(255, 255, 255, 0.7);
            padding: 1rem 2rem;
            border-radius: 35px;
            color: var(--primary-color);
            text-decoration: none;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            pointer-events: none;
            font-weight: 500;
        }

        /* ===================== 底部區塊 ===================== */
        .footer-block {
            width: 100%;
            text-align: center;
            font-size: 0.9rem;
            color: #555;
            background-color: var(--light-bg);
            padding: 1rem 0;
            border-top: 1px solid rgba(0, 0, 0, 0.1);
            position: fixed;
            bottom: 0;
            left: 0;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            z-index: 100;
        }

        /* ===================== 漣漪效果 ===================== */
        .ripple-effect {
            position: fixed;
            width: 20px;
            height: 20px;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 50%;
            transform: translate3d(-50%, -50%, 0) scale(0);
            animation: ripple 1.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            pointer-events: none;
            z-index: 1000;
        }
        
        @keyframes ripple { 
            to { 
                transform: translate3d(-50%, -50%, 0) scale(12); 
                opacity: 0; 
            } 
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* ===================== 手機響應 ===================== */
        @media (max-width: 768px) {
            header, section {
                margin: 1.2rem;
                padding: 1.5rem;
            }
            
            .btn-container {
                top: 15px;
                right: 15px;
            }
            
            section:hover { 
                transform: none !important;
            }
            
            #particles-js canvas {
                opacity: 0.5;
            }
            
            section::after {
                display: none;
            }
            
            #welcome-screen #enter-btn {
                padding: 1rem 2.5rem;
                font-size: 1.1rem;
            }
            
            #welcome-screen h1 {
                font-size: 2.2rem;
            }
            
            .coming-soon {
                padding: 2rem 1.5rem;
            }
            
            .coming-soon-icon {
                font-size: 3rem;
            }
            
            .coming-soon-text {
                font-size: 1.3rem;
            }
            
            .coming-soon-date {
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>

    <!-- 歡迎介面 -->
    <div id="welcome-screen">
        <h1>歡迎進入DSJH805Class網站</h1>
        <button id="enter-btn">進入網站</button>
        <div class="btn-container">
            <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" class="school-btn" target="_blank" rel="noopener noreferrer">進入學校網站</a>
            <a href="https://www.google.com/maps?q=928屏東縣東港鎮東新路1號" class="location-btn" target="_blank" rel="noopener noreferrer">學校位置查看</a>
        </div>
        <div class="transparent-footer">此網站非東新國中官方製作</div>
    </div>

    <!-- 粒子背景 -->
    <div id="particles-js"></div>

    <!-- 頁首 -->
    <header role="banner">
        <h1 id="title" aria-label="東新國中805班級網站">DSJH 805 班級網站</h1>
    </header>

    <!-- 主要內容 -->
    <main id="main-content">
        <section id="schedule">
            <h2>課表</h2>
            <div class="coming-soon">
                <span class="coming-soon-icon">📚</span>
                <div class="coming-soon-text">內容準備中</div>
                <div class="coming-soon-date">9/1 將同開學上線</div>
            </div>
        </section>

        <section id="officers">
            <h2>班級幹部</h2>
            <div class="coming-soon">
                <span class="coming-soon-icon">👥</span>
                <div class="coming-soon-text">內容準備中</div>
                <div class="coming-soon-date">9/1 將同開學上線</div>
            </div>
        </section>

        <section id="important">
            <h2>重要事項</h2>
            <p style="text-align:center; font-size:0.9rem; color:#666;">（可直接修改 JSON 檔案更新）</p>
            <hr style="width:60%; margin:1.2rem auto; border:0; border-top:1px solid rgba(0,0,0,0.1);">
            <div id="event-list"></div>
        </section>

        <section id="photos">
            <h2>班級照片</h2>
            <div class="coming-soon">
                <span class="coming-soon-icon">📷</span>
                <div class="coming-soon-text">內容準備中</div>
                <div class="coming-soon-date">9/1 將同開學上線</div>
            </div>
        </section>

        <section id="contact">
            <h2>作者聯絡方式</h2>
            <div class="contact-container">
                <span class="contact-email">lianyuqing169@gmail.com</span>
            </div>
            <p style="text-align:center; color:#666; font-size:0.95rem; margin-top:1.2rem;">
                請聯絡時將所有事情一次打好，請勿重複傳送 Gmail。
            </p>
        </section>
    </main>

    <!-- 底部文字區塊 -->
    <div class="footer-block">此網站非東新國中官方製作</div>

    <script>
        // ===================== 重要事項 JSON =====================
        const eventsData = [
            { "date": "8/28", "text": "新生訓練" },
            { "date": "8/29", "text": "全校返校日" },
            { "date": "9/1", "text": "正式開學" },
            { "date": "1/20", "text": "寒假開始" }
        ];

        // ===================== 生成公告列表 =====================
        function renderEvents() {
            const eventList = document.getElementById('event-list');
            eventList.innerHTML = '';
            eventsData.forEach(event => {
                const div = document.createElement('div');
                div.className = 'event-item';
                div.innerHTML = `<span style="color:var(--accent-color); margin-right:8px;">📌</span> ${event.date} ${event.text}`;
                eventList.appendChild(div);
            });
        }

        // ===================== 粒子系統 =====================
        class ParticleSystem {
            constructor() {
                this.canvas = document.createElement('canvas');
                this.ctx = this.canvas.getContext('2d');
                this.container = document.getElementById('particles-js');
                this.container.appendChild(this.canvas);
                this.particles = this.createParticles();
                this.resize();
                this.animate();
                this.debouncedResize = this.debounce(() => this.resize(), 100);
                window.addEventListener('resize', this.debouncedResize, { passive: true });
            }
            
            createParticles() {
                const count = Math.min(Math.floor(window.innerWidth / 4), 150);
                return Array.from({ length: count }, () => {
                    const colors = ['#ff9ff3', '#feca57', '#48dbfb', '#1dd1a1', '#5f27cd'];
                    return {
                        x: Math.random() * window.innerWidth,
                        y: Math.random() * window.innerHeight,
                        size: Math.random() * 3 + 1,
                        speedX: (Math.random() - 0.5) * 0.2,
                        speedY: (Math.random() - 0.5) * 0.2,
                        opacity: Math.random() * 0.4 + 0.1,
                        color: colors[Math.floor(Math.random() * colors.length)]
                    };
                });
            }
            
            resize() { 
                this.canvas.width = this.container.offsetWidth; 
                this.canvas.height = this.container.offsetHeight; 
            }
            
            animate() {
                this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);
                this.particles.forEach(p => {
                    p.x += p.speedX; 
                    p.y += p.speedY;
                    if (p.x > this.canvas.width) p.x = 0;
                    if (p.x < 0) p.x = this.canvas.width;
                    if (p.y > this.canvas.height) p.y = 0;
                    if (p.y < 0) p.y = this.canvas.height;
                    
                    this.ctx.fillStyle = `rgba(${this.hexToRgb(p.color)}, ${p.opacity})`;
                    this.ctx.beginPath();
                    this.ctx.arc(p.x, p.y, p.size, 0, Math.PI * 2);
                    this.ctx.fill();
                });
                requestAnimationFrame(() => this.animate());
            }
            
            hexToRgb(hex) { 
                const c = hex.substring(1).match(/.{2}/g).map(x => parseInt(x, 16)); 
                return c.join(','); 
            }
            
            debounce(func, wait) { 
                let timeout; 
                return function() { 
                    const context = this, args = arguments; 
                    clearTimeout(timeout); 
                    timeout = setTimeout(() => func.apply(context, args), wait); 
                }; 
            }
        }

        // ===================== 滾動動畫 =====================
        class ScrollAnimator {
            constructor() {
                this.sections = document.querySelectorAll('section');
                this.hasAnimated = new Set();
                window.addEventListener('scroll', () => this.update(), { passive: true });
                this.update();
            }
            
            update() {
                this.sections.forEach(section => {
                    const rect = section.getBoundingClientRect();
                    if (rect.top < window.innerHeight * 0.75 && !this.hasAnimated.has(section)) {
                        this.hasAnimated.add(section);
                        section.style.opacity = 1;
                        section.style.transform = 'translate3d(0, 0, 0)';
                    }
                });
            }
        }

        // ===================== 漸層跟隨效果 =====================
        class GradientEffect {
            constructor() {
                this.sections = document.querySelectorAll('section');
                this.sections.forEach(section => {
                    section.addEventListener('mousemove', e => this.handleMouseMove(e, section));
                    section.addEventListener('mouseenter', () => section.style.setProperty('--gradient-opacity', '0.8'));
                    section.addEventListener('mouseleave', () => section.style.setProperty('--gradient-opacity', '0'));
                });
            }
            
            handleMouseMove(e, section) {
                const rect = section.getBoundingClientRect();
                const x = ((e.clientX - rect.left) / rect.width) * 100;
                const y = ((e.clientY - rect.top) / rect.height) * 100;
                section.style.setProperty('--gradient-x', `${x}%`);
                section.style.setProperty('--gradient-y', `${y}%`);
            }
        }

        // ===================== 漣漪效果 =====================
        class RippleEffect {
            constructor() { 
                document.addEventListener('click', e => {
                    const ripple = document.createElement('div'); 
                    ripple.className = 'ripple-effect';
                    ripple.style.left = e.clientX + 'px'; 
                    ripple.style.top = e.clientY + 'px';
                    document.body.appendChild(ripple);
                    setTimeout(() => document.body.removeChild(ripple), 1200);
                }); 
            }
        }

        // ===================== 歡迎頁進入動畫 =====================
        document.addEventListener('DOMContentLoaded', () => {
            renderEvents();
            new ParticleSystem();
            new ScrollAnimator();
            new GradientEffect();
            new RippleEffect();

            const welcome = document.getElementById('welcome-screen');
            const main = document.getElementById('main-content');
            const enterBtn = document.getElementById('enter-btn');

            enterBtn.addEventListener('click', () => {
                welcome.style.opacity = '0';
                
                setTimeout(() => {
                    welcome.style.display = 'none';
                    main.style.display = 'block';
                    
                    // 使用requestAnimationFrame确保流畅的动画
                    requestAnimationFrame(() => {
                        main.style.opacity = '1';
                        
                        // header显示动画
                        const header = document.querySelector('header');
                        header.style.opacity = '1';
                        header.style.transform = 'translateY(0)';
                        
                        // section逐个显示动画
                        const sections = document.querySelectorAll('main section');
                        sections.forEach((section, i) => {
                            setTimeout(() => {
                                section.style.opacity = '1';
                                section.style.transform = 'translate3d(0, 0, 0)';
                            }, 300 + (i * 200)); //  staggered animation
                        });
                        
                        // 右上按钮显示
                        document.querySelector('.btn-container').style.opacity = '1';
                        document.querySelector('.btn-container').style.transform = 'translateX(0)';
                    });
                }, 1000);
            });
        });
    </script>
</body>
</html>
