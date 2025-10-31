<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DSJH805Class - 班级网站</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary-color: #3498db;
            --secondary-color: #2980b9;
            --background-color: #f8f9fa;
            --card-color: #ffffff;
            --text-color: #2c3e50;
            --shadow-color: rgba(0, 0, 0, 0.1);
            --transition-speed: 0.4s;
        }
        
        [data-theme="dark"] {
            --primary-color: #64b5f6;
            --secondary-color: #1e88e5;
            --background-color: #121212;
            --card-color: #1e1e1e;
            --text-color: #e0e0e0;
            --shadow-color: rgba(0, 0, 0, 0.3);
        }
        
        body {
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
            transition: background-color var(--transition-speed) ease, color var(--transition-speed) ease;
            font-size: 16px;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            padding: 30px 0;
            animation: fadeIn 1.2s ease;
            position: relative;
            display: flex;
            flex-direction: column;
        }
        
        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            flex: 1;
        }
        
        .logo-icon {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-right: 15px;
            transition: transform 0.5s ease;
        }
        
        .logo:hover .logo-icon {
            transform: rotate(15deg);
        }
        
        h1 {
            font-size: 2.8rem;
            color: var(--secondary-color);
            text-shadow: 2px 2px 4px var(--shadow-color);
            transition: color var(--transition-speed) ease;
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            transition: color var(--transition-speed) ease;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }
        
        .section {
            background: var(--card-color);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px var(--shadow-color);
            transition: transform 0.3s ease, box-shadow 0.3s ease, background-color var(--transition-speed) ease;
            position: relative;
            overflow: hidden;
        }
        
        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px var(--shadow-color);
        }
        
        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
        }
        
        .section-title {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            color: var(--secondary-color);
            font-size: 1.5rem;
            transition: color var(--transition-speed) ease;
        }
        
        .section-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: var(--primary-color);
            transition: color var(--transition-speed) ease;
        }
        
        .content-placeholder {
            text-align: center;
            padding: 30px 0;
            color: #7f8c8d;
        }
        
        .placeholder-icon {
            font-size: 3rem;
            color: #bdc3c7;
            margin-bottom: 15px;
        }
        
        .placeholder-text {
            font-style: italic;
        }
        
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: #7f8c8d;
            border-top: 1px solid rgba(52, 152, 219, 0.3);
        }
        
        /* 顶部按钮样式 */
        .top-buttons {
            display: flex;
            gap: 15px;
        }
        
        .top-button {
            padding: 10px 20px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px var(--shadow-color);
            display: flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
            white-space: nowrap;
        }
        
        .top-button:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 6px 12px var(--shadow-color);
        }
        
        .settings-button {
            background: #2ecc71;
        }
        
        .settings-button:hover {
            background: #27ae60;
        }
        
        /* 设置面板样式 */
        .settings-panel {
            position: fixed;
            top: 0;
            left: -400px;
            width: 380px;
            height: 100vh;
            background: var(--card-color);
            box-shadow: 5px 0 15px var(--shadow-color);
            padding: 30px;
            overflow-y: auto;
            z-index: 1000;
            transition: left 0.4s ease, background-color var(--transition-speed) ease;
        }
        
        .settings-panel.active {
            left: 0;
        }
        
        .settings-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 2px solid #f1f1f1;
        }
        
        .settings-title {
            font-size: 1.8rem;
            color: var(--secondary-color);
            transition: color var(--transition-speed) ease;
        }
        
        .close-settings {
            background: #e74c3c;
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .setting-group {
            margin-bottom: 25px;
        }
        
        .setting-label {
            display: block;
            margin-bottom: 10px;
            font-weight: 600;
            color: var(--text-color);
            transition: color var(--transition-speed) ease;
        }
        
        .theme-options {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        .theme-option {
            padding: 10px 20px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px var(--shadow-color);
        }
        
        .theme-option:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
        }
        
        .theme-option.active {
            background: var(--secondary-color);
            box-shadow: 0 0 0 2px white, 0 0 0 4px var(--secondary-color);
        }
        
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 999;
            display: none;
        }
        
        .overlay.active {
            display: block;
        }
        
        .disclaimer {
            text-align: center;
            margin-top: 40px;
            padding: 15px;
            background: #fff8e1;
            border-radius: 8px;
            font-size: 0.9rem;
            color: #e65100;
            border-left: 4px solid #ffc107;
        }
        
        [data-theme="dark"] .disclaimer {
            background: #332800;
            color: #ffb74d;
        }
        
        /* 语言选择器样式 */
        .language-selector {
            position: relative;
            display: inline-block;
        }
        
        .language-button {
            padding: 10px 20px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px var(--shadow-color);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .language-button:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 6px 12px var(--shadow-color);
        }
        
        .language-dropdown {
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            background: var(--card-color);
            border-radius: 8px;
            box-shadow: 0 10px 20px var(--shadow-color);
            overflow: hidden;
            z-index: 100;
            display: none;
            transition: all 0.3s ease;
        }
        
        .language-dropdown.active {
            display: block;
            animation: slideDown 0.3s ease;
        }
        
        .language-option {
            padding: 12px 20px;
            background: var(--card-color);
            color: var(--text-color);
            border: none;
            width: 100%;
            text-align: left;
            cursor: pointer;
            transition: background-color 0.2s ease;
        }
        
        .language-option:hover {
            background: rgba(52, 152, 219, 0.1);
        }
        
        /* 课表链接样式 */
        .class-table-link {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 40px 20px;
            text-align: center;
            text-decoration: none;
            color: var(--text-color);
            transition: all 0.3s ease;
        }
        
        .class-table-link:hover {
            transform: scale(1.05);
        }
        
        .class-table-icon {
            font-size: 4rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            transition: color var(--transition-speed) ease;
        }
        
        .class-table-title {
            font-size: 1.8rem;
            font-weight: bold;
            margin-bottom: 10px;
            color: var(--secondary-color);
            transition: color var(--transition-speed) ease;
        }
        
        .class-table-description {
            font-size: 1rem;
            color: #7f8c8d;
            max-width: 300px;
            margin-bottom: 20px;
        }
        
        .class-table-button {
            padding: 12px 30px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px var(--shadow-color);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .class-table-button:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 6px 12px var(--shadow-color);
        }
        
        /* 联系开发者样式 */
        .contact-developer {
            margin-top: 40px;
            background: var(--card-color);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px var(--shadow-color);
            text-align: center;
            transition: background-color var(--transition-speed) ease;
        }
        
        .contact-title {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            color: var(--secondary-color);
            font-size: 1.5rem;
            transition: color var(--transition-speed) ease;
        }
        
        .contact-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: var(--primary-color);
            transition: color var(--transition-speed) ease;
        }
        
        .contact-email {
            display: inline-block;
            margin: 15px 0;
            padding: 12px 25px;
            background: var(--background-color);
            border-radius: 30px;
            color: var(--secondary-color);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid rgba(52, 152, 219, 0.2);
        }
        
        .contact-email:hover {
            background: var(--primary-color);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.3);
        }
        
        .contact-note {
            margin-top: 15px;
            font-size: 0.9rem;
            color: #7f8c8d;
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* 平板设备样式 */
        @media (max-width: 1024px) {
            .main-content {
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }
            
            h1 {
                font-size: 2.4rem;
            }
            
            .section-title {
                font-size: 1.4rem;
            }
            
            .top-button {
                padding: 8px 16px;
                font-size: 0.9rem;
            }
        }
        
        /* 手机设备样式 */
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            .header-top {
                flex-direction: column;
                gap: 15px;
            }
            
            .top-buttons {
                width: 100%;
                justify-content: center;
            }
            
            .main-content {
                grid-template-columns: 1fr;
                gap: 15px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .subtitle {
                font-size: 1rem;
            }
            
            .section {
                padding: 20px;
            }
            
            .section-title {
                font-size: 1.3rem;
            }
            
            .settings-panel {
                width: 300px;
                left: -300px;
            }
            
            .top-button {
                width: 100%;
                justify-content: center;
            }
            
            .contact-developer {
                padding: 20px;
            }
        }
        
        /* 小手机设备样式 */
        @media (max-width: 480px) {
            h1 {
                font-size: 1.8rem;
            }
            
            .logo-icon {
                font-size: 2rem;
            }
            
            .section-title {
                font-size: 1.2rem;
            }
            
            .placeholder-icon {
                font-size: 2.5rem;
            }
            
            .settings-panel {
                width: 85%;
                left: -85%;
            }
            
            .contact-email {
                padding: 10px 20px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="header-top">
                <button class="top-button settings-button" id="settingsButton">
                    <i class="fas fa-cog"></i> <span data-lang="settings">設定</span>
                </button>
                
                <div class="logo">
                    <i class="fas fa-graduation-cap logo-icon"></i>
                    <h1>DSJH805Class</h1>
                </div>
                
                <div class="top-buttons">
                    <div class="language-selector">
                        <button class="language-button" id="languageButton">
                            <i class="fas fa-globe"></i> <span id="currentLanguage" data-lang="current">繁體中文</span>
                        </button>
                        <div class="language-dropdown" id="languageDropdown">
                            <button class="language-option" data-lang="zh-TW">繁體中文</button>
                            <button class="language-option" data-lang="zh-CN">简体中文</button>
                            <button class="language-option" data-lang="en">English</button>
                            <button class="language-option" data-lang="ja">日本語</button>
                            <button class="language-option" data-lang="ko">한국어</button>
                        </div>
                    </div>
                    
                    <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" target="_blank" class="top-button">
                        <i class="fas fa-school"></i> <span data-lang="school-website">進入校網</span>
                    </a>
                </div>
            </div>
            
            <p class="subtitle" data-lang="subtitle">我們的專屬班級空間 • 知識分享與交流的平台</p>
        </header>
        
        <div class="main-content">
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-bullhorn section-icon"></i>
                    <span data-lang="latest-notice">最新通知</span>
                </h2>
                <div class="content-placeholder">
                    <i class="fas fa-bell placeholder-icon"></i>
                    <p class="placeholder-text" data-lang="no-content">暫無內容或未開放</p>
                </div>
            </div>
            
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-table section-icon"></i>
                    <span data-lang="class-schedule">課表</span>
                </h2>
                <a href="http://163.24.48.25/classtable/" target="_blank" class="class-table-link">
                    <i class="fas fa-calendar-alt class-table-icon"></i>
                    <div class="class-table-title" data-lang="view-schedule">查看課表</div>
                    <div class="class-table-description" data-lang="schedule-description">
                        點擊此處查看八年五班的完整課表，請選擇「八年五班」查看詳細課程安排
                    </div>
                    <div class="class-table-button">
                        <i class="fas fa-external-link-alt"></i> <span data-lang="go-to-schedule">前往課表</span>
                    </div>
                </a>
            </div>
        </div>
        
        <!-- 联系开发者区块 -->
        <div class="contact-developer">
            <h2 class="contact-title">
                <i class="fas fa-envelope contact-icon"></i>
                <span data-lang="contact-developer">聯繫開發者</span>
            </h2>
            <p data-lang="contact-description">如果您有任何問題或建議，歡迎聯繫開發者：</p>
            <div class="contact-email">lianyuqing169@gmail.com</div>
            <p class="contact-note" data-lang="contact-note">點擊上方郵件地址將自動開啟Gmail發送郵件</p>
        </div>
        
        <!-- 免责声明 -->
        <div class="disclaimer">
            <i class="fas fa-exclamation-circle"></i> <span data-lang="disclaimer">此網站為學生個人製作，非學校官方製作</span>
        </div>
        
        <footer>
            <p>© 2025 DSJH805Class <span data-lang="footer-text">班級網站 - 僅供班級內部使用</span></p>
        </footer>
    </div>
    
    <!-- 设置面板 -->
    <div class="settings-panel" id="settingsPanel">
        <div class="settings-header">
            <h2 class="settings-title" data-lang="website-settings">網站設定</h2>
            <button class="close-settings" id="closeSettings">
                <i class="fas fa-times"></i>
            </button>
        </div>
        
        <div class="setting-group">
            <label class="setting-label" data-lang="theme">主題</label>
            <div class="theme-options">
                <button class="theme-option active" data-theme="light" data-lang="light-theme">淺色</button>
                <button class="theme-option" data-theme="dark" data-lang="dark-theme">深色</button>
                <button class="theme-option" data-theme="auto" data-lang="auto-theme">跟隨系統</button>
            </div>
        </div>
        
        <div class="setting-group">
            <label class="setting-label" data-lang="reset-settings">重設設定</label>
            <button class="top-button" id="resetSettings" style="background: #e74c3c;">
                <i class="fas fa-undo"></i> <span data-lang="reset-default">恢復預設值</span>
            </button>
        </div>
    </div>
    
    <div class="overlay" id="overlay"></div>

    <script>
        // DOM元素
        const settingsButton = document.getElementById('settingsButton');
        const closeSettings = document.getElementById('closeSettings');
        const settingsPanel = document.getElementById('settingsPanel');
        const overlay = document.getElementById('overlay');
        const themeOptions = document.querySelectorAll('.theme-option');
        const resetSettingsButton = document.getElementById('resetSettings');
        const languageButton = document.getElementById('languageButton');
        const languageDropdown = document.getElementById('languageDropdown');
        const languageOptions = document.querySelectorAll('.language-option');
        const currentLanguage = document.getElementById('currentLanguage');
        
        // 多语言文本
        const translations = {
            'zh-TW': {
                'settings': '設定',
                'current': '繁體中文',
                'school-website': '進入校網',
                'subtitle': '我們的專屬班級空間 • 知識分享與交流的平台',
                'latest-notice': '最新通知',
                'class-schedule': '課表',
                'no-content': '暫無內容或未開放',
                'view-schedule': '查看課表',
                'schedule-description': '點擊此處查看八年五班的完整課表，請選擇「八年五班」查看詳細課程安排',
                'go-to-schedule': '前往課表',
                'contact-developer': '聯繫開發者',
                'contact-description': '如果您有任何問題或建議，歡迎聯繫開發者：',
                'contact-note': '點擊上方郵件地址將自動開啟Gmail發送郵件',
                'disclaimer': '此網站為學生個人製作，非學校官方製作',
                'footer-text': '班級網站 - 僅供班級內部使用',
                'website-settings': '網站設定',
                'theme': '主題',
                'light-theme': '淺色',
                'dark-theme': '深色',
                'auto-theme': '跟隨系統',
                'reset-settings': '重設設定',
                'reset-default': '恢復預設值'
            },
            'zh-CN': {
                'settings': '设置',
                'current': '简体中文',
                'school-website': '进入校网',
                'subtitle': '我们的专属班级空间 • 知识分享与交流的平台',
                'latest-notice': '最新通知',
                'class-schedule': '课表',
                'no-content': '暂无内容或未开放',
                'view-schedule': '查看课表',
                'schedule-description': '点击此处查看八年五班的完整课表，请选择「八年五班」查看详细课程安排',
                'go-to-schedule': '前往课表',
                'contact-developer': '联系开发者',
                'contact-description': '如果您有任何问题或建议，欢迎联系开发者：',
                'contact-note': '点击上方邮件地址将自动开启Gmail发送邮件',
                'disclaimer': '此网站为学生个人制作，非学校官方制作',
                'footer-text': '班级网站 - 仅供班级内部使用',
                'website-settings': '网站设置',
                'theme': '主题',
                'light-theme': '浅色',
                'dark-theme': '深色',
                'auto-theme': '跟随系统',
                'reset-settings': '重设设置',
                'reset-default': '恢复默认值'
            },
            'en': {
                'settings': 'Settings',
                'current': 'English',
                'school-website': 'School Website',
                'subtitle': 'Our Exclusive Class Space • Platform for Knowledge Sharing and Exchange',
                'latest-notice': 'Latest Notice',
                'class-schedule': 'Class Schedule',
                'no-content': 'No content or not available',
                'view-schedule': 'View Schedule',
                'schedule-description': 'Click here to view the complete schedule for Class 8-5. Please select "Class 8-5" to view detailed course arrangements',
                'go-to-schedule': 'Go to Schedule',
                'contact-developer': 'Contact Developer',
                'contact-description': 'If you have any questions or suggestions, please contact the developer:',
                'contact-note': 'Click the email address above to automatically open Gmail',
                'disclaimer': 'This website is made by students, not officially by the school',
                'footer-text': 'Class Website - For Internal Use Only',
                'website-settings': 'Website Settings',
                'theme': 'Theme',
                'light-theme': 'Light',
                'dark-theme': 'Dark',
                'auto-theme': 'Follow System',
                'reset-settings': 'Reset Settings',
                'reset-default': 'Restore Default'
            },
            'ja': {
                'settings': '設定',
                'current': '日本語',
                'school-website': '学校のウェブサイト',
                'subtitle': '私たちの専用クラススペース • 知識共有と交流のプラットフォーム',
                'latest-notice': '最新のお知らせ',
                'class-schedule': '時間割',
                'no-content': 'コンテンツがありませんまたは利用できません',
                'view-schedule': '時間割を表示',
                'schedule-description': '8年5組の完全な時間割を表示するにはここをクリックしてください。詳細な授業手配を表示するには「8年5組」を選択してください',
                'go-to-schedule': '時間割へ',
                'contact-developer': '開発者に連絡',
                'contact-description': 'ご質問やご提案がある場合は、開発者までご連絡ください：',
                'contact-note': '上記のメールアドレスをクリックするとGmailが自動的に開きます',
                'disclaimer': 'このウェブサイトは学生が個人で作成したもので、学校公式のものではありません',
                'footer-text': 'クラスウェブサイト - 内部使用のみ',
                'website-settings': 'ウェブサイト設定',
                'theme': 'テーマ',
                'light-theme': 'ライト',
                'dark-theme': 'ダーク',
                'auto-theme': 'システムに従う',
                'reset-settings': '設定をリセット',
                'reset-default': 'デフォルトに戻す'
            },
            'ko': {
                'settings': '설정',
                'current': '한국어',
                'school-website': '학교 웹사이트',
                'subtitle': '우리의 전용 클래스 공간 • 지식 공유 및 교류 플랫폼',
                'latest-notice': '최신 공지',
                'class-schedule': '시간표',
                'no-content': '콘텐츠가 없거나 사용할 수 없음',
                'view-schedule': '시간표 보기',
                'schedule-description': '8학년 5반의 전체 시간표를 보려면 여기를 클릭하세요. 자세한 수업 일정을 보려면 "8학년 5반"을 선택하세요',
                'go-to-schedule': '시간표로 이동',
                'contact-developer': '개발자에게 문의',
                'contact-description': '질문이나 제안 사항이 있으면 개발자에게 연락해 주세요:',
                'contact-note': '위의 이메일 주소를 클릭하면 Gmail이 자동으로 열립니다',
                'disclaimer': '이 웹사이트는 학생이 개인적으로 제작한 것으로 학교 공식 제작물이 아닙니다',
                'footer-text': '클래스 웹사이트 - 내부 사용만',
                'website-settings': '웹사이트 설정',
                'theme': '테마',
                'light-theme': '라이트',
                'dark-theme': '다크',
                'auto-theme': '시스템 따라가기',
                'reset-settings': '설정 재설정',
                'reset-default': '기본값 복원'
            }
        };
        
        // 初始化
        document.addEventListener('DOMContentLoaded', function() {
            // 从本地存储加载设置
            loadSettings();
            
            // 加载语言设置
            loadLanguage();
        });
        
        // 打开设置面板
        settingsButton.addEventListener('click', function() {
            settingsPanel.classList.add('active');
            overlay.classList.add('active');
        });
        
        // 关闭设置面板
        closeSettings.addEventListener('click', function() {
            settingsPanel.classList.remove('active');
            overlay.classList.remove('active');
        });
        
        // 点击遮罩层关闭设置
        overlay.addEventListener('click', function() {
            settingsPanel.classList.remove('active');
            overlay.classList.remove('active');
        });
        
        // 主题选择
        themeOptions.forEach(option => {
            option.addEventListener('click', function() {
                // 移除所有active类
                themeOptions.forEach(opt => opt.classList.remove('active'));
                // 添加active类到当前选项
                this.classList.add('active');
                
                // 获取主题值
                const theme = this.getAttribute('data-theme');
                
                // 应用主题
                applyTheme(theme);
                
                // 保存到本地存储
                localStorage.setItem('theme', theme);
            });
        });
        
        // 应用主题
        function applyTheme(theme) {
            if (theme === 'auto') {
                // 跟随系统主题
                if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
                    document.documentElement.setAttribute('data-theme', 'dark');
                } else {
                    document.documentElement.setAttribute('data-theme', 'light');
                }
                
                // 监听系统主题变化
                if (window.matchMedia) {
                    window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', e => {
                        document.documentElement.setAttribute('data-theme', e.matches ? 'dark' : 'light');
                    });
                }
            } else {
                document.documentElement.setAttribute('data-theme', theme);
            }
        }
        
        // 重设设置
        resetSettingsButton.addEventListener('click', function() {
            // 重置主题
            document.documentElement.setAttribute('data-theme', 'light');
            
            // 重置主题选项
            themeOptions.forEach(option => {
                option.classList.remove('active');
                if (option.getAttribute('data-theme') === 'light') {
                    option.classList.add('active');
                }
            });
            
            // 重置语言
            changeLanguage('zh-TW');
            
            // 清除本地存储
            localStorage.removeItem('theme');
            localStorage.removeItem('language');
        });
        
        // 从本地存储加载设置
        function loadSettings() {
            // 加载主题设置
            const savedTheme = localStorage.getItem('theme') || 'light';
            themeOptions.forEach(option => {
                option.classList.remove('active');
                if (option.getAttribute('data-theme') === savedTheme) {
                    option.classList.add('active');
                }
            });
            applyTheme(savedTheme);
        }
        
        // 语言选择器
        languageButton.addEventListener('click', function() {
            languageDropdown.classList.toggle('active');
        });
        
        // 选择语言
        languageOptions.forEach(option => {
            option.addEventListener('click', function() {
                const lang = this.getAttribute('data-lang');
                changeLanguage(lang);
                languageDropdown.classList.remove('active');
            });
        });
        
        // 点击外部关闭语言选择器
        document.addEventListener('click', function(event) {
            if (!languageButton.contains(event.target) && !languageDropdown.contains(event.target)) {
                languageDropdown.classList.remove('active');
            }
        });
        
        // 更改语言
        function changeLanguage(lang) {
            // 更新当前语言显示
            currentLanguage.textContent = translations[lang]['current'];
            currentLanguage.setAttribute('data-lang', lang);
            
            // 更新所有带data-lang属性的元素
            document.querySelectorAll('[data-lang]').forEach(element => {
                const key = element.getAttribute('data-lang');
                if (translations[lang][key]) {
                    element.textContent = translations[lang][key];
                }
            });
            
            // 保存语言设置
            localStorage.setItem('language', lang);
        }
        
        // 加载语言设置
        function loadLanguage() {
            const savedLanguage = localStorage.getItem('language') || 'zh-TW';
            changeLanguage(savedLanguage);
        }
    </script>
</body>
</html>
