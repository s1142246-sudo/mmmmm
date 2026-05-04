<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>平台跳躍遊戲</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: #1a1a2e;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Arial', sans-serif;
            overflow: hidden;
        }
        #gameContainer {
            position: relative;
        }
        canvas {
            border: 3px solid #4a90d9;
            border-radius: 8px;
            box-shadow: 0 0 30px rgba(74, 144, 217, 0.4);
            background: linear-gradient(to bottom, #87CEEB 0%, #E0F6FF 100%);
        }
        #ui {
            position: absolute;
            top: 10px;
            left: 10px;
            color: #333;
            font-size: 18px;
            font-weight: bold;
        }
        #gameOver, #winScreen {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            display: none;
        }
        #gameOver h1, #winScreen h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }
        #gameOver h1 {
            color: #ff4444;
        }
        #winScreen h1 {
            color: #44ff44;
        }
        #gameOver p, #winScreen p {
            font-size: 24px;
            margin-bottom: 20px;
        }
        .btn {
            padding: 15px 40px;
            font-size: 18px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
        }
        #restartBtn {
            background: #ff6b6b;
            color: white;
        }
        #restartBtn:hover {
            background: #ff4444;
            transform: scale(1.1);
        }
        #startScreen {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            color: #333;
        }
        #startScreen h1 {
            font-size: 42px;
            color: #2d5a8a;
            margin-bottom: 15px;
        }
        #startScreen p {
            font-size: 18px;
            margin-bottom: 25px;
            color: #555;
        }
        #startBtn {
            background: #4a90d9;
            color: white;
        }
        #startBtn:hover {
            background: #2d5a8a;
            transform: scale(1.1);
        }
    </style>
