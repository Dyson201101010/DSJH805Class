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
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
        }
        
        :root {
            --primary-color: #007AFF;
            --secondary-color: #5856D6;
            --background-color: #F2F2F7;
            --card-color: rgba(255, 255, 255, 0.7);
            --text-color: #000000;
            --text-secondary: #8E8E93;
            --shadow-color: rgba(0, 0, 0, 0.1);
            --border-color: rgba(0, 0, 0, 0.1);
            --transition-speed: 0.4s;
        }
        
        [data-theme="dark"] {
            --primary-color: #0A84FF;
            --secondary-color: #5E5CE6;
            --background-color: #000000;
            --card-color: rgba(28, 28, 30, 0.7);
            --text-color: #FFFFFF;
            --text-secondary: #8E8E93;
            --shadow-color: rgba(0, 0, 0, 0.3);
            --border-color: rgba(255, 255, 255, 0.1);
        }
        
        body {
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
            transition: all var(--transition-speed) ease;
            font-size: 17px;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        /* 位置訪問詢問彈窗 */
        .location-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
        }
        
        .location-modal-content {
            background: var(--card-color);
            border-radius: 20px;
            padding: 30px;
            max-width: 500px;
            width: 90%;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
            text-align: center;
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid var(--border-color);
        }
        
        .location-modal h2 {
            margin-bottom: 15px;
            color: var(--text-color);
            font-size: 1.5rem;
        }
        
        .location-modal p {
            margin-bottom: 25px;
            color: var(--text-secondary);
            line-height: 1.5;
        }
        
        .location-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
        }
        
        .location-btn {
            padding: 12px 25px;
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
            font-size: 1rem;
        }
        
        .location-accept {
            background: var(--primary-color);
            color: white;
        }
        
        .location-accept:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
        }
        
        .location-deny {
            background: var(--card-color);
            color: var(--text-color);
            border: 1px solid var(--border-color);
        }
        
        .location-deny:hover {
            background: rgba(0, 0, 0, 0.05);
            transform: translateY(-2px);
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
            flex-wrap: wrap;
            gap: 15px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            flex: 1;
            min-width: 200px;
        }
        
        .logo-icon {
            font-size: 2.5rem;
            color: var(--primary-color);
            margin-right: 15px;
            transition: transform 0.5s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .logo:hover .logo-icon {
            transform: rotate(15deg);
        }
        
        h1 {
            font-size: 2.5rem;
            color: var(--text-color);
            font-weight: 700;
            letter-spacing: -0.5px;
            line-height: 1.2;
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: var(--text-secondary);
            margin-bottom: 20px;
            font-weight: 400;
            line-height: 1.4;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }
        
        /* Apple Liquid Glass 效果 */
        .section {
            background: var(--card-color);
            border-radius: 20px;
            padding: 25px;
            box-shadow: 
                0 4px 20px var(--shadow-color),
                0 0 0 1px var(--border-color);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, 
                transparent 0%, 
                rgba(255, 255, 255, 0.4) 50%, 
                transparent 100%);
        }
        
        .section:hover {
            transform: translateY(-8px);
            box-shadow: 
                0 12px 30px var(--shadow-color),
                0 0 0 1px var(--border-color);
        }
        
        .section-title {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            color: var(--text-color);
            font-size: 1.5rem;
            font-weight: 600;
            line-height: 1.3;
        }
        
        .section-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: var(--primary-color);
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            justify-content: center;
            min-width: 30px;
        }
        
        .content-placeholder {
            text-align: center;
            padding: 30px 0;
            color: var(--text-secondary);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            flex: 1;
        }
        
        .placeholder-icon {
            font-size: 3rem;
            color: var(--text-secondary);
            margin-bottom: 15px;
            opacity: 0.5;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .placeholder-text {
            font-style: italic;
            font-size: 1rem;
            line-height: 1.4;
        }
        
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 25px;
            color: var(--text-secondary);
            border-top: 1px solid var(--border-color);
            line-height: 1.5;
        }
        
        /* 顶部按钮样式 - Apple 风格 */
        .top-buttons {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            justify-content: center;
        }
        
        .top-button {
            padding: 10px 20px;
            background: var(--card-color);
            color: var(--primary-color);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 2px 10px var(--shadow-color);
            display: flex;
            align-items: center;
            gap: 8px;
            text-decoration: none;
            white-space: nowrap;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            line-height: 1.2;
        }
        
        .top-button:hover {
            background: var(--primary-color);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 6px 15px var(--shadow-color);
        }
        
        .settings-button {
            background: var(--card-color);
            color: var(--primary-color);
        }
        
        .settings-button:hover {
            background: var(--primary-color);
            color: white;
        }
        
        /* 设置面板样式 */
        .settings-panel {
            position: fixed;
            top: 0;
            left: -100%;
            width: 90%;
            max-width: 380px;
            height: 100vh;
            background: var(--card-color);
            box-shadow: 8px 0 30px var(--shadow-color);
            padding: 30px;
            overflow-y: auto;
            z-index: 1000;
            transition: left 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border-right: 1px solid var(--border-color);
        }
        
        .settings-panel.active {
            left: 0;
        }
        
        .settings-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .settings-title {
            font-size: 1.8rem;
            color: var(--text-color);
            font-weight: 600;
            line-height: 1.2;
        }
        
        .close-settings {
            background: transparent;
            color: var(--text-secondary);
            border: 1px solid var(--border-color);
            width: 40px;
            height: 40px;
            border-radius: 12px;
            cursor: pointer;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }
        
        .close-settings:hover {
            background: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }
        
        .setting-group {
            margin-bottom: 25px;
        }
        
        .setting-label {
            display: block;
            margin-bottom: 12px;
            font-weight: 600;
            color: var(--text-color);
            font-size: 1.1rem;
            line-height: 1.3;
        }
        
        .theme-options {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
        }
        
        .theme-option {
            padding: 14px 16px;
            background: var(--card-color);
            color: var(--text-color);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 2px 8px var(--shadow-color);
            text-align: center;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            line-height: 1.2;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .theme-option:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px var(--shadow-color);
        }
        
        .theme-option.active {
            background: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
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
            backdrop-filter: blur(5px);
            -webkit-backdrop-filter: blur(5px);
        }
        
        .overlay.active {
            display: block;
        }
        
        .disclaimer {
            text-align: center;
            margin-top: 40px;
            padding: 20px;
            background: var(--card-color);
            border-radius: 16px;
            font-size: 0.95rem;
            color: var(--text-secondary);
            border: 1px solid var(--border-color);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            line-height: 1.5;
        }
        
        /* 语言选择器样式 */
        .language-selector {
            position: relative;
            display: inline-block;
        }
        
        .language-button {
            padding: 10px 20px;
            background: var(--card-color);
            color: var(--primary-color);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 2px 10px var(--shadow-color);
            display: flex;
            align-items: center;
            gap: 8px;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            line-height: 1.2;
        }
        
        .language-button:hover {
            background: var(--primary-color);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 6px 15px var(--shadow-color);
        }
        
        .language-dropdown {
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            background: var(--card-color);
            border-radius: 12px;
            box-shadow: 0 10px 30px var(--shadow-color);
            overflow: hidden;
            z-index: 100;
            display: none;
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
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
            font-size: 1rem;
            line-height: 1.3;
            display: flex;
            align-items: center;
        }
        
        .language-option:hover {
            background: rgba(0, 122, 255, 0.1);
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
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            border-radius: 16px;
            background: var(--card-color);
            border: 1px solid var(--border-color);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            flex: 1;
        }
        
        .class-table-link:hover {
            transform: scale(1.03) translateY(-5px);
            box-shadow: 0 12px 30px var(--shadow-color);
        }
        
        .class-table-icon {
            font-size: 4rem;
            color: var(--primary-color);
            margin-bottom: 20px;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .class-table-title {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 12px;
            color: var(--text-color);
            line-height: 1.2;
        }
        
        .class-table-description {
            font-size: 1.05rem;
            color: var(--text-secondary);
            max-width: 300px;
            margin-bottom: 20px;
            line-height: 1.5;
        }
        
        .class-table-button {
            padding: 12px 30px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(0, 122, 255, 0.3);
            display: flex;
            align-items: center;
            gap: 8px;
            line-height: 1.2;
        }
        
        .class-table-button:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 6px 18px rgba(88, 86, 214, 0.4);
        }
        
        /* Instagram 區塊樣式 */
        .instagram-section {
            margin-top: 40px;
            background: var(--card-color);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 8px 25px var(--shadow-color);
            text-align: center;
            border: 1px solid var(--border-color);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .instagram-title {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            color: var(--text-color);
            font-size: 1.5rem;
            font-weight: 600;
            line-height: 1.2;
        }
        
        .instagram-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: #E4405F;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .instagram-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 12px 25px;
            background: var(--card-color);
            color: var(--primary-color);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 2px 8px var(--shadow-color);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            margin-top: 15px;
            gap: 8px;
        }
        
        .instagram-link:hover {
            background: var(--primary-color);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 6px 15px var(--shadow-color);
        }
        
        /* 联系开发者样式 */
        .contact-developer {
            margin-top: 40px;
            background: var(--card-color);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 8px 25px var(--shadow-color);
            text-align: center;
            border: 1px solid var(--border-color);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .contact-title {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            color: var(--text-color);
            font-size: 1.5rem;
            font-weight: 600;
            line-height: 1.2;
        }
        
        .contact-icon {
            font-size: 1.8rem;
            margin-right: 15px;
            color: var(--primary-color);
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .contact-email {
            display: inline-block;
            margin: 15px 0;
            padding: 12px 25px;
            background: var(--card-color);
            border-radius: 12px;
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
            box-shadow: 0 2px 8px var(--shadow-color);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            line-height: 1.2;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .contact-email:hover {
            background: var(--primary-color);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 6px 15px var(--shadow-color);
        }
        
        /* 多语言排版优化 */
        [lang="zh-TW"], [lang="zh-CN"] {
            letter-spacing: 0.5px;
        }
        
        [lang="en"] {
            letter-spacing: 0.2px;
            font-weight: 500;
        }
        
        [lang="ja"] {
            letter-spacing: 0.3px;
            line-height: 1.5;
        }
        
        [lang="ko"] {
            letter-spacing: 0.2px;
            line-height: 1.5;
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
            .container {
                padding: 15px;
            }
            
            .main-content {
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }
            
            h1 {
                font-size: 2.2rem;
            }
            
            .section-title {
                font-size: 1.4rem;
            }
        }
        
        /* 手机设备样式 */
        @media (max-width: 768px) {
            .container {
                padding: 12px;
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
            
            .logo {
                min-width: auto;
            }
            
            .subtitle {
                font-size: 1.1rem;
            }
            
            .section {
                padding: 20px;
            }
            
            .section-title {
                font-size: 1.3rem;
            }
            
            .settings-panel {
                width: 85%;
            }
            
            .contact-developer, .instagram-section {
                padding: 25px;
            }
            
            .class-table-link {
                padding: 30px 15px;
            }
            
            .class-table-icon {
                font-size: 3.5rem;
            }
            
            .class-table-title {
                font-size: 1.6rem;
            }
            
            .location-buttons {
                flex-direction: column;
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
            
            .settings-panel {
                width: 90%;
                padding: 25px;
            }
            
            .theme-options {
                grid-template-columns: 1fr;
            }
            
            .section-title {
                flex-direction: column;
                text-align: center;
                gap: 10px;
            }
            
            .section-icon {
                margin-right: 0;
            }
        }
    </style>
</head>
<body>
    <!-- 位置訪問詢問彈窗 -->
    <div class="location-modal" id="locationModal">
        <div class="location-modal-content">
            <h2 data-lang="location-request">訪問您的位置</h2>
            <p data-lang="location-description">為了提供更好的體驗，我們希望根據您的位置自動選擇最適合的語言。我們不會存儲或分享您的位置信息。</p>
            <div class="location-buttons">
                <button class="location-btn location-accept" id="acceptLocation" data-lang="allow-location">允許訪問</button>
                <button class="location-btn location-deny" id="denyLocation" data-lang="deny-location">拒絕</button>
            </div>
        </div>
    </div>
    
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

                    <!-- 班級IG帳號連結 -->
                    <a href="https://www.instagram.com/dsjh_805/" target="_blank" class="top-button">
                        <i class="fab fa-instagram"></i> <span data-lang="instagram">班級IG</span>
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
        
        <!-- Instagram 區塊 -->
        <div class="instagram-section">
            <h2 class="instagram-title">
                <i class="fab fa-instagram instagram-icon"></i>
                <span data-lang="instagram-title">班級 Instagram</span>
            </h2>
            <p data-lang="instagram-description">關注我們的班級 Instagram 帳號，獲取最新班級動態和活動照片：</p>
            <a href="https://www.instagram.com/dsjh_805/" target="_blank" class="instagram-link">
                <i class="fab fa-instagram"></i>
                <span data-lang="follow-instagram">@dsjh_805</span>
            </a>
        </div>
        
        <!-- 联系开发者区块 -->
        <div class="contact-developer">
            <h2 class="contact-title">
                <i class="fas fa-envelope contact-icon"></i>
                <span data-lang="contact-developer">聯繫開發者</span>
            </h2>
            <p data-lang="contact-description">如果您有任何問題或建議，歡迎聯繫開發者：</p>
            <div class="contact-email">lianyuqing169@gmail.com</div>
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
            <label class="setting-label" data-lang="theme">主題模式</label>
            <div class="theme-options">
                <button class="theme-option active" data-theme="light" data-lang="light-theme">淺色模式</button>
                <button class="theme-option" data-theme="dark" data-lang="dark-theme">深色模式</button>
                <button class="theme-option" data-theme="auto" data-lang="auto-theme">跟隨系統</button>
            </div>
        </div>
        
        <div class="setting-group">
            <label class="setting-label" data-lang="location-settings">位置設定</label>
            <div class="theme-options">
                <button class="theme-option" id="enableLocation" data-lang="enable-location">啟用位置</button>
                <button class="theme-option" id="disableLocation" data-lang="disable-location">停用位置</button>
            </div>
            <p style="margin-top: 10px; font-size: 0.9rem; color: var(--text-secondary);" data-lang="location-help">停用位置後，將不會再自動根據位置選擇語言</p>
        </div>
        
        <div class="setting-group">
            <label class="setting-label" data-lang="reset-settings">重設設定</label>
            <button class="top-button" id="resetSettings" style="background: #FF3B30; color: white; border: none;">
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
        const locationModal = document.getElementById('locationModal');
        const acceptLocation = document.getElementById('acceptLocation');
        const denyLocation = document.getElementById('denyLocation');
        const enableLocation = document.getElementById('enableLocation');
        const disableLocation = document.getElementById('disableLocation');
        
        // 多语言文本
        const translations = {
            'zh-TW': {
                'settings': '設定',
                'current': '繁體中文',
                'school-website': '進入校網',
                'instagram': '班級IG',
                'instagram-title': '班級 Instagram',
                'instagram-description': '關注我們的班級 Instagram 帳號，獲取最新班級動態和活動照片：',
                'follow-instagram': '@dsjh_805',
                'subtitle': '我們的專屬班級空間 • 知識分享與交流的平台',
                'latest-notice': '最新通知',
                'class-schedule': '課表',
                'no-content': '暫無內容或未開放',
                'view-schedule': '查看課表',
                'schedule-description': '點擊此處查看八年五班的完整課表，請選擇「八年五班」查看詳細課程安排',
                'go-to-schedule': '前往課表',
                'contact-developer': '聯繫開發者',
                'contact-description': '如果您有任何問題或建議，歡迎聯繫開發者：',
                'disclaimer': '此網站為學生個人製作，非學校官方製作',
                'footer-text': '班級網站 - 僅供班級內部使用',
                'website-settings': '網站設定',
                'theme': '主題模式',
                'light-theme': '淺色模式',
                'dark-theme': '深色模式',
                'auto-theme': '跟隨系統',
                'location-settings': '位置設定',
                'enable-location': '啟用位置',
                'disable-location': '停用位置',
                'location-help': '停用位置後，將不會再自動根據位置選擇語言',
                'reset-settings': '重設設定',
                'reset-default': '恢復預設值',
                'location-request': '訪問您的位置',
                'location-description': '為了提供更好的體驗，我們希望根據您的位置自動選擇最適合的語言。我們不會存儲或分享您的位置信息。',
                'allow-location': '允許訪問',
                'deny-location': '拒絕'
            },
            'zh-CN': {
                'settings': '设置',
                'current': '简体中文',
                'school-website': '进入校网',
                'instagram': '班级IG',
                'instagram-title': '班级 Instagram',
                'instagram-description': '关注我们的班级 Instagram 账号，获取最新班级动态和活动照片：',
                'follow-instagram': '@dsjh_805',
                'subtitle': '我们的专属班级空间 • 知识分享与交流的平台',
                'latest-notice': '最新通知',
                'class-schedule': '课表',
                'no-content': '暂无内容或未开放',
                'view-schedule': '查看课表',
                'schedule-description': '点击此处查看八年五班的完整课表，请选择「八年五班」查看详细课程安排',
                'go-to-schedule': '前往课表',
                'contact-developer': '联系开发者',
                'contact-description': '如果您有任何问题或建议，欢迎联系开发者：',
                'disclaimer': '此网站为学生个人制作，非学校官方制作',
                'footer-text': '班级网站 - 仅供班级内部使用',
                'website-settings': '网站设置',
                'theme': '主题模式',
                'light-theme': '浅色模式',
                'dark-theme': '深色模式',
                'auto-theme': '跟随系统',
                'location-settings': '位置设置',
                'enable-location': '启用位置',
                'disable-location': '停用位置',
                'location-help': '停用位置后，将不会再自动根据位置选择语言',
                'reset-settings': '重设设置',
                'reset-default': '恢复默认值',
                'location-request': '访问您的位置',
                'location-description': '为了提供更好的体验，我们希望根据您的位置自动选择最适合的语言。我们不会存储或分享您的位置信息。',
                'allow-location': '允许访问',
                'deny-location': '拒绝'
            },
            'en': {
                'settings': 'Settings',
                'current': 'English',
                'school-website': 'School Website',
                'instagram': 'Class IG',
                'instagram-title': 'Class Instagram',
                'instagram-description': 'Follow our class Instagram account for the latest updates and activity photos:',
                'follow-instagram': '@dsjh_805',
                'subtitle': 'Our Exclusive Class Space • Platform for Knowledge Sharing and Exchange',
                'latest-notice': 'Latest Notice',
                'class-schedule': 'Class Schedule',
                'no-content': 'No content or not available',
                'view-schedule': 'View Schedule',
                'schedule-description': 'Click here to view the complete schedule for Class 8-5. Please select "Class 8-5" to view detailed course arrangements',
                'go-to-schedule': 'Go to Schedule',
                'contact-developer': 'Contact Developer',
                'contact-description': 'If you have any questions or suggestions, please contact the developer:',
                'disclaimer': 'This website is made by students, not officially by the school',
                'footer-text': 'Class Website - For Internal Use Only',
                'website-settings': 'Website Settings',
                'theme': 'Theme Mode',
                'light-theme': 'Light Mode',
                'dark-theme': 'Dark Mode',
                'auto-theme': 'Follow System',
                'location-settings': 'Location Settings',
                'enable-location': 'Enable Location',
                'disable-location': 'Disable Location',
                'location-help': 'After disabling location, language will no longer be automatically selected based on location',
                'reset-settings': 'Reset Settings',
                'reset-default': 'Restore Default',
                'location-request': 'Access Your Location',
                'location-description': 'To provide a better experience, we would like to automatically select the most appropriate language based on your location. We will not store or share your location information.',
                'allow-location': 'Allow Access',
                'deny-location': 'Deny'
            },
            'ja': {
                'settings': '設定',
                'current': '日本語',
                'school-website': '学校のウェブサイト',
                'instagram': 'クラスIG',
                'instagram-title': 'クラス Instagram',
                'instagram-description': '最新のクラス更新と活動写真を入手するには、クラスのInstagramアカウントをフォローしてください：',
                'follow-instagram': '@dsjh_805',
                'subtitle': '私たちの専用クラススペース • 知識共有と交流のプラットフォーム',
                'latest-notice': '最新のお知らせ',
                'class-schedule': '時間割',
                'no-content': 'コンテンツがありませんまたは利用できません',
                'view-schedule': '時間割を表示',
                'schedule-description': '8年5組の完全な時間割を表示するにはここをクリックしてください。詳細な授業手配を表示するには「8年5組」を選択してください',
                'go-to-schedule': '時間割へ',
                'contact-developer': '開発者に連絡',
                'contact-description': 'ご質問やご提案がある場合は、開発者までご連絡ください：',
                'disclaimer': 'このウェブサイトは学生が個人で作成したもので、学校公式のものではありません',
                'footer-text': 'クラスウェブサイト - 内部使用のみ',
                'website-settings': 'ウェブサイト設定',
                'theme': 'テーマモード',
                'light-theme': 'ライトモード',
                'dark-theme': 'ダークモード',
                'auto-theme': 'システムに従う',
                'location-settings': '位置設定',
                'enable-location': '位置を有効化',
                'disable-location': '位置を無効化',
                'location-help': '位置を無効にすると、位置に基づいて言語が自動的に選択されなくなります',
                'reset-settings': '設定をリセット',
                'reset-default': 'デフォルトに戻す',
                'location-request': '位置情報へのアクセス',
                'location-description': 'より良い体験を提供するために、お客様の位置情報に基づいて最適な言語を自動的に選択したいと思います。お客様の位置情報を保存または共有することはありません。',
                'allow-location': 'アクセスを許可',
                'deny-location': '拒否'
            },
            'ko': {
                'settings': '설정',
                'current': '한국어',
                'school-website': '학교 웹사이트',
                'instagram': '클래스 IG',
                'instagram-title': '클래스 Instagram',
                'instagram-description': '최신 클래스 업데이트 및 활동 사진을 보려면 클래스 Instagram 계정을 팔로우하세요:',
                'follow-instagram': '@dsjh_805',
                'subtitle': '우리의 전용 클래스 공간 • 지식 공유 및 교류 플랫폼',
                'latest-notice': '최신 공지',
                'class-schedule': '시간표',
                'no-content': '콘텐츠가 없거나 사용할 수 없음',
                'view-schedule': '시간표 보기',
                'schedule-description': '8학년 5반의 전체 시간표를 보려면 여기를 클릭하세요. 자세한 수업 일정을 보려면 "8학년 5반"을 선택하세요',
                'go-to-schedule': '시간표로 이동',
                'contact-developer': '개발자에게 문의',
                'contact-description': '질문이나 제안 사항이 있으면 개발자에게 연락해 주세요:',
                'disclaimer': '이 웹사이트는 학생이 개인적으로 제작한 것으로 학교 공식 제작물이 아닙니다',
                'footer-text': '클래스 웹사이트 - 내부 사용만',
                'website-settings': '웹사이트 설정',
                'theme': '테마 모드',
                'light-theme': '라이트 모드',
                'dark-theme': '다크 모드',
                'auto-theme': '시스템 따라가기',
                'location-settings': '위치 설정',
                'enable-location': '위치 활성화',
                'disable-location': '위치 비활성화',
                'location-help': '위치를 비활성화하면 위치에 따라 언어가 자동으로 선택되지 않습니다',
                'reset-settings': '설정 재설정',
                'reset-default': '기본값 복원',
                'location-request': '위치 접근',
                'location-description': '더 나은 경험을 제공하기 위해 귀하의 위치를 기반으로 가장 적합한 언어를 자동으로 선택하고자 합니다. 귀하의 위치 정보를 저장하거나 공유하지 않습니다.',
                'allow-location': '접근 허용',
                'deny-location': '거부'
            }
        };
        
        // 國家/地區到語言的映射
        const countryToLanguage = {
            'TW': 'zh-TW', // 台灣 - 繁體中文
            'HK': 'zh-TW', // 香港 - 繁體中文
            'MO': 'zh-TW', // 澳門 - 繁體中文
            'CN': 'zh-CN', // 中國 - 簡體中文
            'US': 'en',    // 美國 - 英文
            'GB': 'en',    // 英國 - 英文
            'CA': 'en',    // 加拿大 - 英文
            'AU': 'en',    // 澳大利亞 - 英文
            'JP': 'ja',    // 日本 - 日文
            'KR': 'ko',    // 韓國 - 韓文
            // 可以根據需要添加更多國家映射
        };
        
        // 初始化
        document.addEventListener('DOMContentLoaded', function() {
            // 檢查位置服務是否啟用
            const locationEnabled = localStorage.getItem('locationEnabled') !== 'false';
            const locationAsked = localStorage.getItem('locationAsked');
            
            if (locationEnabled && !locationAsked) {
                // 顯示位置詢問彈窗
                locationModal.style.display = 'flex';
            } else {
                // 從本地存儲加載設置
                loadSettings();
                
                // 加載語言設置
                loadLanguage();
            }
            
            // 更新位置設定按鈕狀態
            updateLocationButtons();
        });
        
        // 更新位置設定按鈕狀態
        function updateLocationButtons() {
            const locationEnabled = localStorage.getItem('locationEnabled') !== 'false';
            
            if (locationEnabled) {
                enableLocation.classList.add('active');
                disableLocation.classList.remove('active');
            } else {
                enableLocation.classList.remove('active');
                disableLocation.classList.add('active');
            }
        }
        
        // 啟用位置
        enableLocation.addEventListener('click', function() {
            localStorage.setItem('locationEnabled', 'true');
            updateLocationButtons();
            
            // 如果還沒有詢問過位置，顯示詢問彈窗
            const locationAsked = localStorage.getItem('locationAsked');
            if (!locationAsked) {
                locationModal.style.display = 'flex';
            }
        });
        
        // 停用位置
        disableLocation.addEventListener('click', function() {
            localStorage.setItem('locationEnabled', 'false');
            updateLocationButtons();
        });
        
        // 接受位置訪問
        acceptLocation.addEventListener('click', function() {
            // 隱藏彈窗
            locationModal.style.display = 'none';
            
            // 標記為已詢問
            localStorage.setItem('locationAsked', 'true');
            localStorage.setItem('locationEnabled', 'true');
            
            // 更新按鈕狀態
            updateLocationButtons();
            
            // 獲取用戶位置
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    function(position) {
                        // 成功獲取位置，根據位置獲取國家代碼
                        getCountryFromCoordinates(position.coords.latitude, position.coords.longitude);
                    },
                    function(error) {
                        // 獲取位置失敗，使用默認語言
                        console.log('位置獲取失敗:', error);
                        setDefaultLanguage();
                    }
                );
            } else {
                // 瀏覽器不支持地理位置
                console.log('瀏覽器不支持地理位置');
                setDefaultLanguage();
            }
        });
        
        // 拒絕位置訪問
        denyLocation.addEventListener('click', function() {
            // 隱藏彈窗
            locationModal.style.display = 'none';
            
            // 標記為已詢問
            localStorage.setItem('locationAsked', 'true');
            localStorage.setItem('locationEnabled', 'false');
            
            // 更新按鈕狀態
            updateLocationButtons();
            
            // 使用默認語言
            setDefaultLanguage();
        });
        
        // 根據經緯度獲取國家代碼
        function getCountryFromCoordinates(lat, lng) {
            // 使用逆地理編碼API獲取國家信息
            fetch(`https://api.bigdatacloud.net/data/reverse-geocode-client?latitude=${lat}&longitude=${lng}&localityLanguage=en`)
                .then(response => response.json())
                .then(data => {
                    const countryCode = data.countryCode;
                    const language = countryToLanguage[countryCode] || 'zh-TW'; // 默認使用繁體中文
                    
                    // 應用語言
                    changeLanguage(language);
                    
                    // 保存語言設置
                    localStorage.setItem('language', language);
                })
                .catch(error => {
                    console.log('獲取國家信息失敗:', error);
                    setDefaultLanguage();
                });
        }
        
        // 設置默認語言
        function setDefaultLanguage() {
            // 從本地存儲加載設置
            loadSettings();
            
            // 加載語言設置
            loadLanguage();
        }
        
        // 打開設置面板
        settingsButton.addEventListener('click', function() {
            settingsPanel.classList.add('active');
            overlay.classList.add('active');
        });
        
        // 關閉設置面板
        closeSettings.addEventListener('click', function() {
            settingsPanel.classList.remove('active');
            overlay.classList.remove('active');
        });
        
        // 點擊遮罩層關閉設置
        overlay.addEventListener('click', function() {
            settingsPanel.classList.remove('active');
            overlay.classList.remove('active');
        });
        
        // 主題選擇
        themeOptions.forEach(option => {
            option.addEventListener('click', function() {
                // 移除所有active類
                themeOptions.forEach(opt => opt.classList.remove('active'));
                // 添加active類到當前選項
                this.classList.add('active');
                
                // 獲取主題值
                const theme = this.getAttribute('data-theme');
                
                // 應用主題
                applyTheme(theme);
                
                // 保存到本地存儲
                localStorage.setItem('theme', theme);
            });
        });
        
        // 應用主題
        function applyTheme(theme) {
            if (theme === 'auto') {
                // 跟隨系統主題
                if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
                    document.documentElement.setAttribute('data-theme', 'dark');
                } else {
                    document.documentElement.setAttribute('data-theme', 'light');
                }
                
                // 監聽系統主題變化
                if (window.matchMedia) {
                    window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', e => {
                        document.documentElement.setAttribute('data-theme', e.matches ? 'dark' : 'light');
                    });
                }
            } else {
                document.documentElement.setAttribute('data-theme', theme);
            }
        }
        
        // 重設設置
        resetSettingsButton.addEventListener('click', function() {
            // 重置主題
            document.documentElement.setAttribute('data-theme', 'light');
            
            // 重置主題選項
            themeOptions.forEach(option => {
                option.classList.remove('active');
                if (option.getAttribute('data-theme') === 'light') {
                    option.classList.add('active');
                }
            });
            
            // 重置語言
            changeLanguage('zh-TW');
            
            // 重置位置設定
            localStorage.removeItem('locationAsked');
            localStorage.removeItem('locationEnabled');
            updateLocationButtons();
            
            // 清除本地存儲
            localStorage.removeItem('theme');
            localStorage.removeItem('language');
            
            // 重新顯示位置詢問
            locationModal.style.display = 'flex';
        });
        
        // 從本地存儲加載設置
        function loadSettings() {
            // 加載主題設置
            const savedTheme = localStorage.getItem('theme') || 'light';
            themeOptions.forEach(option => {
                option.classList.remove('active');
                if (option.getAttribute('data-theme') === savedTheme) {
                    option.classList.add('active');
                }
            });
            applyTheme(savedTheme);
        }
        
        // 語言選擇器
        languageButton.addEventListener('click', function() {
            languageDropdown.classList.toggle('active');
        });
        
        // 選擇語言
        languageOptions.forEach(option => {
            option.addEventListener('click', function() {
                const lang = this.getAttribute('data-lang');
                changeLanguage(lang);
                languageDropdown.classList.remove('active');
            });
        });
        
        // 點擊外部關閉語言選擇器
        document.addEventListener('click', function(event) {
            if (!languageButton.contains(event.target) && !languageDropdown.contains(event.target)) {
                languageDropdown.classList.remove('active');
            }
        });
        
        // 更改語言
        function changeLanguage(lang) {
            // 更新當前語言顯示
            currentLanguage.textContent = translations[lang]['current'];
            currentLanguage.setAttribute('data-lang', lang);
            
            // 更新所有帶data-lang屬性的元素
            document.querySelectorAll('[data-lang]').forEach(element => {
                const key = element.getAttribute('data-lang');
                if (translations[lang][key]) {
                    element.textContent = translations[lang][key];
                }
            });
            
            // 設置語言屬性
            document.documentElement.lang = lang;
            
            // 保存語言設置
            localStorage.setItem('language', lang);
        }
        
        // 加載語言設置
        function loadLanguage() {
            const savedLanguage = localStorage.getItem('language') || 'zh-TW';
            changeLanguage(savedLanguage);
        }
    </script>
</body>
</html>
