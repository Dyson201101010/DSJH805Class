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
        
        body {
            background: linear-gradient(135deg, #e6f7ff 0%, #b3e0ff 100%);
            color: #2c3e50;
            line-height: 1.6;
            transition: all 0.3s ease;
            font-size: 16px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            padding: 30px 0;
            animation: fadeIn 1.5s ease;
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
            color: #3498db;
            margin-right: 15px;
        }
        
        h1 {
            font-size: 2.8rem;
            color: #2980b9;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: #3498db;
            margin-bottom: 20px;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }
        
        .section {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, #3498db, #2980b9);
        }
        
        .section-title {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            color: #2980b9;
            font-size: 1.5rem;
        }
        
        .section-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: #3498db;
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
            background: #3498db;
            color: white;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            display: flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
            white-space: nowrap;
        }
        
        .top-button:hover {
            background: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
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
            background: white;
            box-shadow: 5px 0 15px rgba(0, 0, 0, 0.1);
            padding: 30px;
            overflow-y: auto;
            z-index: 1000;
            transition: left 0.4s ease;
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
            color: #2980b9;
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
            color: #2c3e50;
        }
        
        .color-options {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        .color-option {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            border: 3px solid white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition: transform 0.2s ease;
        }
        
        .color-option:hover {
            transform: scale(1.1);
        }
        
        .color-option.active {
            border: 3px solid #2c3e50;
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
        
        /* 更新日志样式 */
        .update-log {
            margin-top: 40px;
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .update-title {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            color: #2980b9;
            font-size: 1.5rem;
        }
        
        .update-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: #3498db;
        }
        
        .update-item {
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }
        
        .update-date {
            font-weight: bold;
            color: #2980b9;
            margin-bottom: 5px;
        }
        
        .update-content {
            color: #555;
        }
        
        /* 联系开发者样式 */
        .contact-developer {
            margin-top: 40px;
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        
        .contact-title {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            color: #2980b9;
            font-size: 1.5rem;
        }
        
        .contact-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: #3498db;
        }
        
        .contact-email {
            display: inline-block;
            margin: 15px 0;
            padding: 12px 25px;
            background: #f8f9fa;
            border-radius: 30px;
            color: #2980b9;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid #e6f7ff;
        }
        
        .contact-email:hover {
            background: #3498db;
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
            
            .update-log, .contact-developer {
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
                    <i class="fas fa-cog"></i> 設定
                </button>
                
                <div class="logo">
                    <i class="fas fa-graduation-cap logo-icon"></i>
                    <h1>DSJH805Class</h1>
                </div>
                
                <div class="top-buttons">
                    <a href="https://www.dsjh.ptc.edu.tw/nss/p/index" target="_blank" class="top-button">
                        <i class="fas fa-school"></i> 進入校網
                    </a>
                </div>
            </div>
            
            <p class="subtitle">我們的專屬班級空間 • 知識分享與交流的平台</p>
        </header>
        
        <div class="main-content">
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-book section-icon"></i>
                    課程資源
                </h2>
                <div class="content-placeholder">
                    <i class="fas fa-file-alt placeholder-icon"></i>
                    <p class="placeholder-text">暫無內容或未開放</p>
                </div>
            </div>
            
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-images section-icon"></i>
                    活動相簿
                </h2>
                <div class="content-placeholder">
                    <i class="fas fa-camera placeholder-icon"></i>
                    <p class="placeholder-text">暫無內容或未開放</p>
                </div>
            </div>
            
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-calendar-alt section-icon"></i>
                    班級日程
                </h2>
                <div class="content-placeholder">
                    <i class="fas fa-calendar placeholder-icon"></i>
                    <p class="placeholder-text">暫無內容或未開放</p>
                </div>
            </div>
            
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-comments section-icon"></i>
                    討論區
                </h2>
                <div class="content-placeholder">
                    <i class="fas fa-comment placeholder-icon"></i>
                    <p class="placeholder-text">暫無內容或未開放</p>
                </div>
            </div>
            
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-bullhorn section-icon"></i>
                    最新通知
                </h2>
                <div class="content-placeholder">
                    <i class="fas fa-bell placeholder-icon"></i>
                    <p class="placeholder-text">暫無內容或未開放</p>
                </div>
            </div>
            
            <div class="section">
                <h2 class="section-title">
                    <i class="fas fa-trophy section-icon"></i>
                    班級榮譽
                </h2>
                <div class="content-placeholder">
                    <i class="fas fa-award placeholder-icon"></i>
                    <p class="placeholder-text">暫無內容或未開放</p>
                </div>
            </div>
        </div>
        
        <!-- 联系开发者区块 -->
        <div class="contact-developer">
            <h2 class="contact-title">
                <i class="fas fa-envelope contact-icon"></i>
                聯繫開發者
            </h2>
            <p>如果您有任何問題或建議，歡迎聯繫開發者：</p>
            <a href="mailto:lianyuqing169@gmail.com?subject=關於DSJH805Class班級網站的問題" class="contact-email">
                <i class="fas fa-paper-plane"></i> lianyuqing169@gmail.com
            </a>
            <p class="contact-note">點擊上方郵件地址將自動開啟Gmail發送郵件</p>
        </div>
        
        <!-- 更新日志区块 -->
        <div class="update-log">
            <h2 class="update-title">
                <i class="fas fa-clipboard-list update-icon"></i>
                更新日誌
            </h2>
            <div class="update-item">
                <div class="update-date">2025年9月11日</div>
                <div class="update-content">- 新增聯繫開發者功能</div>
                <div class="update-content">- 添加更新日誌區塊</div>
            </div>
            <div class="update-item">
                <div class="update-date">2025年9月11日</div>
                <div class="update-content">- 優化手機和平板設備的顯示效果</div>
                <div class="update-content">- 修復了一些已知問題</div>
            </div>
            <div class="update-item">
                <div class="update-date">2025年9月1日</div>
                <div class="update-content">- 首次發布更新版DSJH805Class班級網站</div>
                <div class="update-content">- 包含課程資源、活動相簿等基本功能</div>
            </div>
        </div>
        
        <!-- 免责声明 -->
        <div class="disclaimer">
            <i class="fas fa-exclamation-circle"></i> 此網站為學生個人製作，非學校官方製作
        </div>
        
        <footer>
            <p>© 2025 DSJH805Class 班級網站 - 僅供班級內部使用</p>
        </footer>
    </div>
    
    <!-- 设置面板 -->
    <div class="settings-panel" id="settingsPanel">
        <div class="settings-header">
            <h2 class="settings-title">網站設定</h2>
            <button class="close-settings" id="closeSettings">
                <i class="fas fa-times"></i>
            </button>
        </div>
        
        <div class="setting-group">
            <label class="setting-label">主題顏色</label>
            <div class="color-options">
                <div class="color-option active" style="background-color: #b3e0ff;" data-color="#b3e0ff"></div>
                <div class="color-option" style="background-color: #ffb3ba;" data-color="#ffb3ba"></div>
                <div class="color-option" style="background-color: #baffc9;" data-color="#baffc9"></div>
                <div class="color-option" style="background-color: #ffffba;" data-color="#ffffba"></div>
                <div class="color-option" style="background-color: #d9b3ff;" data-color="#d9b3ff"></div>
                <div class="color-option" style="background-color: #b3fff0;" data-color="#b3fff0"></div>
            </div>
        </div>
        
        <div class="setting-group">
            <label class="setting-label">重設設定</label>
            <button class="top-button" id="resetSettings" style="background: #e74c3c;">
                <i class="fas fa-undo"></i> 恢復預設值
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
        const colorOptions = document.querySelectorAll('.color-option');
        const resetSettingsButton = document.getElementById('resetSettings');
        
        // 初始化
        document.addEventListener('DOMContentLoaded', function() {
            // 从本地存储加载设置
            loadSettings();
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
        
        // 颜色选择
        colorOptions.forEach(option => {
            option.addEventListener('click', function() {
                // 移除所有active类
                colorOptions.forEach(opt => opt.classList.remove('active'));
                // 添加active类到当前选项
                this.classList.add('active');
                
                // 获取颜色值
                const color = this.getAttribute('data-color');
                
                // 应用颜色
                document.body.style.background = `linear-gradient(135deg, ${color}33 0%, ${color} 100%)`;
                
                // 保存到本地存储
                localStorage.setItem('themeColor', color);
            });
        });
        
        // 重设设置
        resetSettingsButton.addEventListener('click', function() {
            // 重置颜色
            document.body.style.background = 'linear-gradient(135deg, #e6f7ff 0%, #b3e0ff 100%)';
            
            // 重置颜色选项
            colorOptions.forEach(option => {
                option.classList.remove('active');
                if (option.getAttribute('data-color') === '#b3e0ff') {
                    option.classList.add('active');
                }
            });
            
            // 清除本地存储
            localStorage.removeItem('themeColor');
        });
        
        // 从本地存储加载设置
        function loadSettings() {
            // 加载颜色设置
            const savedColor = localStorage.getItem('themeColor');
            if (savedColor) {
                document.body.style.background = `linear-gradient(135deg, ${savedColor}33 0%, ${savedColor} 100%)`;
                
                // 更新活动颜色选项
                colorOptions.forEach(option => {
                    option.classList.remove('active');
                    if (option.getAttribute('data-color') === savedColor) {
                        option.classList.add('active');
                    }
                });
            }
        }
    </script>
</body>
</html>
