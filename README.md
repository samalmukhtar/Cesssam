<!DOCTYPE html>
<html dir="rtl" lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>النادي العربي للشطرنج - النسخة العصرية</title>
    <!-- إضافة الخطوط العربية من Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700&family=Cairo:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #0a0a0a;
            --secondary-color: #1a1a1a;
            --accent-color: #00ff00;
            --text-color: #00ff00;
            --hover-color: #00cc00;
            --font-primary: 'Cairo', 'Tajawal', sans-serif;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: var(--font-primary);
        }

        /* Theme Switcher */
        .theme-switch {
            position: fixed;
            top: 20px;
            left: 20px;
            z-index: 1000;
            display: flex;
            gap: 10px;
            background: var(--secondary-color);
            padding: 10px;
            border-radius: 8px;
            border: 1px solid var(--accent-color);
        }

        .theme-btn {
            padding: 8px 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-family: var(--font-primary);
            transition: all 0.3s ease;
        }

        .theme-matrix {
            background: #000;
            color: #0f0;
            border: 1px solid #0f0;
        }

        .theme-modern {
            background: #2a2a2a;
            color: #fff;
            border: 1px solid #4a4a4a;
        }

        .theme-light {
            background: #fff;
            color: #000;
            border: 1px solid #ddd;
        }

        body {
            background-color: var(--primary-color);
            color: var(--text-color);
            position: relative;
            overflow-x: hidden;
            font-family: var(--font-primary);
            line-height: 1.6;
        }

        /* Matrix Rain Effect */
        #matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            opacity: 0.1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        header {
            background-color: var(--secondary-color);
            color: var(--text-color);
            padding: 2rem;
            text-align: center;
            border-radius: 15px;
            margin-bottom: 2rem;
            border: 1px solid var(--accent-color);
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);
        }

        header h1 {
            font-size: 2.5em;
            margin-bottom: 0.5em;
            font-weight: 700;
            text-shadow: 0 0 10px var(--accent-color);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 2rem;
        }

        .feature-card {
            background: var(--secondary-color);
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.1);
            transition: all 0.4s ease;
            border: 1px solid var(--accent-color);
        }

        .feature-card:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 0 25px rgba(0, 255, 0, 0.2);
        }

        .feature-card h3 {
            font-size: 1.5em;
            margin-bottom: 1em;
            color: var(--accent-color);
            font-weight: 700;
        }

        .feature-card a {
            color: var(--text-color);
            text-decoration: none;
            transition: all 0.3s ease;
            display: block;
            padding: 10px;
            border-radius: 8px;
            margin: 5px 0;
        }

        .feature-card a:hover {
            background: rgba(0, 255, 0, 0.1);
            transform: translateX(10px);
            color: var(--hover-color);
            text-shadow: 0 0 5px var(--hover-color);
        }

        .feature-card ul {
            list-style: none;
            padding: 0;
        }

        .feature-card li {
            margin: 10px 0;
            transition: all 0.3s ease;
        }

        .chessboard {
            width: 100%;
            max-width: 500px;
            margin: 2rem auto;
            display: grid;
            grid-template-columns: repeat(8, 1fr);
            border: 3px solid var(--accent-color);
            box-shadow: 0 0 30px rgba(0, 255, 0, 0.2);
            border-radius: 8px;
            overflow: hidden;
        }

        .square {
            aspect-ratio: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2em;
            color: var(--accent-color);
            text-shadow: 0 0 5px var(--accent-color);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .square:hover {
            background-color: rgba(0, 255, 0, 0.2);
            transform: scale(1.1);
        }

        .white { background-color: #1a1a1a; }
        .black { background-color: #000000; }

        .btn {
            background-color: var(--secondary-color);
            color: var(--text-color);
            padding: 12px 24px;
            border: 2px solid var(--accent-color);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            font-weight: bold;
            text-align: center;
            margin: 5px;
        }

        .btn:hover {
            background-color: var(--accent-color);
            color: var(--primary-color);
            box-shadow: 0 0 15px var(--accent-color);
            transform: translateY(-2px);
        }

        .chess-resources {
            background: var(--secondary-color);
            padding: 30px;
            border-radius: 15px;
            margin-top: 2rem;
            border: 1px solid var(--accent-color);
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.2);
        }

        .chess-resources h2 {
            font-size: 2em;
            margin-bottom: 1em;
            color: var(--accent-color);
            text-align: center;
        }

        .chess-resources ul {
            list-style-type: none;
            padding: 0;
            display: grid;
            gap: 15px;
        }

        .chess-resources li {
            padding: 15px;
            background: var(--primary-color);
            border-radius: 8px;
            border: 1px solid var(--accent-color);
            transition: all 0.3s ease;
        }

        .chess-resources li:hover {
            transform: translateX(10px);
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.2);
        }

        .chess-resources a {
            color: var(--text-color);
            text-decoration: none;
            transition: all 0.3s ease;
            display: block;
            font-weight: bold;
        }

        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            padding: 15px 25px;
            background: var(--accent-color);
            color: var(--primary-color);
            border-radius: 8px;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s ease;
            z-index: 1000;
        }

        .notification.show {
            transform: translateY(0);
            opacity: 1;
        }

    </style>
