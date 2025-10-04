<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thám Hiểm Tri Thức - Phiên bản Đơn giản</title>
    <style>
        :root {
            --primary: #4a148c;
            --secondary: #ff6f00;
            --accent: #00c853;
            --danger: #d50000;
            --light: #f3e5f5;
            --dark: #1a237e;
            --text: #212121;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a237e 0%, #4a148c 100%);
            color: var(--light);
            min-height: 100vh;
            padding: 10px;
            overflow-x: hidden;
        }
        
        .game-container {
            max-width: 800px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            overflow: hidden;
            position: relative;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: float 15s infinite linear;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-1000px) translateX(500px) rotate(360deg);
                opacity: 0;
            }
        }
        
        .header {
            background: linear-gradient(90deg, var(--primary) 0%, var(--secondary) 100%);
            padding: 15px 10px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: pulse 4s infinite alternate;
        }
        
        @keyframes pulse {
            0% {
                transform: scale(0.8);
                opacity: 0.5;
            }
            100% {
                transform: scale(1.2);
                opacity: 0.8;
            }
        }
        
        .title {
            font-size: clamp(1.8rem, 5vw, 2.5rem);
            margin-bottom: 8px;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            background: linear-gradient(45deg, #fff, #ffeb3b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: glow 2s infinite alternate;
        }
        
        @keyframes glow {
            from {
                text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
            }
            to {
                text-shadow: 0 0 20px rgba(255, 235, 59, 0.8), 0 0 30px rgba(255, 235, 59, 0.6);
            }
        }
        
        .subtitle {
            font-size: clamp(0.9rem, 3vw, 1.2rem);
            opacity: 0.9;
        }
        
        .game-content {
            padding: 15px;
            position: relative;
        }
        
        .stats {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 15px;
            background: rgba(0, 0, 0, 0.2);
            padding: 12px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .player-info {
            display: flex;
            align-items: center;
            gap: 10px;
            flex: 1;
            min-width: 150px;
        }
        
        .player-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(45deg, var(--secondary), var(--accent));
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1rem;
        }
        
        .player-name {
            font-size: 1rem;
            font-weight: bold;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }
        
        .hearts {
            display: flex;
            gap: 5px;
            flex: 1;
            justify-content: center;
            min-width: 120px;
        }
        
        .heart {
            color: var(--danger);
            font-size: 1.3rem;
            animation: heartbeat 1.5s infinite;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.1); }
            10% { transform: scale(1); }
            15% { transform: scale(1.1); }
            20% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        .score {
            font-size: 1.2rem;
            font-weight: bold;
            color: var(--secondary);
            text-shadow: 0 0 10px rgba(255, 111, 0, 0.5);
            flex: 1;
            text-align: right;
            min-width: 100px;
        }
        
        .scene {
            background: rgba(0, 0, 0, 0.3);
            border-radius: 15px;
            padding: 15px;
            margin-bottom: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
            min-height: 150px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        .scene-image {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 12px;
            border: 2px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .scene-title {
            font-size: 1.3rem;
            margin-bottom: 12px;
            color: var(--secondary);
            text-align: center;
        }
        
        .scene-description {
            font-size: 1rem;
            line-height: 1.5;
            margin-bottom: 12px;
            text-align: center;
        }
        
        .question {
            font-size: 1.2rem;
            font-weight: bold;
            text-align: center;
            margin: 15px 0;
            padding: 12px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            border-left: 4px solid var(--accent);
            animation: slideIn 0.5s ease-out;
            word-break: break-word;
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .input-container {
            display: flex;
            gap: 10px;
            margin-top: 15px;
            flex-direction: column;
        }
        
        @media (min-width: 768px) {
            .input-container {
                flex-direction: row;
            }
        }
        
        input {
            flex: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            color: var(--text);
            font-size: 1rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            width: 100%;
        }
        
        input:focus {
            outline: none;
            box-shadow: 0 0 0 2px var(--accent);
            transform: scale(1.02);
        }
        
        button {
            padding: 12px 20px;
            border: none;
            border-radius: 8px;
            background: linear-gradient(45deg, var(--secondary), var(--accent));
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            width: 100%;
        }
        
        @media (min-width: 768px) {
            button {
                width: auto;
            }
        }
        
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 8px rgba(0, 0, 0, 0.3);
        }
        
        button:active {
            transform: translateY(1px);
        }
        
        .feedback {
            margin-top: 15px;
            padding: 12px;
            border-radius: 10px;
            text-align: center;
            font-weight: bold;
            animation: popIn 0.5s;
            display: none;
        }
        
        @keyframes popIn {
            0% {
                transform: scale(0.8);
                opacity: 0;
            }
            100% {
                transform: scale(1);
                opacity: 1;
            }
        }
        
        .correct {
            background: rgba(0, 200, 83, 0.2);
            border: 1px solid var(--accent);
            color: var(--accent);
        }
        
        .incorrect {
            background: rgba(213, 0, 0, 0.2);
            border: 1px solid var(--danger);
            color: var(--danger);
        }
        
        .hint {
            margin-top: 12px;
            padding: 10px;
            background: rgba(255, 193, 7, 0.2);
            border-radius: 8px;
            border-left: 3px solid #ffc107;
            display: none;
            animation: fadeIn 0.5s;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .progress-container {
            margin-top: 15px;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 10px;
            overflow: hidden;
            height: 8px;
        }
        
        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--secondary), var(--accent));
            width: 0%;
            transition: width 0.5s ease-in-out;
            border-radius: 10px;
        }
        
        .stage-indicator {
            text-align: center;
            margin-top: 8px;
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        .active-skill {
            margin-top: 15px;
            padding: 12px;
            background: rgba(255, 111, 0, 0.2);
            border-radius: 10px;
            text-align: center;
            display: none;
        }
        
        .skill-button {
            background: linear-gradient(45deg, #ff4081, #7c4dff);
            margin-top: 10px;
        }
        
        .skills-container {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 15px;
            margin-top: 15px;
        }
        
        .skills-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .skill-item {
            padding: 10px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            border-left: 4px solid var(--accent);
        }
        
        .skill-name {
            font-weight: bold;
            margin-bottom: 5px;
            color: var(--secondary);
        }
        
        .skill-description {
            font-size: 0.9rem;
            opacity: 0.9;
        }
        
        .player-setup {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            padding: 15px;
        }
        
        .setup-form {
            background: rgba(255, 255, 255, 0.9);
            padding: 25px;
            border-radius: 15px;
            width: 100%;
            max-width: 400px;
            text-align: center;
            color: var(--text);
        }
        
        .setup-form h2 {
            margin-bottom: 15px;
            color: var(--primary);
            font-size: 1.5rem;
        }
        
        .setup-form input {
            width: 100%;
            margin-bottom: 15px;
        }
        
        .avatar-options {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 15px 0;
            flex-wrap: wrap;
        }
        
        .avatar-option {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            border: 3px solid transparent;
            transition: all 0.3s;
        }
        
        .avatar-option.selected {
            border-color: var(--accent);
            transform: scale(1.1);
        }
        
        /* Skills Selection Modal */
        .skill-selection {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            padding: 15px;
        }
        
        .skill-modal {
            background: rgba(255, 255, 255, 0.95);
            padding: 25px;
            border-radius: 15px;
            width: 100%;
            max-width: 600px;
            text-align: center;
            color: var(--text);
            max-height: 80vh;
            overflow-y: auto;
        }
        
        .skill-modal h2 {
            margin-bottom: 15px;
            color: var(--primary);
        }
        
        .skill-options {
            display: grid;
            grid-template-columns: 1fr;
            gap: 12px;
            margin: 15px 0;
        }
        
        @media (min-width: 768px) {
            .skill-options {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            }
        }
        
        .skill-option {
            padding: 15px;
            background: rgba(74, 20, 140, 0.1);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
        }
        
        .skill-option:hover {
            background: rgba(74, 20, 140, 0.2);
            transform: translateY(-2px);
            border-color: var(--primary);
        }
        
        .skill-option.selected {
            background: rgba(74, 20, 140, 0.3);
            border-color: var(--accent);
            transform: scale(1.05);
        }
        
        .rules {
            background: rgba(0, 0, 0, 0.2);
            padding: 12px;
            border-radius: 10px;
            margin-top: 15px;
            font-size: 0.9rem;
            line-height: 1.5;
        }
        
        .rules h3 {
            margin-bottom: 8px;
            color: var(--secondary);
        }
        
        .rules ol {
            padding-left: 20px;
        }
        
        .rules li {
            margin-bottom: 5px;
        }
        
        /* Responsive improvements for tablets */
        @media (min-width: 768px) and (max-width: 1024px) {
            .game-content {
                padding: 20px;
            }
            
            .scene-image {
                height: 180px;
            }
            
            .stats {
                padding: 15px;
            }
            
            .player-avatar {
                width: 45px;
                height: 45px;
            }
        }
        
        /* Responsive improvements for large screens */
        @media (min-width: 1025px) {
            .game-content {
                padding: 30px;
            }
            
            .scene-image {
                height: 200px;
            }
        }
    </style>
</head>
<body>
    <div class="player-setup" id="player-setup">
        <div class="setup-form">
            <h2>Chào mừng đến với Thám Hiểm Tri Thức!</h2>
            <p>Hãy nhập tên của bạn và chọn avatar để bắt đầu:</p>
            <input type="text" id="player-name-input" placeholder="Tên của bạn" maxlength="15">
            <div class="avatar-options">
                <div class="avatar-option selected" style="background: #ff6f00;" data-avatar="🦁"></div>
                <div class="avatar-option" style="background: #4a148c;" data-avatar="🐯"></div>
                <div class="avatar-option" style="background: #00c853;" data-avatar="🐉"></div>
                <div class="avatar-option" style="background: #d50000;" data-avatar="🦅"></div>
            </div>
            <button id="start-game-btn">Bắt đầu phiêu lưu!</button>
        </div>
    </div>

    <div class="skill-selection" id="skill-selection">
        <div class="skill-modal">
            <h2>🎉 Chọn Kỹ Năng Đặc Biệt! 🎉</h2>
            <p>Bạn đã hoàn thành 5 màn chơi! Hãy chọn 1 trong 3 kỹ năng ngẫu nhiên:</p>
            <div class="skill-options" id="skill-options">
                <!-- Skill options will be generated by JavaScript -->
            </div>
            <button id="confirm-skill-btn">Xác Nhận Kỹ Năng</button>
        </div>
    </div>

    <div class="game-container" id="main-container" style="display: none;">
        <div class="particles" id="particles"></div>
        
        <div class="header">
            <h1 class="title">Thám Hiểm Tri Thức</h1>
            <p class="subtitle">Phiêu lưu tri thức với hệ thống kỹ năng đặc biệt</p>
        </div>
        
        <div class="game-content">
            <div class="stats">
                <div class="player-info">
                    <div class="player-avatar" id="player-avatar">🦁</div>
                    <div class="player-name" id="player-name">Người chơi</div>
                </div>
                <div class="hearts" id="hearts">
                    <!-- Hearts will be generated by JavaScript -->
                </div>
                <div class="score">Điểm: <span id="score">0</span></div>
            </div>
            
            <div class="scene">
                <img class="scene-image" id="scene-image" src="https://via.placeholder.com/800x200/4a148c/ffffff?text=Khởi+Đầu+Phiêu+Lưu" alt="Cảnh phiêu lưu">
                <h2 class="scene-title" id="scene-title">Màn 1: Khởi Đầu Phiêu Lưu</h2>
                <p class="scene-description" id="scene-description">
                    Hành trình bắt đầu, bạn đến trước một cây cầu gỗ mục nát. Để qua được, bạn phải trả lời đúng câu hỏi kiến thức.
                </p>
                
                <div class="question" id="question">7 x 8 = ?</div>
                
                <div class="input-container">
                    <input type="text" id="answer-input" placeholder="Nhập câu trả lời của bạn...">
                    <button id="submit-btn">Trả lời</button>
                </div>
                
                <div class="feedback" id="feedback"></div>
                <div class="hint" id="hint"></div>
            </div>
            
            <div class="active-skill" id="active-skill">
                <h3>Kỹ Năng Đặc Biệt</h3>
                <p id="active-skill-description">Bạn chưa có kỹ năng nào</p>
                <button class="skill-button" id="use-skill-btn">Sử Dụng Kỹ Năng</button>
            </div>
            
            <div class="progress-container">
                <div class="progress-bar" id="progress-bar"></div>
            </div>
            <div class="stage-indicator" id="stage-indicator">Màn 1 - Tiến độ: 0/5</div>
            
            <div class="skills-container">
                <h3>Kỹ Năng Của Bạn</h3>
                <div class="skills-list" id="skills-list">
                    <div class="skill-item">Chưa có kỹ năng nào</div>
                </div>
            </div>
            
            <div class="rules">
                <h3>Quy tắc trò chơi:</h3>
                <ol>
                    <li>Mỗi màn là một tình huống phiêu lưu khác nhau</li>
                    <li>Trả lời đúng câu hỏi để vượt qua chướng ngại</li>
                    <li>Trả lời đúng: +10 điểm, +1 trái tim (tối đa 5)</li>
                    <li>Trả lời sai: -1 trái tim, nhận gợi ý</li>
                    <li>Sau mỗi 5 màn: Chọn 1 kỹ năng đặc biệt ngẫu nhiên</li>
                    <li>Màn chơi: Vô tận - Cố gắng đạt điểm cao nhất!</li>
                </ol>
            </div>
        </div>
    </div>

    <script>
        // Tạo hiệu ứng hạt nền
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 100;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                const size = Math.random() * 5 + 1;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.top = `${Math.random() * 100}%`;
                
                const duration = Math.random() * 20 + 10;
                particle.style.animationDuration = `${duration}s`;
                
                const delay = Math.random() * 5;
                particle.style.animationDelay = `${delay}s`;
                
                particlesContainer.appendChild(particle);
            }
        }

        // Database kỹ năng (30 skills)
        const skillsDatabase = [
            // Toán học (5 skills)
            { id: 1, name: "Tính Nhẩm Thần Tốc", description: "Tự động hiển thị đáp án cho câu hỏi tính nhẩm", type: "math", effect: "Hiển thị kết quả phép tính" },
            { id: 2, name: "Giải Phương Trình", description: "Hiển thị các bước giải phương trình", type: "math", effect: "Hiển thị phương pháp giải" },
            { id: 3, name: "Hình Học Thông Thái", description: "Hiển thị hình vẽ minh họa cho bài toán hình học", type: "math", effect: "Hiển thị hình ảnh minh họa" },
            { id: 4, name: "Đại Số Cao Thủ", description: "Tự động đơn giản hóa biểu thức đại số", type: "math", effect: "Đơn giản hóa bài toán" },
            { id: 5, name: "Toán Đố Siêu Tốc", description: "Phân tích bài toán đố thành các bước đơn giản", type: "math", effect: "Phân tích bài toán" },
            
            // Khoa học tự nhiên (5 skills)
            { id: 6, name: "Vật Lý Thực Nghiệm", description: "Hiển thị công thức vật lý liên quan", type: "science", effect: "Hiển thị công thức" },
            { id: 7, name: "Hóa Học Phân Tích", description: "Hiển thị phương trình hóa học cân bằng", type: "science", effect: "Cân bằng phương trình" },
            { id: 8, name: "Sinh Học Diệu Kỳ", description: "Hiển thị sơ đồ quá trình sinh học", type: "science", effect: "Hiển thị sơ đồ" },
            { id: 9, name: "Thiên Văn Học", description: "Hiển thị hình ảnh hệ mặt trời và các hành tinh", type: "science", effect: "Hiển thị hình ảnh vũ trụ" },
            { id: 10, name: "Khoa Học Trái Đất", description: "Giải thích hiện tượng tự nhiên chi tiết", type: "science", effect: "Giải thích khoa học" },
            
            // Tiếng Anh (5 skills)
            { id: 11, name: "Từ Vựng Thông Thái", description: "Hiển thị định nghĩa từ vựng tiếng Anh", type: "english", effect: "Hiển thị định nghĩa" },
            { id: 12, name: "Ngữ Pháp Hoàn Hảo", description: "Phân tích cấu trúc ngữ pháp trong câu", type: "english", effect: "Phân tích ngữ pháp" },
            { id: 13, name: "Phát Âm Chuẩn", description: "Hiển thị phiên âm quốc tế IPA", type: "english", effect: "Hiển thị phiên âm" },
            { id: 14, name: "Dịch Thuật Chuyên Nghiệp", description: "Cung cấp bản dịch song ngữ chi tiết", type: "english", effect: "Dịch song ngữ" },
            { id: 15, name: "Giao Tiếp Lưu Loát", description: "Đưa ra các tình huống giao tiếp thực tế", type: "english", effect: "Tình huống giao tiếp" },
            
            // Lịch sử & Văn hóa (5 skills)
            { id: 16, name: "Lịch Sử Sống Động", description: "Hiển thị dòng thời gian sự kiện lịch sử", type: "history", effect: "Dòng thời gian" },
            { id: 17, name: "Địa Lý Toàn Cầu", description: "Hiển thị bản đồ các khu vực liên quan", type: "history", effect: "Hiển thị bản đồ" },
            { id: 18, name: "Văn Hóa Dân Gian", description: "Giải thích phong tục, tập quán văn hóa", type: "history", effect: "Giải thích văn hóa" },
            { id: 19, name: "Khảo Cổ Học", description: "Hiển thị hình ảnh hiện vật lịch sử", type: "history", effect: "Hiển thị hiện vật" },
            { id: 20, name: "Di Sản Thế Giới", description: "Giới thiệu các di sản UNESCO", type: "history", effect: "Giới thiệu di sản" },
            
            // Đố vui & Sáng tạo (5 skills)
            { id: 21, name: "Logic Thiên Tài", description: "Phân tích quy luật logic trong câu đố", type: "puzzle", effect: "Phân tích logic" },
            { id: 22, name: "Sáng Tạo Vô Hạn", description: "Gợi ý các hướng giải quyết sáng tạo", type: "puzzle", effect: "Gợi ý sáng tạo" },
            { id: 23, name: "Tư Duy Phản Biện", description: "Phân tích vấn đề từ nhiều góc độ", type: "puzzle", effect: "Phân tích đa chiều" },
            { id: 24, name: "Giải Mã Bí Ẩn", description: "Tiết lộ manh mối cho câu đố phức tạp", type: "puzzle", effect: "Tiết lộ manh mối" },
            { id: 25, name: "Trí Tuệ Đám Đông", description: "Hiển thị các phương án phổ biến", type: "puzzle", effect: "Phương án phổ biến" },
            
            // Hỗ trợ đa môn (5 skills)
            { id: 26, name: "Bách Khoa Toàn Thư", description: "Cung cấp thông tin bổ sung kiến thức", type: "general", effect: "Thông tin bổ sung" },
            { id: 27, name: "Mẹo Ghi Nhớ", description: "Đưa ra phương pháp ghi nhớ hiệu quả", type: "general", effect: "Phương pháp ghi nhớ" },
            { id: 28, name: "Phân Tích Đề Bài", description: "Phân tích yêu cầu và hướng giải quyết", type: "general", effect: "Phân tích đề bài" },
            { id: 29, name: "Kiến Thức Liên Môn", description: "Kết nối kiến thức giữa các môn học", type: "general", effect: "Kết nối liên môn" },
            { id: 30, name: "Học Tập Chủ Động", description: "Đề xuất chủ đề học tập tiếp theo", type: "general", effect: "Đề xuất học tập" }
        ];

        // Database câu hỏi mẫu
        const questionDatabase = {
            math: [
                { question: "Tính: 125 + 375", answer: "500", hint: "Cộng hàng đơn vị trước: 5 + 5 = 10, viết 0 nhớ 1" },
                { question: "Tìm x: x + 25 = 80", answer: "55", hint: "x = 80 - 25" },
                { question: "Tính: 45 × 6", answer: "270", hint: "40 × 6 = 240, 5 × 6 = 30, tổng 270" },
                { question: "Chia: 144 ÷ 12", answer: "12", hint: "12 × 12 = 144" },
                { question: "Tính: 3² + 4²", answer: "25", hint: "3² = 9, 4² = 16, 9 + 16 = 25" },
                { question: "Tính: 78 - 29", answer: "49", hint: "78 - 20 = 58, 58 - 9 = 49" },
                { question: "Tính: 15 × 8", answer: "120", hint: "10 × 8 = 80, 5 × 8 = 40, tổng 120" },
                { question: "Tính: 96 ÷ 8", answer: "12", hint: "80 ÷ 8 = 10, 16 ÷ 8 = 2, tổng 12" },
                { question: "Tính: 7 × 9", answer: "63", hint: "7 × 10 = 70, 70 - 7 = 63" },
                { question: "Tính: 256 ÷ 16", answer: "16", hint: "16 × 16 = 256" }
            ],
            science: [
                { question: "Công thức tính vận tốc", answer: "v = s/t", hint: "Quãng đường chia thời gian" },
                { question: "Nước sôi ở bao nhiêu độ C?", answer: "100", hint: "Ở điều kiện áp suất tiêu chuẩn" },
                { question: "Công thức hóa học của nước", answer: "h2o", hint: "2 nguyên tử H, 1 nguyên tử O" },
                { question: "Tim người có mấy ngăn?", answer: "4", hint: "2 tâm nhĩ, 2 tâm thất" },
                { question: "Khí nào chiếm tỉ lệ cao nhất trong không khí?", answer: "nitơ", hint: "Khoảng 78%" },
                { question: "Nguyên tố nào phổ biến nhất trong vũ trụ?", answer: "hydro", hint: "Nguyên tố nhẹ nhất" },
                { question: "Cây xanh quang hợp vào thời gian nào?", answer: "ban ngày", hint: "Cần ánh sáng mặt trời" },
                { question: "Trái Đất quay quanh trục mất bao lâu?", answer: "24 giờ", hint: "Một ngày một đêm" },
                { question: "Kim loại nào dẫn điện tốt nhất?", answer: "bạc", hint: "Sau đó là đồng, vàng, nhôm" },
                { question: "Nguyên tố nào cần cho sự sống của cây?", answer: "nitơ", hint: "Có trong phân đạm" }
            ],
            english: [
                { question: "Dịch 'house' sang tiếng Việt", answer: "ngôi nhà", hint: "Nơi để sống" },
                { question: "Số 15 trong tiếng Anh", answer: "fifteen", hint: "Mười lăm" },
                { question: "Màu xanh da trời trong tiếng Anh", answer: "blue", hint: "Blue sky" },
                { question: "Con chó trong tiếng Anh", answer: "dog", hint: "Thú cưng phổ biến" },
                { question: "Từ 'happy' nghĩa là gì?", answer: "vui vẻ", hint: "Cảm xúc tích cực" },
                { question: "Dịch 'book' sang tiếng Việt", answer: "quyển sách", hint: "Để đọc" },
                { question: "Số 20 trong tiếng Anh", answer: "twenty", hint: "Hai mươi" },
                { question: "Màu đỏ trong tiếng Anh", answer: "red", hint: "Màu của máu" },
                { question: "Con mèo trong tiếng Anh", answer: "cat", hint: "Thú cưng hay leo trèo" },
                { question: "Từ 'water' nghĩa là gì?", answer: "nước", hint: "Chất lỏng cần cho sự sống" }
            ],
            history: [
                { question: "Ai là vị vua đầu tiên của nước Văn Lang?", answer: "hùng vương", hint: "Thời đại Hùng Vương" },
                { question: "Trận Bạch Đằng năm 938 do ai lãnh đạo?", answer: "ngô quyền", hint: "Đánh tan quân Nam Hán" },
                { question: "Chiến thắng Điện Biên Phủ năm nào?", answer: "1954", hint: "Thế kỷ 20" },
                { question: "Ai là Chủ tịch nước đầu tiên?", answer: "hồ chí minh", hint: "Bác Hồ" },
                { question: "Ngày Giải phóng miền Nam?", answer: "30/4/1975", hint: "Ngày thống nhất đất nước" },
                { question: "Ai là tác giả của Bình Ngô đại cáo?", answer: "nguyễn trãi", hint: "Danh nhân văn hóa thế giới" },
                { question: "Nhà Lý dời đô về Thăng Long năm nào?", answer: "1010", hint: "Thế kỷ 11" },
                { question: "Ai lãnh đạo cuộc khởi nghĩa Lam Sơn?", answer: "lê lợi", hint: "Vua Lê Thái Tổ" },
                { question: "Chiến thắng Ngọc Hồi - Đống Đa năm nào?", answer: "1789", hint: "Thế kỷ 18" },
                { question: "Ai là vị vua cuối cùng của triều Nguyễn?", answer: "bảo đại", hint: "Vị hoàng đế cuối cùng" }
            ],
            puzzle: [
                { question: "Con gì càng kéo càng ngắn?", answer: "điếu thuốc lá", hint: "Khi hút sẽ ngắn dần" },
                { question: "Cái gì càng nhiều càng ít thấy?", answer: "bóng tối", hint: "Khi có ánh sáng" },
                { question: "Số nào lớn nhất có 2 chữ số?", answer: "99", hint: "Hai chữ số 9" },
                { question: "1/2 của 100 là bao nhiêu?", answer: "50", hint: "100 chia 2" },
                { question: "Cái gì bạn có thể giữ nhưng không chạm được?", answer: "lời hứa", hint: "Cam kết bằng lời" },
                { question: "Cái gì có thể đi mà không có chân?", answer: "thời gian", hint: "Ngày tháng trôi qua" },
                { question: "Cái gì càng để lâu càng nhẹ?", answer: "cây nến", hint: "Khi cháy sẽ nhỏ dần" },
                { question: "Cái gì không ai muốn có nhưng khi có rồi không ai muốn mất?", answer: "tuổi già", hint: "Khi lớn tuổi" },
                { question: "Cái gì luôn đến mà không bao giờ đến?", answer: "ngày mai", hint: "Khi đến rồi thì thành hôm nay" },
                { question: "Cái gì càng lấy càng nhiều?", answer: "cái hố", hint: "Khi đào đất lên" }
            ]
        };

        // Khởi tạo trò chơi
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            
            let currentPlayer = null;
            let currentSkills = [];
            let selectedSkill = null;
            let questionsSinceLastSkill = 0;
            let usedQuestions = []; // Mảng lưu các câu hỏi đã sử dụng
            
            const gameData = {
                currentStage: 1,
                score: 0,
                hearts: 3,
                maxHearts: 5,
                stages: [],
                usedSkills: []
            };
            
            const elements = {
                playerSetup: document.getElementById('player-setup'),
                mainContainer: document.getElementById('main-container'),
                playerNameInput: document.getElementById('player-name-input'),
                startGameBtn: document.getElementById('start-game-btn'),
                playerAvatar: document.getElementById('player-avatar'),
                playerName: document.getElementById('player-name'),
                sceneTitle: document.getElementById('scene-title'),
                sceneDescription: document.getElementById('scene-description'),
                sceneImage: document.getElementById('scene-image'),
                question: document.getElementById('question'),
                answerInput: document.getElementById('answer-input'),
                submitBtn: document.getElementById('submit-btn'),
                feedback: document.getElementById('feedback'),
                hint: document.getElementById('hint'),
                heartsContainer: document.getElementById('hearts'),
                score: document.getElementById('score'),
                progressBar: document.getElementById('progress-bar'),
                stageIndicator: document.getElementById('stage-indicator'),
                skillsList: document.getElementById('skills-list'),
                skillSelection: document.getElementById('skill-selection'),
                skillOptions: document.getElementById('skill-options'),
                confirmSkillBtn: document.getElementById('confirm-skill-btn'),
                activeSkill: document.getElementById('active-skill'),
                activeSkillDescription: document.getElementById('active-skill-description'),
                useSkillBtn: document.getElementById('use-skill-btn')
            };
            
            // Xử lý chọn avatar
            document.querySelectorAll('.avatar-option').forEach(option => {
                option.addEventListener('click', function() {
                    document.querySelectorAll('.avatar-option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    this.classList.add('selected');
                });
            });
            
            // Bắt đầu trò chơi
            elements.startGameBtn.addEventListener('click', function() {
                const playerName = elements.playerNameInput.value.trim();
                const selectedAvatar = document.querySelector('.avatar-option.selected').getAttribute('data-avatar');
                
                if (playerName) {
                    currentPlayer = {
                        name: playerName,
                        avatar: selectedAvatar
                    };
                    
                    elements.playerName.textContent = currentPlayer.name;
                    elements.playerAvatar.textContent = currentPlayer.avatar;
                    
                    elements.playerSetup.style.display = 'none';
                    elements.mainContainer.style.display = 'block';
                    
                    // Khởi tạo trò chơi
                    initializeGame();
                } else {
                    alert('Vui lòng nhập tên của bạn!');
                }
            });
            
            // Khởi tạo trò chơi
            function initializeGame() {
                usedQuestions = []; // Reset danh sách câu hỏi đã dùng
                generateNewStage();
                updateHearts();
                updateScore();
                updateSkillsList();
            }
            
            // Tạo màn chơi mới
            function generateNewStage() {
                const categories = Object.keys(questionDatabase);
                const randomCategory = categories[Math.floor(Math.random() * categories.length)];
                const questions = questionDatabase[randomCategory];
                
                // Lọc ra những câu hỏi chưa được sử dụng
                const availableQuestions = questions.filter(q => 
                    !usedQuestions.includes(q.question)
                );
                
                // Nếu đã dùng hết câu hỏi, reset danh sách đã dùng
                if (availableQuestions.length === 0) {
                    usedQuestions = [];
                    generateNewStage();
                    return;
                }
                
                const randomQuestion = availableQuestions[Math.floor(Math.random() * availableQuestions.length)];
                
                // Thêm câu hỏi vào danh sách đã dùng
                usedQuestions.push(randomQuestion.question);
                
                gameData.stages.push({
                    title: `Màn ${gameData.currentStage}: Thử thách ${randomCategory}`,
                    description: getStageDescription(gameData.currentStage, randomCategory),
                    question: randomQuestion.question,
                    answer: randomQuestion.answer,
                    hint: randomQuestion.hint,
                    image: getStageImage(gameData.currentStage, randomCategory),
                    category: randomCategory
                });
                
                loadCurrentStage();
            }
            
            function getStageDescription(stage, category) {
                const descriptions = {
                    math: `Màn ${stage} - Thử thách Toán học. Hãy vận dụng trí thông minh!`,
                    science: `Màn ${stage} - Khám phá Khoa học. Kiến thức tự nhiên sẽ giúp bạn!`,
                    english: `Màn ${stage} - Phiêu lưu Tiếng Anh. Thể hiện khả năng ngoại ngữ!`,
                    history: `Màn ${stage} - Hành trình Lịch sử. Hiểu biết quá khứ quan trọng!`,
                    puzzle: `Màn ${stage} - Đố vui Sáng tạo. Hãy suy nghĩ thật kỹ!`
                };
                
                return descriptions[category] || `Màn ${stage} - Thử thách Tri thức. Hãy cố gắng hết sức!`;
            }
            
            function getStageImage(stage, category) {
                const colors = ['4a148c', '8e24aa', '5e35b1', '3949ab', '1e88e5'];
                const color = colors[(stage - 1) % colors.length];
                const categoryNames = {
                    math: "Toán Học",
                    science: "Khoa Học",
                    english: "Tiếng Anh", 
                    history: "Lịch Sử",
                    puzzle: "Đố Vui"
                };
                
                return `https://via.placeholder.com/800x200/${color}/ffffff?text=Màn+${stage}+-+${categoryNames[category]}`;
            }
            
            // Cập nhật danh sách kỹ năng
            function updateSkillsList() {
                elements.skillsList.innerHTML = '';
                
                if (currentSkills.length === 0) {
                    elements.skillsList.innerHTML = '<div class="skill-item">Chưa có kỹ năng nào</div>';
                    elements.activeSkill.style.display = 'none';
                } else {
                    currentSkills.forEach(skill => {
                        const skillDiv = document.createElement('div');
                        skillDiv.className = 'skill-item';
                        skillDiv.innerHTML = `
                            <div class="skill-name">${skill.name}</div>
                            <div class="skill-description">${skill.description}</div>
                        `;
                        elements.skillsList.appendChild(skillDiv);
                    });
                    
                    if (selectedSkill) {
                        elements.activeSkillDescription.textContent = `${selectedSkill.name}: ${selectedSkill.effect}`;
                        elements.activeSkill.style.display = 'block';
                    }
                }
            }
            
            // Cập nhật giao diện trái tim
            function updateHearts() {
                elements.heartsContainer.innerHTML = '';
                for (let i = 0; i < gameData.maxHearts; i++) {
                    const heart = document.createElement('span');
                    heart.classList.add('heart');
                    if (i < gameData.hearts) {
                        heart.textContent = '❤️';
                    } else {
                        heart.textContent = '♡';
                        heart.style.opacity = '0.5';
                    }
                    elements.heartsContainer.appendChild(heart);
                }
            }
            
            // Cập nhật điểm số
            function updateScore() {
                elements.score.textContent = gameData.score;
            }
            
            // Cập nhật thanh tiến trình
            function updateProgress() {
                const progress = (questionsSinceLastSkill % 5) * 20;
                elements.progressBar.style.width = `${progress}%`;
                elements.stageIndicator.textContent = `Màn ${gameData.currentStage} - Tiến độ: ${questionsSinceLastSkill}/5`;
            }
            
            // Hiển thị phản hồi
            function showFeedback(message, isCorrect) {
                elements.feedback.textContent = message;
                elements.feedback.className = 'feedback ' + (isCorrect ? 'correct' : 'incorrect');
                elements.feedback.style.display = 'block';
                
                setTimeout(() => {
                    elements.feedback.style.display = 'none';
                }, 3000);
            }
            
            // Hiển thị gợi ý
            function showHint() {
                const currentStage = gameData.stages[gameData.currentStage - 1];
                elements.hint.textContent = `💡 Gợi ý: ${currentStage.hint}`;
                elements.hint.style.display = 'block';
            }
            
            // Chuyển sang màn tiếp theo
            function nextStage() {
                gameData.currentStage++;
                questionsSinceLastSkill++;
                
                // Kiểm tra xem đã đến lúc chọn skill chưa
                if (questionsSinceLastSkill >= 5) {
                    showSkillSelection();
                    questionsSinceLastSkill = 0;
                } else {
                    generateNewStage();
                }
            }
            
            // Hiển thị lựa chọn skill
            function showSkillSelection() {
                // Chọn ngẫu nhiên 3 skill từ database
                const randomSkills = [];
                const availableSkills = [...skillsDatabase];
                
                for (let i = 0; i < 3; i++) {
                    const randomIndex = Math.floor(Math.random() * availableSkills.length);
                    randomSkills.push(availableSkills[randomIndex]);
                    availableSkills.splice(randomIndex, 1);
                }
                
                // Hiển thị skill options
                elements.skillOptions.innerHTML = '';
                randomSkills.forEach(skill => {
                    const skillOption = document.createElement('div');
                    skillOption.className = 'skill-option';
                    skillOption.innerHTML = `
                        <div class="skill-name">${skill.name}</div>
                        <div class="skill-description">${skill.description}</div>
                        <div class="skill-effect">Hiệu ứng: ${skill.effect}</div>
                    `;
                    skillOption.addEventListener('click', function() {
                        document.querySelectorAll('.skill-option').forEach(opt => {
                            opt.classList.remove('selected');
                        });
                        this.classList.add('selected');
                        selectedSkill = skill;
                    });
                    elements.skillOptions.appendChild(skillOption);
                });
                
                elements.skillSelection.style.display = 'flex';
            }
            
            // Xác nhận chọn skill
            elements.confirmSkillBtn.addEventListener('click', function() {
                if (selectedSkill) {
                    currentSkills.push(selectedSkill);
                    updateSkillsList();
                    elements.skillSelection.style.display = 'none';
                    selectedSkill = null;
                    
                    // Tiếp tục game
                    generateNewStage();
                } else {
                    alert('Vui lòng chọn một kỹ năng!');
                }
            });
            
            // Sử dụng skill
            elements.useSkillBtn.addEventListener('click', function() {
                if (selectedSkill) {
                    // Thực hiện hiệu ứng skill
                    applySkillEffect(selectedSkill);
                    
                    // Xóa skill đã sử dụng
                    const skillIndex = currentSkills.findIndex(skill => skill.id === selectedSkill.id);
                    if (skillIndex > -1) {
                        currentSkills.splice(skillIndex, 1);
                    }
                    
                    // Reset selected skill
                    selectedSkill = null;
                    updateSkillsList();
                    
                    showFeedback('Đã sử dụng kỹ năng đặc biệt!', true);
                }
            });
            
            // Áp dụng hiệu ứng skill
            function applySkillEffect(skill) {
                const currentStage = gameData.stages[gameData.currentStage - 1];
                
                // Thực hiện các hiệu ứng khác nhau dựa trên loại skill
                switch(skill.type) {
                    case 'math':
                        if (currentStage.category === 'math') {
                            showFeedback('Kỹ năng Toán học được kích hoạt! Hiển thị đáp án...', true);
                        }
                        break;
                    case 'science':
                        if (currentStage.category === 'science') {
                            showFeedback('Kỹ năng Khoa học được kích hoạt! Thông tin bổ sung...', true);
                        }
                        break;
                    case 'english':
                        if (currentStage.category === 'english') {
                            showFeedback('Kỹ năng Tiếng Anh được kích hoạt! Phiên âm và định nghĩa...', true);
                        }
                        break;
                    default:
                        showFeedback('Kỹ năng đặc biệt được kích hoạt!', true);
                }
                
                // Ghi lại skill đã sử dụng
                gameData.usedSkills.push(skill.name);
            }
            
            // Tải màn chơi hiện tại
            function loadCurrentStage() {
                const currentStage = gameData.stages[gameData.currentStage - 1];
                
                elements.sceneTitle.textContent = currentStage.title;
                elements.sceneDescription.textContent = currentStage.description;
                elements.question.textContent = currentStage.question;
                elements.sceneImage.src = currentStage.image;
                elements.answerInput.value = '';
                elements.hint.style.display = 'none';
                
                updateProgress();
            }
            
            // Xử lý khi người chơi trả lời
            function handleAnswer() {
                const userAnswer = elements.answerInput.value.trim().toLowerCase();
                const currentStage = gameData.stages[gameData.currentStage - 1];
                
                if (userAnswer === currentStage.answer) {
                    // Trả lời đúng
                    gameData.score += 10;
                    if (gameData.hearts < gameData.maxHearts) {
                        gameData.hearts++;
                    }
                    
                    showFeedback('Chính xác! +10 điểm và +1 trái tim 🎉', true);
                    updateScore();
                    updateHearts();
                    
                    // Chuyển màn sau 1.5 giây
                    setTimeout(nextStage, 1500);
                } else {
                    // Trả lời sai
                    gameData.hearts--;
                    showFeedback('Sai rồi! -1 trái tim 😢 Thử lại nhé!', false);
                    updateHearts();
                    showHint();
                    
                    // Kiểm tra nếu hết trái tim
                    if (gameData.hearts <= 0) {
                        setTimeout(() => {
                            if (confirm('Bạn đã hết trái tim! Trò chơi kết thúc. Điểm của bạn: ' + gameData.score + '. Chơi lại không?')) {
                                resetGame();
                            }
                        }, 1000);
                    }
                }
            }
            
            // Reset trò chơi
            function resetGame() {
                gameData.currentStage = 1;
                gameData.score = 0;
                gameData.hearts = 3;
                gameData.stages = [];
                currentSkills = [];
                selectedSkill = null;
                questionsSinceLastSkill = 0;
                usedQuestions = [];
                
                initializeGame();
                
                elements.question.style.display = 'block';
                elements.inputContainer.style.display = 'flex';
            }
            
            // Gắn sự kiện cho trò chơi
            elements.submitBtn.addEventListener('click', handleAnswer);
            elements.answerInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    handleAnswer();
                }
            });
        });
    </script>
</body>
</html>
