<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>東新國中805班級網站 - 淺藍風格</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4a86e8;
            --primary-light: #6fa3ef;
            --primary-dark: #3a6bc0;
            --secondary: #87ceeb;
            --accent: #5c9ead;
            --light: #f0f8ff;
            --dark: #2c3e50;
            --success: #5cb85c;
            --warning: #f0ad4e;
            --danger: #d9534f;
            --gray: #a0aec0;
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #e6f7ff 0%, #c3e6fc 100%);
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 30px;
            width: 100%;
        }
        
        /* 歡迎畫面 - 灰白色霧面玻璃效果 */
        #welcome-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(245, 245, 245, 0.8);
            backdrop-filter: blur(10px);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            z-index: 1000;
            color: var(--dark);
            transition: opacity 0.8s ease;
            padding: 20px;
        }
        
        .welcome-content {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(15px);
            padding: 60px 40px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            width: 100%;
            border: 1px solid rgba(255, 255, 255, 0.5);
        }
        
        #welcome-screen h1 {
            font-size: 3.5rem;
            margin-bottom: 25px;
            color: var(--primary);
        }
        
        #welcome-screen p {
            font-size: 1.4rem;
            margin-bottom: 40px;
            color: var(--dark);
            opacity: 0.9;
            line-height: 1.8;
        }
        
        #enter-btn {
            padding: 18px 50px;
            font-size: 1.4rem;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            font-weight: 600;
            margin-bottom: 30px;
        }
        
        #enter-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.3);
            background: var(--primary-dark);
        }
        
        .welcome-buttons {
            display: flex;
            gap: 20px;
            margin-top: 40px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .welcome-btn {
            padding: 15px 30px;
            background: rgba(255, 255, 255, 0.6);
            color: var(--dark);
            text-decoration: none;
            border-radius: 50px;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 500;
            border: 1px solid rgba(255, 255, 255, 0.5);
            font-size: 1.1rem;
        }
        
        .welcome-btn:hover {
            background: rgba(255, 255, 255, 0.9);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* 導航欄 */
        header {
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .nav-links {
            display: flex;
            gap: 25px;
        }
        
        .nav-links a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            padding: 8px 15px;
            border-radius: 20px;
        }
        
        .nav-links a:hover, .nav-links a.active {
            background: var(--primary);
            color: white;
        }
        
        /* 主內容區 */
        .hero {
            padding: 100px 0;
            text-align: center;
            background: linear-gradient(135deg, rgba(122, 186, 255, 0.15) 0%, rgba(96, 163, 248, 0.15) 100%);
            margin-bottom: 60px;
            width: 100%;
        }
        
        .hero h1 {
            font-size: 3.2rem;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto;
            color: var(--dark);
            opacity: 0.8;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            color: var(--primary);
            font-size: 2.5rem;
            position: relative;
            padding-bottom: 15px;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 5px;
            background: var(--accent);
            border-radius: 3px;
        }
        
        /* 卡片樣式 */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-bottom: 80px;
            width: 100%;
        }
        
        .card {
            background: rgba(255, 255, 255, 0.85);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.5);
        }
        
        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .card-header {
            background: var(--primary);
            color: white;
            padding: 25px;
            text-align: center;
            font-size: 1.6rem;
            font-weight: 600;
        }
        
        .card-body {
            padding: 30px;
            text-align: center;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        /* 班級幹部表格樣式 */
        .officers-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px auto;
            max-width: 700px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            overflow: hidden;
            background: white;
        }
        
        .officers-table th, .officers-table td {
            padding: 18px;
            text-align: center;
            border-bottom: 1px solid rgba(0, 0, 0, 0.1);
            font-size: 1.1rem;
        }
        
        .officers-table th {
            background-color: rgba(74, 134, 232, 0.25);
            color: var(--primary);
            font-weight: 600;
        }
        
        .officers-table tr:last-child td {
            border-bottom: none;
        }
        
        .officers-table tr:hover {
            background-color: rgba(74, 134, 232, 0.08);
        }
        
        /* 暫不顯示內容樣式 */
        .no-content {
            text-align: center;
            padding: 40px 20px;
            width: 100%;
        }
        
        .no-content-icon {
            font-size: 4.5rem;
            color: var(--accent);
            margin-bottom: 25px;
            display: block;
            opacity: 0.7;
        }
        
        .no-content-text {
            font-size: 1.8rem;
            color: var(--dark);
            margin-bottom: 15px;
            font-weight: 500;
            opacity: 0.8;
        }
        
        /* 公告樣式 */
        .announcement-list {
            display: flex;
            flex-direction: column;
            gap: 25px;
            width: 100%;
        }
        
        .announcement {
            background: rgba(255, 255, 255, 0.7);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            display: flex;
            gap: 20px;
            align-items: flex-start;
        }
        
        .announcement-icon {
            background: var(--primary);
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            flex-shrink: 0;
        }
        
        .announcement-content h3 {
            margin-bottom: 10px;
            color: var(--primary);
            font-size: 1.4rem;
        }
        
        .announcement-date {
            color: var(--gray);
            font-size: 1rem;
            margin-top: 8px;
        }
        
        /* 聯絡樣式 */
        .contact-methods {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            justify-content: center;
            margin-top: 50px;
            width: 100%;
        }
        
        .contact-method {
            background: rgba(255, 255, 255, 0.85);
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            flex: 1;
            min-width: 300px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.5);
        }
        
        .contact-method:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.15);
        }
        
        .contact-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }
        
        .contact-method h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .contact-method p {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }
        
        .contact-method small {
            font-size: 1rem;
            color: var(--gray);
        }
        
        /* 頁腳 */
        footer {
            background: var(--dark);
            color: white;
            text-align: center;
            padding: 30px;
            margin-top: 100px;
            width: 100%;
        }
        
        footer p {
            font-size: 1.1rem;
        }
        
        /* 返回按鈕 */
        #back-to-welcome {
            position: fixed;
            top: 20px;
            right: 25px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            z-index: 101;
            transition: var(--transition);
            font-size: 1.4rem;
        }
        
        #back-to-welcome:hover {
            background: var(--primary-dark);
            transform: translateY(-3px) scale(1.05);
        }
        
        /* 響應式設計 */
        @media (max-width: 992px) {
            .welcome-content {
                padding: 40px 30px;
            }
            
            #welcome-screen h1 {
                font-size: 2.8rem;
            }
            
            #welcome-screen p {
                font-size: 1.2rem;
            }
            
            #enter-btn {
                padding: 15px 40px;
                font-size: 1.2rem;
            }
            
            .welcome-btn {
                padding: 12px 25px;
                font-size: 1rem;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .section-title {
                font-size: 2.2rem;
            }
            
            .card-grid {
                grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
                gap: 30px;
            }
        }
        
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
                gap: 15px;
            }
            
            .hero {
                padding: 80px 0;
            }
            
            .hero h1 {
                font-size: 2.3rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section-title {
                font-size: 2rem;
                margin-bottom: 40px;
            }
            
            .welcome-content {
                padding: 30px 20px;
            }
            
            #welcome-screen h1 {
                font-size: 2.3rem;
            }
            
            .card-grid {
                gap: 25px;
                margin-bottom: 60px;
            }
            
            .card-header {
                padding: 20px;
                font-size: 1.4rem;
            }
            
            .card-body {
                padding: 25px;
            }
            
            .officers-table th, .officers-table td {
                padding: 15px 12px;
                font-size: 1rem;
            }
            
            .contact-method {
                min-width: 250px;
                padding: 25px;
            }
            
            .welcome-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .welcome-btn {
                width: 100%;
                max-width: 300px;
                justify-content: center;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 0 20px;
            }
            
            .hero {
                padding: 60px 0;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .card-grid {
                grid-template-columns: 1fr;
            }
            
            .officers-table {
                font-size: 0.9rem;
            }
            
            .officers-table th, .officers-table td {
                padding: 12px 8px;
            }
            
            .no-content-text {
                font-size: 1.5rem;
            }
            
            .no-content-icon {
                font-size: 3.5rem;
            }
            
            #back-to-welcome {
                width: 50px;
                height: 50px;
                font-size: 1.2rem;
                top: 15px;
                right: 15px;
            }
        }
    </style>
