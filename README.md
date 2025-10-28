<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nainia Youssef | AI & Game Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #ff00cc;
            --secondary: #00ffff;
            --accent: #ffcc00;
            --dark: #0a0a2a;
            --light: #f0f8ff;
            --neon-glow: 0 0 10px currentColor, 0 0 20px currentColor, 0 0 40px currentColor;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--dark) 0%, #1a1a3a 100%);
            color: var(--light);
            overflow-x: hidden;
            min-height: 100vh;
        }
        
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.3;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 0;
            border-bottom: 2px solid var(--primary);
            margin-bottom: 3rem;
            animation: glow 3s infinite alternate;
        }
        
        @keyframes glow {
            from { box-shadow: 0 0 5px var(--primary); }
            to { box-shadow: 0 0 20px var(--primary), 0 0 30px var(--secondary); }
        }
        
        .logo {
            font-size: 2.5rem;
            font-weight: 800;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: var(--neon-glow);
        }
        
        .visitor-counter {
            background: rgba(0, 0, 0, 0.5);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            border: 1px solid var(--accent);
            font-family: 'Courier New', monospace;
            box-shadow: 0 0 10px var(--accent);
        }
        
        .hero {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            margin-bottom: 4rem;
            align-items: center;
        }
        
        .profile-card {
            background: rgba(10, 10, 42, 0.7);
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid var(--secondary);
            transition: transform 0.5s, box-shadow 0.5s;
            position: relative;
            overflow: hidden;
        }
        
        .profile-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 255, 255, 0.4);
        }
        
        .profile-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(0, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }
        
        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 1.5rem;
            border: 3px solid var(--primary);
            box-shadow: 0 0 20px var(--primary);
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: var(--dark);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .tagline {
            font-size: 1.2rem;
            color: var(--secondary);
            margin-bottom: 1.5rem;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .social-links a {
            color: var(--light);
            font-size: 1.5rem;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            color: var(--accent);
            transform: scale(1.3);
            text-shadow: var(--neon-glow);
        }
        
        .skills-section {
            margin-bottom: 4rem;
        }
        
        h2 {
            font-size: 2rem;
            margin-bottom: 2rem;
            text-align: center;
            color: var(--accent);
            text-shadow: 0 0 10px var(--accent);
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.5rem;
        }
        
        .skill-card {
            background: rgba(255, 204, 0, 0.1);
            border-radius: 10px;
            padding: 1.5rem;
            text-align: center;
            transition: all 0.3s;
            border: 1px solid transparent;
            position: relative;
            overflow: hidden;
        }
        
        .skill-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            box-shadow: 0 5px 15px rgba(255, 204, 0, 0.3);
        }
        
        .skill-card i {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--accent);
        }
        
        .ai-animation, .game-animation {
            height: 300px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
        
        .pacman-container {
            position: relative;
            width: 200px;
            height: 200px;
        }
        
        .pacman {
            width: 0;
            height: 0;
            border: 100px solid var(--accent);
            border-right: 100px solid transparent;
            border-radius: 100px;
            animation: eat 0.7s infinite;
            position: absolute;
            top: 0;
            left: 0;
        }
        
        @keyframes eat {
            0% { transform: rotate(0deg); }
            50% { transform: rotate(35deg); }
            100% { transform: rotate(0deg); }
        }
        
        .dot {
            position: absolute;
            width: 30px;
            height: 30px;
            background: var(--secondary);
            border-radius: 50%;
            top: 85px;
            left: 220px;
            animation: dots 5s infinite linear;
        }
        
        .dot:nth-child(2) {
            animation-delay: 0.5s;
        }
        
        .dot:nth-child(3) {
            animation-delay: 1s;
        }
        
        .dot:nth-child(4) {
            animation-delay: 1.5s;
        }
        
        @keyframes dots {
            0% { left: 220px; }
            100% { left: -50px; }
        }
        
        .robot {
            width: 150px;
            height: 200px;
            position: relative;
        }
        
        .robot-head {
            width: 120px;
            height: 100px;
            background: var(--secondary);
            border-radius: 30px 30px 0 0;
            position: relative;
            margin: 0 auto;
        }
        
        .robot-eye {
            width: 20px;
            height: 20px;
            background: var(--dark);
            border-radius: 50%;
            position: absolute;
            top: 30px;
            animation: blink 3s infinite;
        }
        
        .robot-eye.left {
            left: 30px;
        }
        
        .robot-eye.right {
            right: 30px;
        }
        
        @keyframes blink {
            0%, 90%, 100% { transform: scaleY(1); }
            95% { transform: scaleY(0.1); }
        }
        
        .robot-body {
            width: 150px;
            height: 100px;
            background: var(--primary);
            border-radius: 0 0 20px 20px;
            position: relative;
        }
        
        .robot-arm {
            width: 30px;
            height: 80px;
            background: var(--primary);
            position: absolute;
            top: 0;
            border-radius: 15px;
        }
        
        .robot-arm.left {
            left: -35px;
            transform-origin: top right;
            animation: wave-left 2s infinite alternate;
        }
        
        .robot-arm.right {
            right: -35px;
            transform-origin: top left;
            animation: wave-right 2s infinite alternate;
        }
        
        @keyframes wave-left {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(-20deg); }
        }
        
        @keyframes wave-right {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(20deg); }
        }
        
        .projects-section {
            margin-bottom: 4rem;
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background: rgba(255, 0, 204, 0.1);
            border-radius: 15px;
            padding: 1.5rem;
            transition: all 0.3s;
            border: 1px solid transparent;
            position: relative;
            overflow: hidden;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 10px 20px rgba(255, 0, 204, 0.3);
        }
        
        .project-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
        }
        
        .project-card h3 {
            color: var(--primary);
            margin-bottom: 1rem;
        }
        
        footer {
            text-align: center;
            padding: 2rem 0;
            border-top: 1px solid var(--secondary);
            margin-top: 3rem;
        }
        
        .pulse {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        @media (max-width: 768px) {
            .hero {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
        }
    </style>
</head>
<body>
    <canvas class="matrix-bg" id="matrix"></canvas>
    
    <div class="container">
        <header>
            <div class="logo">NY</div>
            <div class="visitor-counter">
                <i class="fas fa-eye"></i> Visitors: <span id="count">1024</span>
            </div>
        </header>
        
        <section class="hero">
            <div class="profile-card pulse">
                <div class="profile-img">
                    <i class="fas fa-robot"></i>
                </div>
                <h1>Nainia Youssef</h1>
                <p class="tagline">AI & Data Science Student | Game & App Developer</p>
                <p>20 years old passionate developer from Morocco, blending artificial intelligence with creative game development.</p>
                
                <div class="social-links">
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-github"></i></a>
                </div>
            </div>
            
            <div class="ai-animation">
                <div class="robot">
                    <div class="robot-head">
                        <div class="robot-eye left"></div>
                        <div class="robot-eye right"></div>
                    </div>
                    <div class="robot-body">
                        <div class="robot-arm left"></div>
                        <div class="robot-arm right"></div>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="skills-section">
            <h2>Technical Arsenal</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <i class="fab fa-python"></i>
                    <h3>Python</h3>
                    <p>AI/ML, Data Science</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-brain"></i>
                    <h3>AI & ML</h3>
                    <p>Neural Networks, Deep Learning</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-js-square"></i>
                    <h3>JavaScript</h3>
                    <p>React, Node.js, Express</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-gamepad"></i>
                    <h3>Game Dev</h3>
                    <p>GD Script, Unity, C#</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-database"></i>
                    <h3>Databases</h3>
                    <p>SQL, MongoDB</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-code"></i>
                    <h3>Web Dev</h3>
                    <p>HTML, CSS, React</p>
                </div>
            </div>
        </section>
        
        <section class="game-animation">
            <div class="pacman-container">
                <div class="pacman"></div>
                <div class="dot"></div>
                <div class="dot"></div>
                <div class="dot"></div>
                <div class="dot"></div>
            </div>
        </section>
        
        <section class="projects-section">
            <h2>Creative Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>AI-Powered Game NPCs</h3>
                    <p>Developed intelligent non-player characters using machine learning algorithms for realistic gameplay interactions.</p>
                </div>
                <div class="project-card">
                    <h3>Data Visualization Dashboard</h3>
                    <p>Created interactive dashboards with Chart.js and React for complex data analysis and presentation.</p>
                </div>
                <div class="project-card">
                    <h3>Multiplayer Web Game</h3>
                    <p>Built an engaging multiplayer experience using Node.js, Socket.io and React with real-time interactions.</p>
                </div>
            </div>
        </section>
        
        <footer>
            <p>© 2023 Nainia Youssef | AI Enthusiast & Game Developer</p>
            <p>Let's connect and build the future together!</p>
        </footer>
    </div>

    <script>
        // Matrix background effect
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');
        
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        const chars = "010101010101010101AI人工智能0101010101010101";
        const charArray = chars.split("");
        
        const font_size = 14;
        const columns = canvas.width / font_size;
        
        const drops = [];
        for(let x = 0; x < columns; x++)
            drops[x] = 1;
        
        function drawMatrix() {
            ctx.fillStyle = "rgba(10, 10, 42, 0.04)";
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = "#0F0";
            ctx.font = font_size + "px arial";
            
            for(let i = 0; i < drops.length; i++) {
                const text = charArray[Math.floor(Math.random() * charArray.length)];
                ctx.fillText(text, i * font_size, drops[i] * font_size);
                
                if(drops[i] * font_size > canvas.height && Math.random() > 0.975)
                    drops[i] = 0;
                
                drops[i]++;
            }
        }
        
        setInterval(drawMatrix, 35);
        
        // Visitor counter animation
        let count = 1024;
        const countElement = document.getElementById('count');
        
        setInterval(() => {
            count += Math.floor(Math.random() * 3);
            countElement.textContent = count;
        }, 5000);
        
        // Add hover effects to all cards
        document.querySelectorAll('.skill-card, .project-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });
    </script>
</body>
</html>