</head>
<body>
    <div class="theme-switch">
        <button class="theme-btn theme-matrix" onclick="setTheme('matrix')">ماتريكس</button>
        <button class="theme-btn theme-modern" onclick="setTheme('modern')">عصري</button>
        <button class="theme-btn theme-light" onclick="setTheme('light')">فاتح</button>
    </div>
    <div id="notification" class="notification"></div>
    <canvas id="matrix-bg"></canvas>
    <div class="container">
        <header>
            <h1>النادي العربي للشطرنج</h1>
            <p>مرحباً بكم في منصة تعلم وممارسة الشطرنج</p>
        </header>

        <div class="features-grid">
            <div class="feature-card">
                <h3>تعلم الشطرنج</h3>
                <p>دروس تفاعلية للمبتدئين والمتقدمين</p>
                <ul>
                    <li><a href="https://www.youtube.com/playlist?list=PLLALQuK1NDriznhy4WQzRJQiPqNRZZWHp" target="_blank">📚 تعلم القواعد الأساسية</a></li>
                    <li><a href="https://lichess.org/learn#/" target="_blank">🎯 استراتيجيات متقدمة</a></li>
                    <li><a href="https://lichess.org/training" target="_blank">⚡ تمارين تكتيكية</a></li>
                    <li><a href="https://www.chess.com/ar/lessons" target="_blank">📝 دروس تفاعلية</a></li>
                    <li><a href="https://www.chess.com/ar/puzzles" target="_blank">🧩 ألغاز شطرنج</a></li>
                </ul>
            </div>

            <div class="feature-card">
                <h3>تحديات يومية</h3>
                <p>حل المشكلات وتحسين مستواك</p>
                <ul>
                    <li><a href="https://lichess.org/training/daily" target="_blank">🎯 مسائل شطرنج يومية</a></li>
                    <li><a href="https://lichess.org/tournament" target="_blank">🏆 مباريات مع اللاعبين</a></li>
                    <li><a href="https://lichess.org/tournament/weekly" target="_blank">🌟 بطولات أسبوعية</a></li>
                    <li><a href="https://www.chess.com/ar/play/online" target="_blank">🎮 العب مباشرة</a></li>
                    <li><a href="https://www.chess.com/ar/tournament" target="_blank">🏅 شارك في البطولات</a></li>
                </ul>
            </div>

            <div class="feature-card">
                <h3>مجتمع النادي</h3>
                <p>تواصل مع لاعبين آخرين</p>
                <ul>
                    <li><a href="https://lichess.org/forum" target="_blank">💬 منتدى للنقاش</a></li>
                    <li><a href="https://www.chess.com/ar/forum" target="_blank">👥 مشاركة الخبرات</a></li>
                    <li><a href="https://lichess.org/team" target="_blank">🤝 تنظيم البطولات</a></li>
                    <li><a href="https://www.chess.com/ar/clubs" target="_blank">🌐 انضم للنوادي</a></li>
                    <li><a href="https://www.chess.com/ar/coaches" target="_blank">👨‍🏫 تواصل مع المدربين</a></li>
                </ul>
            </div>
        </div>

        <div class="chessboard">
            <script>
                // إنشاء رقعة الشطرنج
                function createBoard() {
                    const board = document.querySelector('.chessboard');
                    const pieces = {
                        0: '♜♞♝♛♚♝♞♜',
                        1: '♟♟♟♟♟♟♟♟',
                        6: '♙♙♙♙♙♙♙♙',
                        7: '♖♘♗♕♔♗♘♖'
                    };
                    
                    for (let i = 0; i < 8; i++) {
                        for (let j = 0; j < 8; j++) {
                            const square = document.createElement('div');
                            square.className = `square ${(i + j) % 2 ? 'black' : 'white'}`;
                            
                            if (pieces[i]) {
                                square.textContent = pieces[i][j];
                            }
                            
                            square.addEventListener('click', () => showMoveHint(i, j));
                            board.appendChild(square);
                        }
                    }
                }

                // إظهار تلميحات الحركة
                function showMoveHint(row, col) {
                    showNotification('انقر على القطعة لمعرفة حركاتها المتاحة');
                }

                // إظهار الإشعارات
                function showNotification(message) {
                    const notification = document.getElementById('notification');
                    notification.textContent =