</head>
<body>
    <!-- 歡迎畫面 -->
    <div id="welcome-screen">
        <div class="welcome-content">
            <h1>歡迎來到東新國中805班</h1>
            <p>我們是一個充滿活力與學習熱情的班級，這個網站將提供最新的班級資訊、課表、公告和活動照片。</p>
            <button id="enter-btn">進入網站</button>
            
            <div class="welcome-buttons">
                <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" class="welcome-btn" target="_blank">
                    <i class="fas fa-school"></i> 學校網站
                </a>
                <a href="https://www.google.com/maps?q=928屏東縣東港鎮東新路1號" class="welcome-btn" target="_blank">
                    <i class="fas fa-map-marker-alt"></i> 學校位置
                </a>
                <a href="mailto:lianyuqing169@gmail.com" class="welcome-btn">
                    <i class="fas fa-envelope"></i> 聯絡我們
                </a>
            </div>
        </div>
    </div>

    <!-- 返回歡迎畫面按鈕 -->
    <button id="back-to-welcome" title="返回歡迎畫面">
        <i class="fas fa-home"></i>
    </button>

    <!-- 導航欄 -->
    <header>
        <div class="container nav-container">
            <div class="logo">
                <i class="fas fa-graduation-cap"></i>
                <span>東新國中805班</span>
            </div>
            
            <nav class="nav-links">
                <a href="#schedule" class="active">課表</a>
                <a href="#officers">班級幹部</a>
                <a href="#announcements">重要公告</a>
                <a href="#gallery">班級相冊</a>
                <a href="#contact">聯絡我們</a>
            </nav>
        </div>
    </header>

    <!-- 主內容 -->
    <main>
        <!-- 英雄區域 -->
        <section class="hero">
            <div class="container">
                <h1>歡迎來到805班級網站</h1>
                <p>我們是一個積極向上、團結友愛的班集體，在這裡您可以找到所有關於我們班的資訊和動態。</p>
            </div>
        </section>

        <div class="container">
            <!-- 課表區域 -->
            <section id="schedule">
                <h2 class="section-title">課程表</h2>
                <div class="card">
                    <div class="card-header">805班 每週課表</div>
                    <div class="card-body">
                        <div class="no-content">
                            <i class="fas fa-calendar-alt no-content-icon"></i>
                            <div class="no-content-text">暫不顯示任何內容</div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 班級幹部區域 -->
            <section id="officers">
                <h2 class="section-title">班級幹部</h2>
                <div class="card">
                    <div class="card-header">805班 班級幹部名單</div>
                    <div class="card-body">
                        <table class="officers-table">
                            <tr>
                                <th>職務</th>
                                <th>座號</th>
                            </tr>
                            <tr>
                                <td>班長</td>
                                <td>12號</td>
                            </tr>
                            <tr>
                                <td>副班長</td>
                                <td>24號</td>
                            </tr>
                            <tr>
                                <td>風紀股長</td>
                                <td>2號</td>
                            </tr>
                            <tr>
                                <td>副風紀股長</td>
                                <td>17號</td>
                            </tr>
                            <tr>
                                <td>衛生股長</td>
                                <td>6號</td>
                            </tr>
                            <tr>
                                <td>副衛生股長</td>
                                <td>3號</td>
                            </tr>
                            <tr>
                                <td>總務股長</td>
                                <td>23號</td>
                            </tr>
                            <tr>
                                <td>副總務股長</td>
                                <td>18號</td>
                            </tr>
                            <tr>
                                <td>輔導股長</td>
                                <td>1號</td>
                            </tr>
                            <tr>
                                <td>午餐股長</td>
                                <td>25號</td>
                            </tr>
                            <tr>
                                <td>導師秘書</td>
                                <td>14號</td>
                            </tr>
                        </table>
                    </div>
                </div>
            </section>

            <!-- 重要公告區域 -->
            <section id="announcements">
                <h2 class="section-title">重要公告</h2>
                <div class="card">
                    <div class="card-header">最新公告</div>
                    <div class="card-body">
                        <div class="no-content">
                            <i class="fas fa-bullhorn no-content-icon"></i>
                            <div class="no-content-text">暫不顯示任何內容</div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 班級相冊區域 -->
            <section id="gallery">
                <h2 class="section-title">班級相冊</h2>
                <div class="card">
                    <div class="card-header">805班 活動照片</div>
                    <div class="card-body">
                        <div class="no-content">
                            <i class="fas fa-camera no-content-icon"></i>
                            <div class="no-content-text">暫不顯示任何內容</div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 聯絡我們區域 -->
            <section id="contact">
                <h2 class="section-title">聯絡我們</h2>
                <div class="contact-methods">
                    <div class="contact-method">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <h3>電子郵件</h3>
                        <p>lianyuqing169@gmail.com</p>
                        <small>請將所有事情一次說明清楚，請勿重複傳送郵件</small>
                    </div>
                    
                    <div class="contact-method">
                        <div class="contact-icon">
                            <i class="fas fa-school"></i>
                        </div>
                        <h3>學校地址</h3>
                        <p>928屏東縣東港鎮東新路1號</p>
                        <small>歡迎家長來校參觀與交流</small>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <!-- 頁腳 -->
    <footer>
        <div class="container">
            <p>此網站非東新國中官方製作 | 東新國中805班級網站</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const welcomeScreen = document.getElementById('welcome-screen');
            const enterBtn = document.getElementById('enter-btn');
            const backToWelcomeBtn = document.getElementById('back-to-welcome');
            
            // 進入網站按鈕事件
            enterBtn.addEventListener('click', function() {
                welcomeScreen.style.opacity = '0';
                setTimeout(() => {
                    welcomeScreen.style.display = 'none';
                }, 800);
            });
            
            // 返回歡迎畫面按鈕事件
            backToWelcomeBtn.addEventListener('click', function() {
                welcomeScreen.style.display = 'flex';
                setTimeout(() => {
                    welcomeScreen.style.opacity = '1';
                }, 10);
            });
            
            // 導航欄滾動效果
            const navLinks = document.querySelectorAll('.nav-links a');
            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    const targetSection = document.querySelector(targetId);
                    
                    // 更新活動狀態
                    navLinks.forEach(navLink => navLink.classList.remove('active'));
                    this.classList.add('active');
                    
                    // 滾動到目標區域
                    window.scrollTo({
                        top: targetSection.offsetTop - 100,
                        behavior: 'smooth'
                    });
                });
            });
            
            // 根據滾動位置更新導航欄活動狀態
            window.addEventListener('scroll', function() {
                const scrollPosition = window.scrollY;
                
                document.querySelectorAll('section').forEach(section => {
                    const sectionTop = section.offsetTop - 150;
                    const sectionBottom = sectionTop + section.offsetHeight;
                    const sectionId = section.getAttribute('id');
                    
                    if (scrollPosition >= sectionTop && scrollPosition < sectionBottom) {
                        navLinks.forEach(link => {
                            link.classList.remove('active');
                            if (link.getAttribute('href') === `#${sectionId}`) {
                                link.classList.add('active');
                            }
                        });
                    }
                });
            });
        });
    </script>
</body>
</html>