</head>
<body>
    <div id="gameContainer">
        <canvas id="gameCanvas" width="800" height="500"></canvas>
        <div id="ui">❤️ <span id="lives">3</span> | 💎 <span id="coins">0</span> | 🏆 <span id="level">1</span></div>
        
        <div id="startScreen">
            <h1>🏃 平台跳躍</h1>
            <p>使用 ← → 鍵移動，↑ 鍵跳躍</p>
            <button id="startBtn" class="btn">開始遊戲</button>
        </div>

        <div id="gameOver">
            <h1>遊戲結束</h1>
            <p>你失敗了！</p>
            <button id="restartBtn" class="btn">重新開始</button>
        </div>

        <div id="winScreen">
            <h1>🎉 恭喜過關！</h1>
            <p>金幣收集: <span id="finalCoins">0</span></p>
            <button id="nextLevelBtn" class="btn" style="background: #44ff44; color: #333;">下一關</button>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const livesDisplay = document.getElementById('lives');
        const coinsDisplay = document.getElementById('coins');
        const levelDisplay = document.getElementById('level');
        const gameOverScreen = document.getElementById('gameOver');
        const winScreen = document.getElementById('winScreen');
        const startScreen = document.getElementById('startScreen');
        const finalCoinsDisplay = document.getElementById('finalCoins');
        const startBtn = document.getElementById('startBtn');
        const restartBtn = document.getElementById('restartBtn');
        const nextLevelBtn = document.getElementById('nextLevelBtn');

        let player, platforms, coins, enemies, keys, gameRunning, currentLevel, lives, totalCoins;

        const levels = [
            {
                platforms: [
                    { x: 0, y: 480, width: 800, height: 20 },
                    { x: 100, y: 380, width: 120, height: 20 },
                    { x: 300, y: 300, width: 120, height: 20 },
                    { x: 500, y: 220, width: 120, height: 20 },
                    { x: 650, y: 350, width: 100, height: 20 },
                ],
                coins: [
                    { x: 150, y: 340 },
                    { x: 350, y: 260 },
                    { x: 550, y: 180 },
                    { x: 690, y: 310 },
                ],
                enemies: [
                    { x: 200, y: 450, speed: 2 },
                    { x: 500, y: 450, speed: 3 },
                ],
                goal: { x: 700, y: 420, width: 40, height: 60 },
                playerStart: { x: 50, y: 430 }
            },
            {
                platforms: [
                    { x: 0, y: 480, width: 150, height: 20 },
                    { x: 200, y: 420, width: 100, height: 20 },
                    { x: 350, y: 350, width: 100, height: 20 },
                    { x: 500, y: 280, width: 80, height: 20 },
                    { x: 350, y: 200, width: 100, height: 20 },
                    { x: 150, y: 150, width: 100, height: 20 },
                    { x: 650, y: 480, width: 150, height: 20 },
                ],
                coins: [
                    { x: 240, y: 380 },
                    { x: 390, y: 310 },
                    { x: 530, y: 240 },
                    { x: 390, y: 160 },
                    { x: 190, y: 110 },
                    { x: 700, y: 440 },
                ],
                enemies: [
                    { x: 220, y: 390, speed: 2 },
                    { x: 360, y: 320, speed: 3 },
                ],
                goal: { x: 720, y: 420, width: 40, height: 60 },
                playerStart: { x: 30, y: 430 }
            },
            {
                platforms: [
                    { x: 0, y: 480, width: 100, height: 20 },
                    { x: 150, y: 400, width: 80, height: 20 },
                    { x: 280, y: 320, width: 80, height: 20 },
                    { x: 400, y: 250, width: 80, height: 20 },
                    { x: 520, y: 180, width: 80, height: 20 },
                    { x: 650, y: 120, width: 150, height: 20 },
                    { x: 300, y: 420, width: 100, height: 20 },
                    { x: 600, y: 350, width: 100, height: 20 },
                ],
                coins: [
                    { x: 180, y: 360 },
                    { x: 310, y: 280 },
                    { x: 430, y: 210 },
                    { x: 550, y: 140 },
                    { x: 700, y: 80 },
                    { x: 340, y: 380 },
                    { x: 640, y: 310 },
                ],
                enemies: [
                    { x: 160, y: 370, speed: 2 },
                    { x: 410, y: 220, speed: 3 },
                    { x: 530, y: 150, speed: 2 },
                ],
                goal: { x: 720, y: 60, width: 40, height: 60 },
                playerStart: { x: 30, y: 430 }
            }
        ];

        function init() {
            const level = levels[currentLevel - 1];
            player = {
                x: level.playerStart.x,
                y: level.playerStart.y,
                width: 30,
                height: 40,
                vx: 0,
                vy: 0,
                speed: 5,
                jumpPower: -12,
                grounded: false,
                facingRight: true
            };
            platforms = level.platforms;
            coins = level.coins.map(c => ({ ...c, collected: false }));
            enemies = level.enemies.map(e => ({ ...e, width: 30, height: 30 }));
            keys = {};
            gameRunning = true;
            lives = lives || 3;
            currentLevel = currentLevel || 1;
            totalCoins = totalCoins || 0;
            updateUI();
            gameOverScreen.style.display = 'none';
            winScreen.style.display = 'none';
        }

        function updateUI() {
            livesDisplay.textContent = lives;
            coinsDisplay.textContent = totalCoins;
            levelDisplay.textContent = currentLevel;
        }

        function drawPlayer() {
            ctx.fillStyle = '#ff6b6b';
            ctx.fillRect(player.x, player.y, player.width, player.height);
            
            ctx.fillStyle = '#ffccaa';
            ctx.fillRect(player.x + 5, player.y + 5, 20, 15);
            
            ctx.fillStyle = '#333';
            if (player.facingRight) {
                ctx.fillRect(player.x + 18, player.y + 8, 4, 4);
            } else {
                ctx.fillRect(player.x + 8, player.y + 8, 4, 4);
            }

            ctx.fillStyle = '#ff6b6b';
            if (player.facingRight) {
                ctx.fillRect(player.x + 20, player.y + 25, 8, 15);
            } else {
                ctx.fillRect(player.x + 2, player.y + 25, 8, 15);
            }
        }

        function drawPlatform(platform) {
            ctx.fillStyle = '#8B4513';
            ctx.fillRect(platform.x, platform.y, platform.width, platform.height);
            
            ctx.fillStyle = '#228B22';
            ctx.fillRect(platform.x, platform.y, platform.width, 6);
        }

        function drawCoin(coin) {
            if (coin.collected) return;
            ctx.fillStyle = '#FFD700';
            ctx.shadowBlur = 10;
            ctx.shadowColor = '#FFD700';
            ctx.beginPath();
            ctx.arc(coin.x + 10, coin.y + 10, 10, 0, Math.PI * 2);
            ctx.fill();
            ctx.shadowBlur = 0;
            
            ctx.fillStyle = '#FFA500';
            ctx.font = '14px Arial';
            ctx.fillText('$', coin.x + 6, coin.y + 15);
        }

        function drawEnemy(enemy) {
            ctx.fillStyle = '#663399';
            ctx.fillRect(enemy.x, enemy.y, enemy.width, enemy.height);
            
            ctx.fillStyle = '#ff0000';
            ctx.fillRect(enemy.x + 5, enemy.y + 8, 6, 6);
            ctx.fillRect(enemy.x + 19, enemy.y + 8, 6, 6);
            
            ctx.fillStyle = '#ffff00';
            ctx.fillRect(enemy.x + 8, enemy.y + 18, 14, 4);
        }

        function drawGoal(goal) {
            ctx.fillStyle = '#44ff44';
            ctx.fillRect(goal.x, goal.y, goal.width, goal.height);
            
            ctx.fillStyle = '#228B22';
            ctx.fillRect(goal.x + 10, goal.y - 20, 20, 25);
            
            ctx.fillStyle = '#ff4444';
            ctx.fillRect(goal.x + 5, goal.y + 10, 10, 20);
            ctx.fillRect(goal.x + 25, goal.y + 10, 10, 20);
        }

        function drawBackground() {
            const gradient = ctx.createLinearGradient(0, 0, 0, canvas.height);
            gradient.addColorStop(0, '#87CEEB');
            gradient.addColorStop(1, '#E0F6FF');
            ctx.fillStyle = gradient;
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            ctx.fillStyle = 'rgba(255, 255, 255, 0.8)';
            ctx.beginPath();
            ctx.arc(700, 80, 40, 0, Math.PI * 2);
            ctx.fill();

            ctx.fillStyle = 'rgba(255, 255, 255, 0.6)';
            for (let i = 0; i < 5; i++) {
                ctx.beginPath();
                ctx.arc(100 + i * 150, 50 + (i % 2) * 30, 20 + i * 5, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function update() {
            if (!gameRunning) return;

            if (keys['ArrowLeft']) {
                player.vx = -player.speed;
                player.facingRight = false;
            } else if (keys['ArrowRight']) {
                player.vx = player.speed;
                player.facingRight = true;
            } else {
                player.vx = 0;
            }

            if (keys['ArrowUp'] && player.grounded) {
                player.vy = player.jumpPower;
                player.grounded = false;
            }

            player.vy += 0.6;
            player.x += player.vx;
            player.y += player.vy;

            if (player.x < 0) player.x = 0;
            if (player.x > canvas.width - player.width) player.x = canvas.width - player.width;

            player.grounded = false;
            platforms.forEach(platform => {
                if (player.x < platform.x + platform.width &&
                    player.x + player.width > platform.x &&
                    player.y + player.height > platform.y &&
                    player.y + player.height < platform.y + platform.height + player.vy + 5) {
                    player.y = platform.y - player.height;
                    player.vy = 0;
                    player.grounded = true;
                }
            });

            if (player.y > canvas.height) {
                playerDeath();
            }

            coins.forEach(coin => {
                if (!coin.collected &&
                    player.x < coin.x + 20 &&
                    player.x + player.width > coin.x &&
                    player.y < coin.y + 20 &&
                    player.y + player.height > coin.y) {
                    coin.collected = true;
                    totalCoins += 10;
                    updateUI();
                }
            });

            const level = levels[currentLevel - 1];
            if (player.x < level.goal.x + level.goal.width &&
                player.x + player.width > level.goal.x &&
                player.y < level.goal.y + level.goal.height &&
                player.y + player.height > level.goal.y) {
                levelComplete();
            }

            enemies.forEach(enemy => {
                enemy.x += enemy.speed;
                if (enemy.x <= 0 || enemy.x >= canvas.width - enemy.width) {
                    enemy.speed *= -1;
                }

                if (player.x < enemy.x + enemy.width &&
                    player.x + player.width > enemy.x &&
                    player.y < enemy.y + enemy.height &&
                    player.y + player.height > enemy.y) {
                    playerDeath();
                }
            });
        }

        function draw() {
            drawBackground();
            platforms.forEach(drawPlatform);
            coins.forEach(drawCoin);
            enemies.forEach(drawEnemy);
            drawGoal(levels[currentLevel - 1].goal);
            drawPlayer();
        }

        function gameLoop() {
            update();
            draw();
            if (gameRunning) {
                requestAnimationFrame(gameLoop);
            }
        }

        function playerDeath() {
            lives--;
            updateUI();
            if (lives <= 0) {
                gameRunning = false;
                gameOverScreen.style.display = 'block';
            } else {
                const level = levels[currentLevel - 1];
                player.x = level.playerStart.x;
                player.y = level.playerStart.y;
                player.vx = 0;
                player.vy = 0;
            }
        }

        function levelComplete() {
            gameRunning = false;
            finalCoinsDisplay.textContent = totalCoins;
            if (currentLevel >= levels.length) {
                winScreen.querySelector('h1').textContent = '🎉 恭喜通關！';
                nextLevelBtn.textContent = '重新開始';
            } else {
                winScreen.querySelector('h1').textContent = '🎉 恭喜過關！';
                nextLevelBtn.textContent = '下一關';
            }
            winScreen.style.display = 'block';
        }

        function startGame() {
            currentLevel = 1;
            lives = 3;
            totalCoins = 0;
            init();
            startScreen.style.display = 'none';
            gameLoop();
        }

        function nextLevel() {
            if (currentLevel >= levels.length) {
                currentLevel = 1;
            } else {
                currentLevel++;
            }
            init();
            gameLoop();
        }

        document.addEventListener('keydown', (e) => {
            keys[e.key] = true;
            if (['ArrowUp', 'ArrowDown', 'ArrowLeft', 'ArrowRight', ' '].includes(e.key)) {
                e.preventDefault();
            }
        });

        document.addEventListener('keyup', (e) => {
            keys[e.key] = false;
        });

        startBtn.addEventListener('click', startGame);
        restartBtn.addEventListener('click', startGame);
        nextLevelBtn.addEventListener('click', nextLevel);

        drawBackground();
    </script>
</body>
</html>
