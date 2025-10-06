<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VŨ TRỤ TRI THỨC</title>
    <style>
        /* CSS nâng cấp với hơn 2000 dòng code */
        :root {
            --primary: #4a148c;
            --secondary: #ff6f00;
            --accent: #00c853;
            --danger: #d50000;
            --light: #f3e5f5;
            --dark: #1a237e;
            --legendary: #ffd700;
            --epic: #9c27b0;
            --rare: #2196f3;
            --common: #78909c;
            --mythic: #ff6d00;
            --divine: #00e5ff;
            --cosmic: #7c4dff;
            --nebula: #e040fb;
            --quantum: #18ffff;
            --galaxy: #311b92;
            --blackhole: #000051;
            --supernova: #ff4081;
            --grade6: #4caf50;
            --grade7: #2196f3;
            --grade8: #ff9800;
            --grade9: #f44336;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--galaxy) 0%, var(--blackhole) 100%);
            color: var(--light);
            min-height: 100vh;
            padding: 10px;
            overflow-x: hidden;
        }
        
        /* Hiệu ứng vũ trụ nâng cấp */
        .universe-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 10% 20%, rgba(120, 119, 198, 0.4) 0%, transparent 40%),
                radial-gradient(circle at 90% 80%, rgba(255, 119, 198, 0.3) 0%, transparent 45%),
                radial-gradient(circle at 30% 90%, rgba(120, 219, 255, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 70% 10%, rgba(255, 215, 0, 0.2) 0%, transparent 55%),
                radial-gradient(circle at 50% 50%, rgba(124, 77, 255, 0.2) 0%, transparent 60%);
            z-index: -3;
            animation: universeMove 30s infinite linear;
        }
        
        @keyframes universeMove {
            0% { transform: scale(1) rotate(0deg); }
            25% { transform: scale(1.05) rotate(90deg); }
            50% { transform: scale(1.1) rotate(180deg); }
            75% { transform: scale(1.05) rotate(270deg); }
            100% { transform: scale(1) rotate(360deg); }
        }
        
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
        }
        
        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite alternate;
        }
        
        @keyframes twinkle {
            0% { opacity: 0.2; transform: scale(0.7); }
            50% { opacity: 0.8; transform: scale(1.1); }
            100% { opacity: 0.4; transform: scale(0.9); }
        }
        
        .cosmic-orbs {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .cosmic-orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(60px);
            opacity: 0.7;
            animation: cosmicFloat 20s infinite linear;
        }
        
        @keyframes cosmicFloat {
            0% {
                transform: translate(0, 0) rotate(0deg) scale(1);
            }
            25% {
                transform: translate(150px, 80px) rotate(90deg) scale(1.2);
            }
            50% {
                transform: translate(80px, 150px) rotate(180deg) scale(1.5);
            }
            75% {
                transform: translate(-80px, 100px) rotate(270deg) scale(1.2);
            }
            100% {
                transform: translate(0, 0) rotate(360deg) scale(1);
            }
        }
        
        .game-container {
            max-width: 1400px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(25px);
            border-radius: 30px;
            box-shadow: 
                0 25px 50px rgba(0, 0, 0, 0.5),
                0 0 150px rgba(155, 39, 176, 0.4),
                0 0 300px rgba(124, 77, 255, 0.3);
            overflow: hidden;
            position: relative;
            border: 3px solid rgba(255, 255, 255, 0.2);
        }
        
        .cosmic-border {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, 
                transparent 0%, 
                rgba(255, 215, 0, 0.15) 15%, 
                transparent 30%, 
                rgba(156, 39, 176, 0.15) 45%, 
                transparent 60%, 
                rgba(33, 150, 243, 0.15) 75%, 
                transparent 90%);
            animation: borderGlow 6s infinite linear;
            z-index: -1;
            border-radius: 30px;
        }
        
        @keyframes borderGlow {
            0% { background-position: 0% 0%; }
            100% { background-position: 400% 400%; }
        }
        
        .header {
            background: linear-gradient(135deg, #8E24AA 0%, #4A148C 30%, #1A237E 60%, #000051 100%);
            padding: 30px 25px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: -150%;
            left: -150%;
            width: 400%;
            height: 400%;
            background: radial-gradient(circle, rgba(255,255,255,0.15) 0%, transparent 70%);
            animation: cosmicPulse 8s infinite alternate;
        }
        
        @keyframes cosmicPulse {
            0% {
                transform: scale(0.7) rotate(0deg);
                opacity: 0.2;
            }
            100% {
                transform: scale(1.6) rotate(180deg);
                opacity: 0.8;
            }
        }
        
        .title {
            font-size: clamp(3rem, 7vw, 5rem);
            margin-bottom: 20px;
            text-shadow: 
                0 0 25px rgba(255, 255, 255, 0.9),
                0 0 50px rgba(255, 235, 59, 0.7),
                0 0 80px rgba(255, 193, 7, 0.5),
                0 0 120px rgba(255, 87, 34, 0.3);
            background: linear-gradient(45deg, #FFEB3B, #FF9800, #FF4081, #E040FB, #7C4DFF, #00E5FF);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: titleGlow 4s infinite alternate;
            font-weight: 900;
            letter-spacing: 3px;
        }
        
        @keyframes titleGlow {
            from {
                filter: hue-rotate(0deg);
                text-shadow: 
                    0 0 25px rgba(255, 255, 255, 0.9),
                    0 0 50px rgba(255, 235, 59, 0.7);
            }
            to {
                filter: hue-rotate(360deg);
                text-shadow: 
                    0 0 35px rgba(255, 255, 255, 1),
                    0 0 70px rgba(255, 193, 7, 0.9),
                    0 0 110px rgba(255, 87, 34, 0.7),
                    0 0 150px rgba(124, 77, 255, 0.5);
            }
        }
        
        .subtitle {
            font-size: clamp(1.5rem, 4vw, 2.2rem);
            opacity: 0.9;
            text-shadow: 0 3px 15px rgba(0, 0, 0, 0.6);
            background: linear-gradient(45deg, #B388FF, #82B1FF, #80DEEA);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 600;
            margin-bottom: 10px;
        }
        
        .game-content {
            padding: 30px;
            position: relative;
        }
        
        .stats {
            display: grid;
            grid-template-columns: 1fr auto 1fr;
            align-items: center;
            gap: 25px;
            margin-bottom: 30px;
            background: rgba(0, 0, 0, 0.4);
            padding: 25px;
            border-radius: 25px;
            box-shadow: 
                0 10px 20px rgba(0, 0, 0, 0.4),
                inset 0 1px 0 rgba(255, 255, 255, 0.15);
            border: 2px solid rgba(255, 255, 255, 0.15);
            position: relative;
            overflow: hidden;
        }
        
        .stats::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(74, 20, 140, 0.3) 0%, 
                rgba(26, 35, 126, 0.2) 50%, 
                rgba(0, 0, 81, 0.3) 100%);
            z-index: -1;
        }
        
        .player-info {
            display: flex;
            align-items: center;
            gap: 20px;
        }
        
        .player-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: linear-gradient(135deg, #FF6F00, #FFCA28, #FFD700);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 2rem;
            box-shadow: 0 6px 20px rgba(255, 111, 0, 0.5);
            border: 3px solid rgba(255, 255, 255, 0.4);
            animation: avatarPulse 3s infinite alternate;
            position: relative;
            overflow: hidden;
        }
        
        .player-avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
        }
        
        .player-avatar::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, 
                transparent, 
                rgba(255, 255, 255, 0.3), 
                transparent);
            transform: rotate(45deg);
            animation: avatarShine 4s infinite;
        }
        
        @keyframes avatarShine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }
        
        @keyframes avatarPulse {
            0% { transform: scale(1); box-shadow: 0 6px 20px rgba(255, 111, 0, 0.5); }
            100% { transform: scale(1.08); box-shadow: 0 8px 25px rgba(255, 111, 0, 0.7); }
        }
        
        .player-name {
            font-size: 1.6rem;
            font-weight: bold;
            background: linear-gradient(45deg, #FFEB3B, #FF9800, #FF6F00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 3px 6px rgba(0, 0, 0, 0.4);
        }
        
        .player-level {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-top: 5px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .level-bar {
            width: 100px;
            height: 8px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 4px;
            overflow: hidden;
        }
        
        .level-progress {
            height: 100%;
            background: linear-gradient(90deg, #FF6F00, #FFCA28);
            border-radius: 4px;
            transition: width 0.5s ease;
        }
        
        .hearts {
            display: flex;
            gap: 10px;
            justify-content: center;
            align-items: center;
        }
        
        .heart {
            color: var(--danger);
            font-size: 2.5rem;
            animation: heartbeat 2s infinite;
            text-shadow: 0 0 15px rgba(213, 0, 0, 0.7);
            position: relative;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.4); }
            10% { transform: scale(1); }
            15% { transform: scale(1.4); }
            20% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        .score-container {
            text-align: right;
        }
        
        .score {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--secondary);
            text-shadow: 
                0 0 15px rgba(255, 111, 0, 0.7),
                0 0 30px rgba(255, 111, 0, 0.5);
            background: linear-gradient(45deg, #FF6F00, #FFCA28, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .scene {
            background: rgba(0, 0, 0, 0.5);
            border-radius: 25px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 
                0 15px 35px rgba(0, 0, 0, 0.5),
                inset 0 1px 0 rgba(255, 255, 255, 0.15);
            border: 2px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
            min-height: 250px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        .scene::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(74, 20, 140, 0.4) 0%, 
                rgba(26, 35, 126, 0.3) 50%, 
                rgba(0, 0, 81, 0.4) 100%);
            z-index: -1;
        }
        
        .scene-title {
            font-size: 2.2rem;
            margin-bottom: 20px;
            color: var(--secondary);
            text-align: center;
            text-shadow: 0 3px 10px rgba(0, 0, 0, 0.6);
            background: linear-gradient(45deg, #FF6F00, #FFCA28, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
        }
        
        .scene-title::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, transparent, #FF6F00, transparent);
        }
        
        .scene-description {
            font-size: 1.3rem;
            line-height: 1.7;
            margin-bottom: 20px;
            text-align: center;
            opacity: 0.9;
            padding: 0 20px;
        }
        
        .question {
            font-size: 1.8rem;
            font-weight: bold;
            text-align: center;
            margin: 25px 0;
            padding: 25px;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 20px;
            border-left: 8px solid var(--accent);
            animation: slideIn 0.6s ease-out;
            word-break: break-word;
            box-shadow: 
                0 6px 20px rgba(0, 0, 0, 0.4),
                inset 0 1px 0 rgba(255, 255, 255, 0.15);
            position: relative;
        }
        
        .question::before {
            content: '❓';
            position: absolute;
            top: -15px;
            left: 20px;
            font-size: 2rem;
            background: var(--accent);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(0, 200, 83, 0.5);
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .input-container {
            display: flex;
            gap: 20px;
            margin-top: 25px;
            flex-direction: column;
        }
        
        @media (min-width: 768px) {
            .input-container {
                flex-direction: row;
            }
        }
        
        input {
            flex: 1;
            padding: 20px 25px;
            border: none;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.95);
            color: #333;
            font-size: 1.3rem;
            box-shadow: 
                0 6px 20px rgba(0, 0, 0, 0.25),
                inset 0 3px 6px rgba(0, 0, 0, 0.1);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            width: 100%;
            border: 3px solid transparent;
        }
        
        input:focus {
            outline: none;
            box-shadow: 
                0 0 0 4px var(--accent),
                0 10px 30px rgba(0, 200, 83, 0.4);
            transform: scale(1.03);
            border-color: var(--accent);
        }
        
        button {
            padding: 20px 35px;
            border: none;
            border-radius: 15px;
            background: linear-gradient(135deg, var(--secondary), var(--accent), var(--cosmic));
            color: white;
            font-weight: bold;
            font-size: 1.3rem;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 
                0 8px 25px rgba(255, 111, 0, 0.5),
                0 3px 6px rgba(0, 0, 0, 0.2);
            width: 100%;
            position: relative;
            overflow: hidden;
        }
        
        @media (min-width: 768px) {
            button {
                width: auto;
            }
        }
        
        button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255, 255, 255, 0.5), 
                transparent);
            transition: left 0.6s;
        }
        
        button:hover::before {
            left: 100%;
        }
        
        button:hover {
            transform: translateY(-5px);
            box-shadow: 
                0 15px 35px rgba(255, 111, 0, 0.7),
                0 5px 10px rgba(0, 0, 0, 0.3);
        }
        
        button:active {
            transform: translateY(2px);
            box-shadow: 
                0 5px 20px rgba(255, 111, 0, 0.5),
                0 2px 4px rgba(0, 0, 0, 0.2);
        }
        
        .feedback {
            margin-top: 25px;
            padding: 25px;
            border-radius: 20px;
            text-align: center;
            font-weight: bold;
            font-size: 1.5rem;
            animation: popIn 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            display: none;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
        }
        
        .feedback::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(255, 255, 255, 0.1) 0%, 
                transparent 50%, 
                rgba(255, 255, 255, 0.1) 100%);
            z-index: -1;
        }
        
        @keyframes popIn {
            0% {
                transform: scale(0.7) translateY(30px);
                opacity: 0;
            }
            100% {
                transform: scale(1) translateY(0);
                opacity: 1;
            }
        }
        
        .correct {
            background: linear-gradient(135deg, rgba(0, 200, 83, 0.4), rgba(76, 175, 80, 0.3));
            border: 3px solid var(--accent);
            color: var(--accent);
            text-shadow: 0 3px 6px rgba(0, 0, 0, 0.4);
        }
        
        .incorrect {
            background: linear-gradient(135deg, rgba(213, 0, 0, 0.4), rgba(244, 67, 54, 0.3));
            border: 3px solid var(--danger);
            color: var(--danger);
            text-shadow: 0 3px 6px rgba(0, 0, 0, 0.4);
        }
        
        .hint {
            margin-top: 20px;
            padding: 20px;
            background: rgba(255, 193, 7, 0.25);
            border-radius: 15px;
            border-left: 6px solid #ffc107;
            display: none;
            animation: fadeIn 0.6s;
            font-size: 1.2rem;
            box-shadow: 0 4px 15px rgba(255, 193, 7, 0.3);
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .skill-effect {
            margin-top: 20px;
            padding: 20px;
            background: rgba(124, 77, 255, 0.25);
            border-radius: 15px;
            border-left: 6px solid #7c4dff;
            display: none;
            animation: fadeIn 0.6s;
            font-size: 1.2rem;
            box-shadow: 0 4px 15px rgba(124, 77, 255, 0.3);
        }
        
        .progress-container {
            margin-top: 25px;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 20px;
            overflow: hidden;
            height: 15px;
            box-shadow: inset 0 3px 6px rgba(0, 0, 0, 0.4);
            position: relative;
        }
        
        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--secondary), var(--accent), var(--cosmic), var(--supernova));
            width: 0%;
            transition: width 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            border-radius: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255, 255, 255, 0.5), 
                transparent);
            animation: progressShine 3s infinite;
        }
        
        @keyframes progressShine {
            0% { left: -100%; }
            100% { left: 100%; }
        }
        
        .stage-indicator {
            text-align: center;
            margin-top: 15px;
            font-size: 1.2rem;
            opacity: 0.9;
            text-shadow: 0 3px 6px rgba(0, 0, 0, 0.4);
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }
        
        .stage-indicator::before, .stage-indicator::after {
            content: '✦';
            color: var(--secondary);
            font-size: 1.5rem;
            animation: twinkle 2s infinite alternate;
        }
        
        .active-skill {
            margin-top: 30px;
            padding: 25px;
            background: linear-gradient(135deg, rgba(255, 111, 0, 0.4), rgba(255, 61, 0, 0.3));
            border-radius: 25px;
            text-align: center;
            display: none;
            box-shadow: 
                0 10px 30px rgba(255, 111, 0, 0.4),
                inset 0 1px 0 rgba(255, 255, 255, 0.15);
            border: 3px solid rgba(255, 111, 0, 0.4);
            animation: skillPulse 4s infinite alternate;
            position: relative;
            overflow: hidden;
        }
        
        .active-skill::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(255, 255, 255, 0.1) 0%, 
                transparent 50%, 
                rgba(255, 255, 255, 0.1) 100%);
            z-index: -1;
        }
        
        @keyframes skillPulse {
            0% { 
                box-shadow: 0 10px 30px rgba(255, 111, 0, 0.4);
                transform: scale(1);
            }
            100% { 
                box-shadow: 0 15px 40px rgba(255, 111, 0, 0.6);
                transform: scale(1.02);
            }
        }
        
        .skill-button {
            background: linear-gradient(135deg, #FF4081, #7C4DFF, #00E5FF, #18FFFF);
            margin-top: 20px;
            font-size: 1.5rem;
            padding: 25px 50px;
            box-shadow: 
                0 10px 30px rgba(255, 64, 129, 0.5),
                0 5px 10px rgba(0, 0, 0, 0.3);
        }
        
        .skills-container {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 25px;
            padding: 30px;
            margin-top: 30px;
            box-shadow: 
                0 15px 35px rgba(0, 0, 0, 0.5),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.15);
            position: relative;
        }
        
        .skills-container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(74, 20, 140, 0.2) 0%, 
                rgba(26, 35, 126, 0.15) 50%, 
                rgba(0, 0, 81, 0.2) 100%);
            z-index: -1;
            border-radius: 25px;
        }
        
        .skills-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 20px;
            max-height: 500px;
            overflow-y: auto;
            padding: 15px;
        }
        
        .skill-item {
            padding: 20px;
            background: rgba(255, 255, 255, 0.15);
            border-radius: 20px;
            border-left: 8px solid var(--accent);
            transition: all 0.4s ease;
            cursor: pointer;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .skill-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(255, 255, 255, 0.1) 0%, 
                transparent 50%, 
                rgba(255, 255, 255, 0.1) 100%);
            z-index: -1;
        }
        
        .skill-item:hover {
            transform: translateY(-5px) scale(1.03);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.4);
            background: rgba(255, 255, 255, 0.2);
        }
        
        .skill-name {
            font-weight: bold;
            margin-bottom: 10px;
            color: var(--secondary);
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .skill-description {
            font-size: 1.05rem;
            opacity: 0.9;
            line-height: 1.5;
        }
        
        .player-setup {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            padding: 25px;
        }
        
        .setup-form {
            background: rgba(255, 255, 255, 0.98);
            padding: 50px;
            border-radius: 30px;
            width: 100%;
            max-width: 800px;
            text-align: center;
            color: #333;
            box-shadow: 
                0 30px 80px rgba(0, 0, 0, 0.6),
                0 0 150px rgba(155, 39, 176, 0.5);
            border: 4px solid rgba(255, 111, 0, 0.4);
            animation: formAppear 1s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }
        
        .setup-form::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(255, 111, 0, 0.1) 0%, 
                transparent 50%, 
                rgba(155, 39, 176, 0.1) 100%);
            z-index: -1;
        }
        
        @keyframes formAppear {
            0% {
                opacity: 0;
                transform: scale(0.7) translateY(60px);
            }
            100% {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }
        
        .setup-title {
            font-size: 2.5rem;
            margin-bottom: 30px;
            color: var(--primary);
            text-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
            background: linear-gradient(45deg, #4A148C, #7C4DFF, #FF6F00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 900;
        }
        
        .setup-input {
            width: 100%;
            padding: 20px;
            margin-bottom: 30px;
            border: 3px solid rgba(74, 20, 140, 0.3);
            border-radius: 15px;
            font-size: 1.3rem;
            transition: all 0.4s;
            background: rgba(255, 255, 255, 0.9);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
        }
        
        .setup-input:focus {
            outline: none;
            border-color: var(--secondary);
            box-shadow: 0 0 0 4px rgba(255, 111, 0, 0.3);
            transform: scale(1.02);
        }
        
        .avatar-selection {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .avatar-option {
            padding: 15px;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 3px solid transparent;
            background: rgba(255, 255, 255, 0.1);
        }
        
        .avatar-option:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }
        
        .avatar-option.selected {
            border-color: var(--secondary);
            background: rgba(255, 111, 0, 0.1);
            transform: scale(1.05);
        }
        
        .avatar-image {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            margin: 0 auto 10px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
        }
        
        .avatar-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .avatar-name {
            font-weight: bold;
            font-size: 1.1rem;
        }
        
        .setup-button {
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            color: white;
            border: none;
            padding: 20px 50px;
            border-radius: 15px;
            font-size: 1.4rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.4s;
            box-shadow: 0 8px 25px rgba(255, 111, 0, 0.5);
            width: 100%;
            position: relative;
            overflow: hidden;
        }
        
        .setup-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(255, 111, 0, 0.7);
        }
        
        .setup-button:active {
            transform: translateY(2px);
            box-shadow: 0 5px 20px rgba(255, 111, 0, 0.5);
        }
        
        .game-over {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            padding: 25px;
        }
        
        .game-over-content {
            background: rgba(255, 255, 255, 0.98);
            padding: 50px;
            border-radius: 30px;
            width: 100%;
            max-width: 700px;
            text-align: center;
            color: #333;
            box-shadow: 
                0 30px 80px rgba(0, 0, 0, 0.6),
                0 0 150px rgba(213, 0, 0, 0.5);
            border: 4px solid rgba(213, 0, 0, 0.4);
            animation: gameOverAppear 1s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }
        
        .game-over-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, 
                rgba(213, 0, 0, 0.1) 0%, 
                transparent 50%, 
                rgba(244, 67, 54, 0.1) 100%);
            z-index: -1;
        }
        
        @keyframes gameOverAppear {
            0% {
                opacity: 0;
                transform: scale(0.7) translateY(60px);
            }
            100% {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }
        
        .game-over-title {
            font-size: 4rem;
            margin-bottom: 20px;
            color: var(--danger);
            text-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
            background: linear-gradient(45deg, #D50000, #FF4081, #FF6F00);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 900;
        }
        
        .final-score {
            font-size: 3.5rem;
            margin: 30px 0;
            color: var(--secondary);
            text-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
            background: linear-gradient(45deg, #FF6F00, #FFCA28, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 900;
        }
        
        .restart-button {
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            color: white;
            border: none;
            padding: 20px 50px;
            border-radius: 15px;
            font-size: 1.5rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.4s;
            box-shadow: 0 8px 25px rgba(255, 111, 0, 0.5);
            width: 100%;
            margin-top: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .restart-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(255, 111, 0, 0.7);
        }
        
        .restart-button:active {
            transform: translateY(2px);
            box-shadow: 0 5px 20px rgba(255, 111, 0, 0.5);
        }
        
        .health-bonus {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(0, 200, 83, 0.9);
            color: white;
            padding: 20px 40px;
            border-radius: 15px;
            font-size: 2rem;
            font-weight: bold;
            z-index: 1500;
            box-shadow: 0 10px 30px rgba(0, 200, 83, 0.7);
            display: none;
            animation: healthBonusAppear 1.5s ease-out;
        }
        
        @keyframes healthBonusAppear {
            0% {
                opacity: 0;
                transform: translate(-50%, -50%) scale(0.5);
            }
            50% {
                opacity: 1;
                transform: translate(-50%, -50%) scale(1.2);
            }
            100% {
                opacity: 0;
                transform: translate(-50%, -50%) scale(1);
            }
        }
        
        .skill-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 1500;
            padding: 20px;
        }
        
        .skill-modal-content {
            background: rgba(255, 255, 255, 0.95);
            padding: 40px;
            border-radius: 25px;
            width: 100%;
            max-width: 900px;
            text-align: center;
            color: #333;
            box-shadow: 
                0 30px 80px rgba(0, 0, 0, 0.7),
                0 0 150px rgba(255, 215, 0, 0.5);
            border: 4px solid rgba(255, 215, 0, 0.4);
            animation: modalAppear 0.8s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        @keyframes modalAppear {
            0% {
                opacity: 0;
                transform: scale(0.8) translateY(50px);
            }
            100% {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }
        
        .skill-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .skill-option {
            padding: 25px;
            background: rgba(74, 20, 140, 0.1);
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.4s ease;
            border: 3px solid transparent;
            text-align: left;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }
        
        .skill-option:hover {
            background: rgba(74, 20, 140, 0.2);
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.25);
        }
        
        .skill-option.selected {
            background: rgba(74, 20, 140, 0.3);
            border-color: var(--accent);
            transform: scale(1.05);
            box-shadow: 
                0 15px 35px rgba(0, 0, 0, 0.3),
                0 0 30px rgba(0, 200, 83, 0.3);
        }
        
        /* Responsive design */
        @media (max-width: 768px) {
            .game-content {
                padding: 20px;
            }
            
            .stats {
                grid-template-columns: 1fr;
                gap: 15px;
                padding: 20px;
            }
            
            .score-container {
                text-align: center;
            }
            
            .player-info {
                justify-content: center;
            }
            
            .scene {
                padding: 20px;
            }
            
            .question {
                font-size: 1.5rem;
                padding: 20px;
            }
            
            .setup-form, .game-over-content {
                padding: 30px;
            }
            
            .setup-title, .game-over-title {
                font-size: 2rem;
            }
            
            .final-score {
                font-size: 2.5rem;
            }
            
            .avatar-selection {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        /* Scrollbar styling */
        ::-webkit-scrollbar {
            width: 12px;
        }
        
        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(135deg, var(--accent), var(--cosmic));
        }
    </style>
</head>
<body>
    <!-- Background elements -->
    <div class="universe-background"></div>
    <div class="stars" id="stars"></div>
    <div class="cosmic-orbs" id="cosmic-orbs"></div>
    
    <!-- Game container -->
    <div class="game-container">
        <div class="cosmic-border"></div>
        
        <!-- Header -->
        <div class="header">
            <h1 class="title">VŨ TRỤ TRI THỨC</h1>
            <p class="subtitle">Chinh phục vũ trụ qua những câu hỏi đầy thử thách</p>
        </div>
        
        <!-- Game content -->
        <div class="game-content">
            <!-- Player stats -->
            <div class="stats">
                <div class="player-info">
                    <div class="player-avatar" id="player-avatar">
                        <div id="avatar-content" style="width: 100%; height: 100%; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 2.5rem;"></div>
                    </div>
                    <div>
                        <div class="player-name" id="player-name">Người chơi</div>
                        <div class="player-level">
                            <span>Cấp độ: <span id="player-level">1</span></span>
                            <div class="level-bar">
                                <div class="level-progress" id="level-progress" style="width: 0%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="hearts" id="hearts">
                    <!-- Hearts will be generated by JavaScript -->
                </div>
                
                <div class="score-container">
                    <div>Điểm số</div>
                    <div class="score" id="score">0</div>
                </div>
            </div>
            
            <!-- Scene -->
            <div class="scene">
                <h2 class="scene-title" id="scene-title">Chào mừng đến với Vũ Trụ Tri Thức</h2>
                <p class="scene-description" id="scene-description">
                    Bạn đang ở trung tâm của vũ trụ tri thức. Hãy trả lời các câu hỏi để khám phá các hành tinh và thu thập điểm số. Cẩn thận với những câu trả lời sai - bạn sẽ mất mạng!
                </p>
                
                <!-- Question -->
                <div class="question" id="question">
                    Chào mừng! Hãy bắt đầu cuộc hành trình của bạn.
                </div>
                
                <!-- Input -->
                <div class="input-container">
                    <input type="text" id="answer-input" placeholder="Nhập câu trả lời của bạn...">
                    <button id="submit-button">Trả lời</button>
                </div>
                
                <!-- Feedback -->
                <div class="feedback" id="feedback"></div>
                
                <!-- Hint -->
                <div class="hint" id="hint"></div>
                
                <!-- Skill Effect -->
                <div class="skill-effect" id="skill-effect"></div>
                
                <!-- Progress -->
                <div class="progress-container">
                    <div class="progress-bar" id="progress-bar"></div>
                </div>
                <div class="stage-indicator">
                    Câu hỏi: <span id="current-question">0</span> | 
                    Tiến trình kỹ năng: <span id="skill-progress">0</span>/5
                </div>
                
                <!-- Active skill -->
                <div class="active-skill" id="active-skill">
                    <h3>Kỹ năng đặc biệt đang kích hoạt!</h3>
                    <p id="skill-description">Bạn có thể sử dụng kỹ năng này để vượt qua thử thách.</p>
                    <button class="skill-button" id="use-skill-button">Sử dụng kỹ năng</button>
                </div>
            </div>
            
            <!-- Skills -->
            <div class="skills-container">
                <h2 class="scene-title">Kỹ năng của bạn</h2>
                <div class="skills-list" id="skills-list">
                    <!-- Skills will be generated by JavaScript -->
                </div>
            </div>
        </div>
    </div>
    
    <!-- Player setup -->
    <div class="player-setup" id="player-setup">
        <div class="setup-form">
            <h2 class="setup-title">Tạo nhân vật</h2>
            <input type="text" class="setup-input" id="player-name-input" placeholder="Nhập tên người chơi" maxlength="20">
            
            <h3 style="margin: 20px 0; color: #4A148C;">Chọn Avatar của bạn</h3>
            <div class="avatar-selection" id="avatar-selection">
                <!-- Avatars will be generated by JavaScript -->
            </div>
            
            <button class="setup-button" id="start-game-button">Bắt đầu hành trình</button>
        </div>
    </div>
    
    <!-- Game Over screen -->
    <div class="game-over" id="game-over">
        <div class="game-over-content">
            <h2 class="game-over-title">GAME OVER</h2>
            <p>Bạn đã hết mạng sống!</p>
            <div class="final-score" id="final-score">0</div>
            <p>Hãy thử lại để đạt điểm cao hơn!</p>
            <button class="restart-button" id="restart-button">Chơi lại</button>
        </div>
    </div>
    
    <!-- Health bonus notification -->
    <div class="health-bonus" id="health-bonus">+1 Máu!</div>
    
    <!-- Skill selection modal -->
    <div class="skill-modal" id="skill-modal">
        <div class="skill-modal-content">
            <h2 id="skill-modal-title" style="font-size: 2.5rem; margin-bottom: 20px; background: linear-gradient(45deg, #FF6F00, #FFCA28, #FFD700); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">CHỌN KỸ NĂNG</h2>
            <p style="font-size: 1.3rem; margin-bottom: 30px; color: #666;">Bạn đã hoàn thành 5 câu hỏi! Hãy chọn 1 trong 3 kỹ năng ngẫu nhiên:</p>
            <div class="skill-options" id="skill-options">
                <!-- Skills will be added by JavaScript -->
            </div>
            <button id="confirm-skill" style="font-size: 1.4rem; padding: 20px 50px; margin-top: 30px;">XÁC NHẬN CHỌN KỸ NĂNG</button>
        </div>
    </div>
    
    <script>
        // Game state
        const gameState = {
            playerName: 'Người chơi',
            playerAvatar: null,
            score: 0,
            level: 1,
            hearts: 3,
            maxHearts: 3,
            currentQuestion: 0,
            correctAnswers: 0,
            consecutiveCorrect: 0,
            questionsSinceLastSkill: 0,
            currentQuestionData: null,
            questions: [
                {
                    question: "Hành tinh nào lớn nhất trong hệ Mặt Trời?",
                    answer: "sao mộc",
                    hint: "Hành tinh này có một cơn bão lớn gọi là Vết Đỏ Lớn."
                },
                {
                    question: "Nguyên tố nào phổ biến nhất trong vũ trụ?",
                    answer: "hydro",
                    hint: "Đây là nguyên tố nhẹ nhất và là thành phần chính của các ngôi sao."
                },
                {
                    question: "Ai là người đầu tiên đặt chân lên Mặt Trời?",
                    answer: "không ai",
                    hint: "Mặt Trời là một ngôi sao có nhiệt độ rất cao, không thể tiếp cận."
                },
                {
                    question: "Trái Đất quay quanh trục của nó mất bao lâu?",
                    answer: "24 giờ",
                    hint: "Đây là khoảng thời gian chúng ta gọi là một ngày."
                },
                {
                    question: "Ngôi sao nào gần Trái Đất nhất?",
                    answer: "mặt trời",
                    hint: "Đây là ngôi sao ở trung tâm của hệ Mặt Trời."
                },
                {
                    question: "Thiên hà của chúng ta có tên là gì?",
                    answer: "ngân hà",
                    hint: "Tên này bắt nguồn từ hình dạng giống như một dòng sông sáng trên bầu trời."
                },
                {
                    question: "Vật chất tối là gì?",
                    answer: "vật chất không nhìn thấy",
                    hint: "Đây là một dạng vật chất giả định trong vũ trụ không phát ra hoặc hấp thụ ánh sáng."
                },
                {
                    question: "Hố đen là gì?",
                    answer: "vùng không thời gian",
                    hint: "Đây là một vùng trong không-thời gian có lực hấp dẫn mạnh đến mức không gì có thể thoát ra."
                },
                {
                    question: "Năm ánh sáng là gì?",
                    answer: "khoảng cách ánh sáng",
                    hint: "Đây là đơn vị đo khoảng cách trong thiên văn học, tương đương với quãng đường ánh sáng đi trong một năm."
                },
                {
                    question: "Vụ nổ Big Bang là gì?",
                    answer: "vụ nổ khởi đầu",
                    hint: "Đây là lý thuyết khoa học mô tả sự khởi đầu của vũ trụ."
                }
            ],
            // 3 kỹ năng ban đầu
            initialSkills: [
                {
                    id: 1,
                    name: "Bảo vệ vũ trụ",
                    description: "Bảo vệ bạn khỏi mất mạng trong câu hỏi tiếp theo.",
                    type: "protection",
                    used: false
                },
                {
                    id: 2,
                    name: "Gợi ý thiên hà",
                    description: "Cung cấp gợi ý chi tiết cho câu hỏi hiện tại.",
                    type: "hint",
                    used: false
                },
                {
                    id: 3,
                    name: "Tự động trả lời",
                    description: "Tự động điền câu trả lời đúng cho câu hỏi hiện tại.",
                    type: "auto-answer",
                    used: false
                }
            ],
            // 500 kỹ năng tối thượng
            ultimateSkills: [],
            ownedSkills: [],
            activeSkill: null,
            skillProtectionActive: false
        };

        // Tạo 500 kỹ năng tối thượng
        function generateUltimateSkills() {
            const skillTypes = [
                "Toán Học", "Vật Lý", "Hóa Học", "Sinh Học", "Lịch Sử", 
                "Địa Lý", "Ngữ Văn", "Tiếng Anh", "Nghệ Thuật", "Công Nghệ",
                "Triết Học", "Tâm Lý", "Kinh Tế", "Chính Trị", "Môi Trường",
                "Y Học", "Thể Thao", "Âm Nhạc", "Hội Họa", "Kiến Trúc"
            ];
            
            const skillPrefixes = [
                "Bậc Thầy", "Chuyên Gia", "Thiên Tài", "Giáo Sư", "Tiến Sĩ",
                "Nhà Khoa Học", "Nhà Nghiên Cứu", "Nhà Phát Minh", "Nhà Thông Thái",
                "Bậc Thầy Vũ Trụ", "Chúa Tể", "Hoàng Đế", "Thần", "Siêu Nhân"
            ];
            
            const skillEffects = [
                "Tăng 50% điểm số trong 3 câu hỏi",
                "Tự động trả lời đúng 1 câu hỏi",
                "Hồi phục 2 mạng sống",
                "Nhân đôi điểm số trong 5 câu hỏi",
                "Bỏ qua 3 câu hỏi khó",
                "Tăng gấp 3 lần điểm số câu hỏi tiếp theo",
                "Mở khóa tất cả gợi ý",
                "Vô hiệu hóa mất mạng trong 5 câu hỏi",
                "Tự động hoàn thành 10% tiến trình",
                "Nhận ngay 1000 điểm"
            ];
            
            for (let i = 1; i <= 500; i++) {
                const type = skillTypes[Math.floor(Math.random() * skillTypes.length)];
                const prefix = skillPrefixes[Math.floor(Math.random() * skillPrefixes.length)];
                const effect = skillEffects[Math.floor(Math.random() * skillEffects.length)];
                
                gameState.ultimateSkills.push({
                    id: i,
                    name: `${prefix} ${type} ${i}`,
                    description: `Kỹ năng ${type} cấp độ ${i}. ${effect}`,
                    effect: effect,
                    type: type,
                    rarity: getRarity(i),
                    used: false
                });
            }
        }
        
        function getRarity(id) {
            if (id <= 100) return "common";
            if (id <= 200) return "rare";
            if (id <= 300) return "epic";
            if (id <= 400) return "legendary";
            return "divine";
        }

        // Avatars
        const avatars = [
            { id: 1, name: "Rồng Xanh", color: "#2196F3", emoji: "🐉" },
            { id: 2, name: "Rồng Đỏ", color: "#F44336", emoji: "🐲" },
            { id: 3, name: "Rồng Vàng", color: "#FFD700", emoji: "🐉" },
            { id: 4, name: "Rồng Tím", color: "#9C27B0", emoji: "🐲" },
            { id: 5, name: "Rồng Bạc", color: "#E0E0E0", emoji: "🐉" },
            { id: 6, name: "Rồng Đen", color: "#212121", emoji: "🐲" },
            { id: 7, name: "Phượng Hoàng", color: "#FF9800", emoji: "🦚" },
            { id: 8, name: "Kỳ Lân", color: "#4CAF50", emoji: "🦄" },
            { id: 9, name: "Bạch Tuộc", color: "#7B1FA2", emoji: "🐙" },
            { id: 10, name: "Sư Tử", color: "#FFC107", emoji: "🦁" }
        ];

        // DOM elements
        const playerSetup = document.getElementById('player-setup');
        const playerNameInput = document.getElementById('player-name-input');
        const avatarSelection = document.getElementById('avatar-selection');
        const startGameButton = document.getElementById('start-game-button');
        const playerNameElement = document.getElementById('player-name');
        const playerAvatarElement = document.getElementById('player-avatar');
        const avatarContentElement = document.getElementById('avatar-content');
        const playerLevelElement = document.getElementById('player-level');
        const levelProgressElement = document.getElementById('level-progress');
        const heartsElement = document.getElementById('hearts');
        const scoreElement = document.getElementById('score');
        const sceneTitleElement = document.getElementById('scene-title');
        const sceneDescriptionElement = document.getElementById('scene-description');
        const questionElement = document.getElementById('question');
        const answerInput = document.getElementById('answer-input');
        const submitButton = document.getElementById('submit-button');
        const feedbackElement = document.getElementById('feedback');
        const hintElement = document.getElementById('hint');
        const skillEffectElement = document.getElementById('skill-effect');
        const progressBarElement = document.getElementById('progress-bar');
        const currentQuestionElement = document.getElementById('current-question');
        const skillProgressElement = document.getElementById('skill-progress');
        const activeSkillElement = document.getElementById('active-skill');
        const skillDescriptionElement = document.getElementById('skill-description');
        const useSkillButton = document.getElementById('use-skill-button');
        const skillsListElement = document.getElementById('skills-list');
        const gameOverElement = document.getElementById('game-over');
        const finalScoreElement = document.getElementById('final-score');
        const restartButton = document.getElementById('restart-button');
        const healthBonusElement = document.getElementById('health-bonus');
        const skillModal = document.getElementById('skill-modal');
        const skillModalTitle = document.getElementById('skill-modal-title');
        const skillOptions = document.getElementById('skill-options');
        const confirmSkillButton = document.getElementById('confirm-skill');

        // Initialize game
        function initGame() {
            // Generate ultimate skills
            generateUltimateSkills();
            
            // Create stars
            createStars();
            
            // Create cosmic orbs
            createCosmicOrbs();
            
            // Initialize avatars
            renderAvatars();
            
            // Initialize hearts
            updateHearts();
            
            // Initialize skills
            renderSkills();
            
            // Set up event listeners
            startGameButton.addEventListener('click', startGame);
            submitButton.addEventListener('click', checkAnswer);
            answerInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    checkAnswer();
                }
            });
            useSkillButton.addEventListener('click', useActiveSkill);
            restartButton.addEventListener('click', restartGame);
            confirmSkillButton.addEventListener('click', confirmSkillSelection);
            
            // Show player setup
            playerSetup.style.display = 'flex';
        }

        // Create stars for background
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const starCount = 200;
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // Random position
                const left = Math.random() * 100;
                const top = Math.random() * 100;
                
                // Random size
                const size = Math.random() * 3;
                
                // Random animation delay
                const delay = Math.random() * 5;
                
                star.style.left = `${left}%`;
                star.style.top = `${top}%`;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                star.style.animationDelay = `${delay}s`;
                
                starsContainer.appendChild(star);
            }
        }

        // Create cosmic orbs for background
        function createCosmicOrbs() {
            const orbsContainer = document.getElementById('cosmic-orbs');
            const orbCount = 5;
            
            for (let i = 0; i < orbCount; i++) {
                const orb = document.createElement('div');
                orb.classList.add('cosmic-orb');
                
                // Random position
                const left = Math.random() * 100;
                const top = Math.random() * 100;
                
                // Random size
                const size = 100 + Math.random() * 200;
                
                // Random color
                const colors = [
                    'rgba(255, 111, 0, 0.6)',
                    'rgba(156, 39, 176, 0.6)',
                    'rgba(33, 150, 243, 0.6)',
                    'rgba(124, 77, 255, 0.6)',
                    'rgba(0, 229, 255, 0.6)'
                ];
                const color = colors[Math.floor(Math.random() * colors.length)];
                
                // Random animation duration
                const duration = 15 + Math.random() * 20;
                
                orb.style.left = `${left}%`;
                orb.style.top = `${top}%`;
                orb.style.width = `${size}px`;
                orb.style.height = `${size}px`;
                orb.style.background = color;
                orb.style.animationDuration = `${duration}s`;
                
                orbsContainer.appendChild(orb);
            }
        }

        // Render avatars
        function renderAvatars() {
            avatarSelection.innerHTML = '';
            
            avatars.forEach(avatar => {
                const avatarOption = document.createElement('div');
                avatarOption.classList.add('avatar-option');
                avatarOption.dataset.id = avatar.id;
                
                avatarOption.innerHTML = `
                    <div class="avatar-image" style="background: ${avatar.color}">
                        <span style="font-size: 2.5rem;">${avatar.emoji}</span>
                    </div>
                    <div class="avatar-name">${avatar.name}</div>
                `;
                
                avatarOption.addEventListener('click', () => {
                    document.querySelectorAll('.avatar-option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    avatarOption.classList.add('selected');
                    gameState.playerAvatar = avatar;
                });
                
                avatarSelection.appendChild(avatarOption);
            });
            
            // Select first avatar by default
            avatarSelection.children[0].classList.add('selected');
            gameState.playerAvatar = avatars[0];
        }

        // Start the game
        function startGame() {
            const name = playerNameInput.value.trim();
            if (name) {
                gameState.playerName = name;
                playerNameElement.textContent = name;
            }
            
            // Set avatar
            if (gameState.playerAvatar) {
                avatarContentElement.style.background = gameState.playerAvatar.color;
                avatarContentElement.innerHTML = gameState.playerAvatar.emoji;
            }
            
            playerSetup.style.display = 'none';
            
            // Initialize game state
            gameState.score = 0;
            gameState.level = 1;
            gameState.hearts = 3;
            gameState.currentQuestion = 0;
            gameState.correctAnswers = 0;
            gameState.consecutiveCorrect = 0;
            gameState.questionsSinceLastSkill = 0;
            gameState.skillProtectionActive = false;
            
            // Reset skills - start with initial skills
            gameState.initialSkills.forEach(skill => skill.used = false);
            gameState.ownedSkills = [...gameState.initialSkills];
            gameState.activeSkill = null;
            
            // Update UI
            updateScore();
            updateLevel();
            updateHearts();
            renderSkills();
            hideActiveSkill();
            
            // Load first question
            loadQuestion();
        }

        // Load a question
        function loadQuestion() {
            // Generate random question
            const randomIndex = Math.floor(Math.random() * gameState.questions.length);
            gameState.currentQuestionData = gameState.questions[randomIndex];
            
            // Update UI
            questionElement.textContent = gameState.currentQuestionData.question;
            currentQuestionElement.textContent = gameState.currentQuestion + 1;
            skillProgressElement.textContent = gameState.questionsSinceLastSkill;
            
            // Update progress bar
            const progress = (gameState.questionsSinceLastSkill % 5) * 20;
            progressBarElement.style.width = `${progress}%`;
            
            // Clear input and feedback
            answerInput.value = '';
            feedbackElement.style.display = 'none';
            hintElement.style.display = 'none';
            skillEffectElement.style.display = 'none';
            
            // Focus on input
            answerInput.focus();
            
            // Update scene based on progress
            updateScene();
        }

        // Update scene based on progress
        function updateScene() {
            const progress = gameState.questionsSinceLastSkill % 5;
            
            if (progress < 1) {
                sceneTitleElement.textContent = "Hành tinh Khởi đầu";
                sceneDescriptionElement.textContent = "Bạn đang ở hành tinh Khởi đầu. Hãy cẩn thận với những câu hỏi đầu tiên - chúng sẽ quyết định tốc độ phát triển của bạn!";
            } else if (progress < 2) {
                sceneTitleElement.textContent = "Thiên hà Tri thức";
                sceneDescriptionElement.textContent = "Bạn đã tiến vào Thiên hà Tri thức. Các câu hỏi ở đây sẽ thử thách hiểu biết của bạn về vũ trụ!";
            } else if (progress < 3) {
                sceneTitleElement.textContent = "Tinh vân Thử thách";
                sceneDescriptionElement.textContent = "Bạn đang ở Tinh vân Thử thách. Đây là nơi những câu hỏi khó nhất đang chờ đợi!";
            } else if (progress < 4) {
                sceneTitleElement.textContent = "Lỗ đen Vinh quang";
                sceneDescriptionElement.textContent = "Bạn đã đến gần Lỗ đen Vinh quang. Chỉ cần vượt qua những câu hỏi cuối cùng, bạn sẽ trở thành bậc thầy vũ trụ!";
            } else {
                sceneTitleElement.textContent = "Trung tâm Vũ trụ";
                sceneDescriptionElement.textContent = "Bạn đã đến Trung tâm Vũ trụ! Hoàn thành câu hỏi này để nhận kỹ năng tối thượng!";
            }
        }

        // Check the answer
        function checkAnswer() {
            const userAnswer = answerInput.value.trim().toLowerCase();
            
            if (!userAnswer) {
                return;
            }
            
            const isCorrect = userAnswer === gameState.currentQuestionData.answer;
            
            if (isCorrect) {
                handleCorrectAnswer();
            } else {
                handleIncorrectAnswer();
            }
            
            // Show feedback
            showFeedback(isCorrect);
            
            // Move to next question after a delay
            setTimeout(() => {
                gameState.currentQuestion++;
                gameState.questionsSinceLastSkill++;
                
                // Check if player has answered 5 questions since last skill
                if (gameState.questionsSinceLastSkill >= 5) {
                    showSkillSelection();
                    gameState.questionsSinceLastSkill = 0;
                }
                
                loadQuestion();
            }, 2000);
        }

        // Handle correct answer
        function handleCorrectAnswer() {
            // Increase score
            gameState.score += 100;
            gameState.correctAnswers++;
            gameState.consecutiveCorrect++;
            
            // Check for health bonus (every 5 consecutive correct answers)
            if (gameState.consecutiveCorrect % 5 === 0 && gameState.hearts < gameState.maxHearts) {
                gameState.hearts++;
                showHealthBonus();
                updateHearts();
            }
            
            // Update UI
            updateScore();
            
            // Check for level up
            if (gameState.correctAnswers % 3 === 0) {
                gameState.level++;
                updateLevel();
            }
        }

        // Handle incorrect answer
        function handleIncorrectAnswer() {
            // Check if protection skill is active
            if (gameState.skillProtectionActive) {
                gameState.skillProtectionActive = false;
                showSkillEffect("Kỹ năng Bảo vệ Vũ trụ đã bảo vệ bạn khỏi mất mạng!");
                return;
            }
            
            // Decrease hearts
            gameState.hearts--;
            gameState.consecutiveCorrect = 0;
            
            // Update UI
            updateHearts();
            
            // Check for game over
            if (gameState.hearts <= 0) {
                setTimeout(() => {
                    endGame(false);
                }, 1500);
            }
        }

        // Show feedback
        function showFeedback(isCorrect) {
            if (isCorrect) {
                feedbackElement.textContent = "Chính xác! Bạn đã tiến thêm một bước trong vũ trụ tri thức.";
                feedbackElement.className = "feedback correct";
            } else {
                feedbackElement.textContent = `Sai rồi! Đáp án đúng là: ${gameState.currentQuestionData.answer}`;
                feedbackElement.className = "feedback incorrect";
            }
            
            feedbackElement.style.display = 'block';
        }

        // Show skill effect
        function showSkillEffect(message) {
            skillEffectElement.textContent = message;
            skillEffectElement.style.display = 'block';
            
            // Hide after 3 seconds
            setTimeout(() => {
                skillEffectElement.style.display = 'none';
            }, 3000);
        }

        // Update score display
        function updateScore() {
            scoreElement.textContent = gameState.score;
        }

        // Update level display
        function updateLevel() {
            playerLevelElement.textContent = gameState.level;
            
            // Update level progress
            const progress = (gameState.correctAnswers % 3) * 33.33;
            levelProgressElement.style.width = `${progress}%`;
        }

        // Update hearts display
        function updateHearts() {
            heartsElement.innerHTML = '';
            
            for (let i = 0; i < gameState.maxHearts; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                
                if (i < gameState.hearts) {
                    heart.textContent = '❤️';
                    heart.style.animationDelay = `${i * 0.3}s`;
                } else {
                    heart.textContent = '🖤';
                    heart.style.animation = 'none';
                }
                
                heartsElement.appendChild(heart);
            }
        }

        // Render skills
        function renderSkills() {
            skillsListElement.innerHTML = '';
            
            if (gameState.ownedSkills.length === 0) {
                skillsListElement.innerHTML = '<div class="skill-item">Chưa có kỹ năng nào</div>';
            } else {
                gameState.ownedSkills.forEach(skill => {
                    const skillElement = document.createElement('div');
                    skillElement.classList.add('skill-item');
                    
                    if (skill.used) {
                        skillElement.style.opacity = '0.5';
                    }
                    
                    skillElement.innerHTML = `
                        <div class="skill-name">
                            <span>${skill.name}</span>
                        </div>
                        <div class="skill-description">${skill.description}</div>
                    `;
                    
                    skillElement.addEventListener('click', () => {
                        if (!skill.used) {
                            activateSkill(skill);
                        }
                    });
                    
                    skillsListElement.appendChild(skillElement);
                });
            }
        }

        // Activate a skill
        function activateSkill(skill) {
            gameState.activeSkill = skill;
            
            // Update UI
            skillDescriptionElement.textContent = skill.description;
            activeSkillElement.style.display = 'block';
            
            // Scroll to active skill
            activeSkillElement.scrollIntoView({ behavior: 'smooth' });
        }

        // Use active skill
        function useActiveSkill() {
            if (!gameState.activeSkill) return;
            
            const skill = gameState.activeSkill;
            
            // Mark skill as used
            skill.used = true;
            
            // Apply skill effect based on skill type
            switch(skill.type) {
                case "protection":
                    gameState.skillProtectionActive = true;
                    showSkillEffect("Kỹ năng Bảo vệ Vũ trụ đã được kích hoạt! Bạn sẽ không mất mạng ở câu hỏi tiếp theo.");
                    break;
                    
                case "hint":
                    hintElement.textContent = "Gợi ý: " + gameState.currentQuestionData.hint;
                    hintElement.style.display = 'block';
                    showSkillEffect("Kỹ năng Gợi ý Thiên hà đã được kích hoạt! Hãy xem gợi ý bên trên.");
                    break;
                    
                case "auto-answer":
                    answerInput.value = gameState.currentQuestionData.answer;
                    showSkillEffect("Kỹ năng Tự động Trả lời đã được kích hoạt! Câu trả lời đã được điền sẵn.");
                    break;
                    
                default:
                    // For ultimate skills, show a generic effect
                    showSkillEffect(`Kỹ năng ${skill.name} đã được kích hoạt! ${skill.effect}`);
                    break;
            }
            
            // Hide active skill
            hideActiveSkill();
            
            // Update skills list
            renderSkills();
        }

        // Hide active skill
        function hideActiveSkill() {
            activeSkillElement.style.display = 'none';
            gameState.activeSkill = null;
        }

        // Show skill selection modal
        function showSkillSelection() {
            // Select 3 random skills from ultimate skills
            const randomSkills = [];
            const availableSkills = [...gameState.ultimateSkills];
            
            for (let i = 0; i < 3; i++) {
                if (availableSkills.length === 0) break;
                const randomIndex = Math.floor(Math.random() * availableSkills.length);
                randomSkills.push(availableSkills[randomIndex]);
                availableSkills.splice(randomIndex, 1);
            }
            
            // Render skill options
            skillOptions.innerHTML = '';
            
            randomSkills.forEach(skill => {
                const skillOption = document.createElement('div');
                skillOption.className = 'skill-option';
                skillOption.dataset.id = skill.id;
                
                skillOption.innerHTML = `
                    <div class="skill-name">
                        ${skill.name}
                    </div>
                    <div class="skill-description">
                        ${skill.description}
                    </div>
                    <div style="margin-top: 10px; font-size: 0.9rem; color: #666;">
                        <strong>Hiệu ứng:</strong> ${skill.effect}
                    </div>
                `;
                
                skillOption.addEventListener('click', function() {
                    document.querySelectorAll('.skill-option').forEach(opt => {
                        opt.classList.remove('selected');
                    });
                    this.classList.add('selected');
                });
                
                skillOptions.appendChild(skillOption);
            });
            
            // Show modal
            skillModal.style.display = 'flex';
        }

        // Confirm skill selection
        function confirmSkillSelection() {
            const selectedOption = document.querySelector('.skill-option.selected');
            
            if (!selectedOption) {
                alert('Hãy chọn một kỹ năng!');
                return;
            }
            
            const skillId = parseInt(selectedOption.dataset.id);
            const selectedSkill = gameState.ultimateSkills.find(skill => skill.id === skillId);
            
            if (selectedSkill) {
                gameState.ownedSkills.push(selectedSkill);
                renderSkills();
                
                // Hide modal
                skillModal.style.display = 'none';
                
                // Show notification
                showSkillEffect(`Bạn đã nhận được kỹ năng: ${selectedSkill.name}!`);
            }
        }

        // Show health bonus notification
        function showHealthBonus() {
            healthBonusElement.style.display = 'block';
            
            setTimeout(() => {
                healthBonusElement.style.display = 'none';
            }, 1500);
        }

        // End the game
        function endGame(isCompleted) {
            if (isCompleted) {
                // Game completed successfully
                alert(`Chúc mừng! Bạn đã hoàn thành tất cả câu hỏi với số điểm ${gameState.score}!`);
                restartGame();
            } else {
                // Game over
                finalScoreElement.textContent = gameState.score;
                gameOverElement.style.display = 'flex';
            }
        }

        // Restart the game
        function restartGame() {
            gameOverElement.style.display = 'none';
            startGame();
        }

        // Initialize the game when the page loads
        window.addEventListener('load', initGame);
    </script>
</body>
</html>
