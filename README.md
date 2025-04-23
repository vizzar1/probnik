# probnik
ccf
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NIGHT CITY STEAM</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --neon-red: #FF003C;
            --cyber-yellow: #FFD300;
            --neon-blue: #00FFFF;
            --dark-bg: #0A0A12;
        }

        body {
            margin: 0;
            background: var(--dark-bg);
            color: var(--neon-blue);
            font-family: 'Orbitron', sans-serif;
            overflow-x: hidden;
            position: relative;
        }

        /* Анимация падающих долларов */
        .dollar-rain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            pointer-events: none;
            z-index: 0;
        }

        .dollar {
            position: absolute;
            color: var(--cyber-yellow);
            font-size: 24px;
            opacity: 0.7;
            animation: fall linear infinite;
            text-shadow: 0 0 10px var(--cyber-yellow);
        }

        @keyframes fall {
            0% { transform: translateY(-100vh) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }

        /* Основной контент */
        .container {
            position: relative;
            z-index: 1;
            max-width: 1200px;
            margin: 0 auto;
            padding: 30px;
        }

        /* Заголовок */
        .cyber-header {
            text-align: center;
            padding: 100px 0;
            border-bottom: 3px solid var(--neon-red);
            margin-bottom: 50px;
            position: relative;
        }

        .cyber-header h1 {
            font-size: 4em;
            text-transform: uppercase;
            animation: glitch 1s infinite;
        }

        @keyframes glitch {
            0% { text-shadow: 3px 0 0 var(--neon-red), -3px 0 0 var(--neon-blue); }
            100% { text-shadow: -3px 0 0 var(--neon-red), 3px 0 0 var(--neon-blue); }
        }

        /* Калькулятор */
        .calculator {
            background: rgba(0, 0, 0, 0.7);
            border: 3px solid var(--neon-blue);
            padding: 40px;
            margin: 50px 0;
            position: relative;
            transform: translateY(50px);
            opacity: 0;
            animation: slideUp 1s forwards;
        }

        @keyframes slideUp {
            to { transform: translateY(0); opacity: 1; }
        }

        .cyber-input {
            width: 100%;
            padding: 20px;
            margin: 30px 0;
            background: transparent;
            border: 2px solid var(--neon-red);
            color: var(--neon-blue);
            font-size: 2em;
            text-align: center;
            transition: 0.3s;
        }

        .cyber-input:focus {
            outline: none;
            box-shadow: 0 0 30px var(--neon-red);
        }

        .result {
            font-size: 2.5em;
            text-align: center;
            margin: 30px 0;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Преимущества */
        .advantages {
            display: grid;
            gap: 30px;
            margin: 100px 0;
            opacity: 0;
            transform: translateY(50px);
            animation: slideUp 1s 0.5s forwards;
        }

        .advantage-card {
            background: rgba(255, 0, 60, 0.1);
            padding: 30px;
            border-left: 5px solid var(--neon-blue);
            transition: 0.3s;
        }

        .advantage-card:hover {
            transform: translateX(20px);
        }

        /* Футер */
        .cyber-footer {
            background: rgba(0, 0, 0, 0.9);
            padding: 50px;
            text-align: center;
            border-top: 3px solid var(--neon-red);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 30px 0;
        }

        .social-link {
            color: var(--neon-blue);
            text-decoration: none;
            font-size: 1.2em;
            transition: 0.3s;
        }

        .social-link:hover {
            color: var(--neon-red);
        }

        /* Иконка телеграмма */
        .telegram-fixed {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--neon-red);
            color: black;
            padding: 15px 25px;
            border-radius: 30px;
            text-decoration: none;
            animation: pulse 2s infinite;
        }
    </style>
</head>
<body>
    <div class="dollar-rain" id="dollarRain"></div>

    <div class="container">
        <header class="cyber-header">
            <h1>STEAM POPOLNENIE 2077</h1>
            <p>КОМИССИЯ ВСЕГО 7%</p>
        </header>

        <div class="calculator">
            <input type="number" class="cyber-input" id="amount" placeholder="ВВЕДИТЕ СУММУ" min="50">
            <div class="result" id="result">
                <div>К ОПЛАТЕ: <span id="total">0</span>₽</div>
                <div style="font-size: 0.6em; color: var(--neon-red);">Включая комиссию 7%</div>
            </div>
            <button class="cyber-input" style="background: var(--neon-red); color: black; cursor: pointer;">
                ПОДТВЕРДИТЬ ТРАНЗАКЦИЮ
            </button>
        </div>

        <div class="advantages">
            <div class="advantage-card">
                <h2>ПОЧЕМУ МЫ?</h2>
                <p>▄︻̷̿┻̿═━一 ЛУЧШИЕ УСЛОВИЯ В НОЧНОМ ГОРОДЕ</p>
            </div>
            
            <div class="advantage-card">
                <h3>⬇️ САМАЯ НИЗКАЯ КОМИССИЯ</h3>
                <p>Всего 7% против 15% у конкурентов</p>
            </div>

            <div class="advantage-card">
                <h3>🔒 ЗАЩИЩЕННЫЕ ТРАНЗАКЦИИ</h3>
                <p>Используем криптографию уровня Arasaka</p>
            </div>
        </div>

        <div class="cyber-footer">
            <div class="social-links">
                <a href="https://t.me/your_channel" class="social-link" target="_blank">
                    <i class="fab fa-telegram"></i> ТЕХПОДДЕРЖКА
                </a>
                <a href="#vk-group" class="social-link">
                    <i class="fab fa-vk"></i> НАША ГРУППА
                </a>
            </div>
            <p>⚠️ ВСЕ ОПЕРАЦИИ ЗАЩИЩЕНЫ PROTON SECURITY SYSTEM ⚠️</p>
        </div>
    </div>

    <a href="https://t.me/your_channel" class="telegram-fixed" target="_blank">
        <i class="fab fa-telegram"></i> НАПИСАТЬ
    </a>

    <script>
        // Анимация падающих долларов
        function createDollar() {
            const dollar = document.createElement('div');
            dollar.className = 'dollar';
            dollar.style.left = Math.random() * 100 + '%';
            dollar.style.animationDuration = Math.random() * 3 + 2 + 's';
            dollar.textContent = '$';
            document.getElementById('dollarRain').appendChild(dollar);

            setTimeout(() => dollar.remove(), 5000);
        }
        setInterval(createDollar, 100);

        // Калькулятор комиссии
        const amountInput = document.getElementById('amount');
        const totalSpan = document.getElementById('total');

        amountInput.addEventListener('input', () => {
            const amount = parseFloat(amountInput.value) || 0;
            const total = amount * 1.07;
            totalSpan.textContent = total.toFixed(2);
        });

        // Плавный скролл
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Анимация при скролле
        window.addEventListener('scroll', () => {
            document.querySelectorAll('.advantages').forEach(el => {
                const rect = el.getBoundingClientRect();
                if(rect.top < window.innerHeight * 0.8) {
                    el.style.opacity = '1';
                    el.style.transform = 'translateY(0)';
                }
            });
        });
    </script>
</body>
</html>
