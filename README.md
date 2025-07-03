<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daim Khan - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'JetBrains Mono', 'Courier New', monospace;
            background: #0a0a0a;
            color: #fff;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 10;
        }

        /* Animated Digital Network Background */
        .digital-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at 20% 50%, rgba(0, 255, 255, 0.05) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(255, 0, 255, 0.05) 0%, transparent 50%),
                        radial-gradient(circle at 40% 80%, rgba(0, 255, 0, 0.05) 0%, transparent 50%),
                        linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
        }

        .node {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #00ffff;
            border-radius: 50%;
            box-shadow: 0 0 10px #00ffff;
            animation: pulse 2s ease-in-out infinite;
        }

        .connection {
            position: absolute;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 255, 0.3), transparent);
            animation: flow 3s linear infinite;
        }

        @keyframes pulse {
            0%, 100% { 
                transform: scale(1); 
                opacity: 0.8;
                box-shadow: 0 0 10px #00ffff;
            }
            50% { 
                transform: scale(1.5); 
                opacity: 1;
                box-shadow: 0 0 20px #00ffff, 0 0 30px #00ffff;
            }
        }

        @keyframes flow {
            0% { transform: translateX(-100px); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateX(100px); opacity: 0; }
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 60px;
            padding: 40px 0;
            animation: fadeInUp 1s ease-out;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            margin-bottom: 30px;
        }

        .profile-img {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #00ff00);
            padding: 4px;
            animation: rotate 8s linear infinite;
        }

        .profile-inner {
            width: 100%;
            height: 100%;
            background: #1a1a2e;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Ctext y='50' font-size='40' text-anchor='middle' dominant-baseline='middle' fill='%2300ffff'%3E👨‍💻%3C/text%3E%3C/svg%3E");
            background-size: 60px 60px;
            background-repeat: no-repeat;
            background-position: center;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .glitch {
            font-size: 3.5rem;
            font-weight: 900;
            text-transform: uppercase;
            position: relative;
            text-shadow: 0.05em 0 0 #00ffff, -0.03em -0.04em 0 #ff00ff,
                        0.025em 0.04em 0 #ffff00;
            animation: glitch 725ms infinite;
        }

        @keyframes glitch {
            0%, 61.5%, 100% {
                transform: translate3d(0, 0, 0);
            }
            20% {
                transform: translate3d(-2px, 2px, 0);
            }
            40% {
                transform: translate3d(-2px, -2px, 0);
            }
            60% {
                transform: translate3d(2px, 2px, 0);
            }
        }

        .subtitle {
            font-size: 1.4rem;
            color: #00ffff;
            margin-top: 20px;
            animation: typewriter 4s steps(50, end) 1s both;
            white-space: nowrap;
            overflow: hidden;
            border-right: 3px solid #00ffff;
        }

        @keyframes typewriter {
            from { width: 0; }
            to { width: 100%; }
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.02);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 255, 255, 0.2);
            border-radius: 15px;
            padding: 35px;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            animation: slideInUp 0.8s ease-out;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .skill-card:hover::before {
            left: 100%;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            border-color: #00ffff;
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.2);
        }

        .skill-header {
            display: flex;
            align-items: center;
            margin-bottom: 25px;
        }

        .skill-icon {
            width: 50px;
            height: 50px;
            margin-right: 20px;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            animation: float 3s ease-in-out infinite;
        }

        .skill-title {
            font-size: 1.5rem;
            font-weight: bold;
            color: #00ffff;
            text-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
        }

        .skill-list {
            list-style: none;
            padding: 0;
        }

        .skill-item {
            margin-bottom: 15px;
            padding: 12px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            animation: fadeInLeft 0.6s ease-out;
        }

        .skill-item::before {
            content: '▶';
            color: #00ffff;
            margin-right: 12px;
            font-size: 0.8rem;
        }

        .skill-name {
            font-weight: bold;
            color: #fff;
            margin-bottom: 5px;
        }

        .skill-desc {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
            line-height: 1.5;
        }

        /* Stats Section */
        .stats-section {
            background: rgba(255, 255, 255, 0.02);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 255, 255, 0.2);
            border-radius: 20px;
            padding: 50px;
            margin-bottom: 60px;
            text-align: center;
        }

        .stats-title {
            font-size: 2.2rem;
            margin-bottom: 40px;
            color: #00ffff;
            text-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: rgba(0, 255, 255, 0.1);
            border: 1px solid rgba(0, 255, 255, 0.3);
            border-radius: 15px;
            padding: 30px 20px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #00ffff, #ff00ff, #00ff00);
            animation: slide 2s linear infinite;
        }

        @keyframes slide {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .stat-card:hover {
            transform: scale(1.05);
            background: rgba(0, 255, 255, 0.15);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #00ffff;
            text-shadow: 0 0 10px rgba(0, 255, 255, 0.5);
            margin-bottom: 10px;
        }

        .stat-label {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1rem;
        }

        /* Tech Stack */
        .tech-section {
            margin-top: 50px;
        }

        .tech-title {
            font-size: 1.8rem;
            margin-bottom: 30px;
            color: #00ffff;
            text-align: center;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
        }

        .tech-item {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 255, 255, 0.2);
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(0, 255, 255, 0.1), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }

        .tech-item:hover::before {
            transform: translateX(100%);
        }

        .tech-item:hover {
            border-color: #00ffff;
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 255, 255, 0.2);
        }

        /* Contact Section */
        .contact-section {
            background: rgba(255, 255, 255, 0.02);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(0, 255, 255, 0.2);
            border-radius: 20px;
            padding: 50px;
            text-align: center;
        }

        .contact-title {
            font-size: 2.2rem;
            margin-bottom: 20px;
            color: #00ffff;
            text-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
        }

        .contact-desc {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            margin-bottom: 40px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            flex-wrap: wrap;
        }

        .social-link {
            display: inline-block;
            width: 60px;
            height: 60px;
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: #000;
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #ff00ff, #00ff00);
            opacity: 0;
            transition: opacity 0.3s;
        }

        .social-link:hover::before {
            opacity: 1;
        }

        .social-link:hover {
            transform: scale(1.1) rotate(360deg);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .glitch {
                font-size: 2.5rem;
            }
            
            .skills-container {
                grid-template-columns: 1fr;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .tech-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="digital-bg" id="digitalBg"></div>
    
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="profile-container">
                <div class="profile-img">
                    <div class="profile-inner"></div>
                </div>
            </div>
            <h1 class="glitch">Daim Khan</h1>
            <div class="subtitle">Full-Stack Developer | Blockchain Expert | Cybersecurity Specialist</div>
        </div>

        <!-- Skills -->
        <div class="skills-container">
            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon">🧱</div>
                    <h3 class="skill-title">Blockchain Development</h3>
                </div>
                <ul class="skill-list">
                    <li class="skill-item">
                        <div class="skill-name">Smart Contract Development</div>
                        <div class="skill-desc">Writing and deploying secure smart contracts (Solana, Solidity) for presales, tokenomics, and airdrops.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Web3 Integration</div>
                        <div class="skill-desc">Connecting dApps with wallets like Phantom, MetaMask, Trust Wallet using Web3.js.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Tokenomics & Presale Systems</div>
                        <div class="skill-desc">Designing ICO flows, vesting schedules, and investment logic.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Solana Development</div>
                        <div class="skill-desc">Creating SPL tokens, managing Solana wallets, using RPCs, Phantom/Trust integrations.</div>
                    </li>
                </ul>
            </div>

            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon">💻</div>
                    <h3 class="skill-title">Full-Stack Web Development</h3>
                </div>
                <ul class="skill-list">
                    <li class="skill-item">
                        <div class="skill-name">Frontend Development</div>
                        <div class="skill-desc">Building responsive UIs using HTML, CSS, JavaScript, React, Tailwind CSS.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Backend Development</div>
                        <div class="skill-desc">Using Node.js, Express.js, and MongoDB to build scalable backend APIs and databases.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Authentication & APIs</div>
                        <div class="skill-desc">Securing platforms with login systems, JWT, Firebase Auth, and RESTful endpoints.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Admin Dashboards & Panels</div>
                        <div class="skill-desc">Creating control centers for token sales, user tracking, and airdrop management.</div>
                    </li>
                </ul>
            </div>

            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon">🧊</div>
                    <h3 class="skill-title">3D Design & Web Graphics</h3>
                </div>
                <ul class="skill-list">
                    <li class="skill-item">
                        <div class="skill-name">Three.js & WebGL</div>
                        <div class="skill-desc">Integrating animated 3D models and GLTF/GLB assets into websites for immersive visuals.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">3D Modeling</div>
                        <div class="skill-desc">Basic modeling using Blender or other tools to create assets for web or game use.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Interactive UIs</div>
                        <div class="skill-desc">Enhancing UX with animated borders, floating elements, hover effects, and SVG animations.</div>
                    </li>
                </ul>
            </div>

            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon">🤖</div>
                    <h3 class="skill-title">Bot & Automation Development</h3>
                </div>
                <ul class="skill-list">
                    <li class="skill-item">
                        <div class="skill-name">Telegram Bots</div>
                        <div class="skill-desc">Building bots that push crypto alerts, price updates, and social media monitoring.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Discord Bots</div>
                        <div class="skill-desc">Automating tasks, community engagement, and moderation in Web3 communities.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">DEX Tools</div>
                        <div class="skill-desc">Creating scanners and bots for Raydium, PumpFun, and others to track tokens.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Trading Automation</div>
                        <div class="skill-desc">Auto-alert systems, pump-detection bots, and sniper bots.</div>
                    </li>
                </ul>
            </div>

            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon">🧠</div>
                    <h3 class="skill-title">Cybersecurity & Ethical Hacking</h3>
                </div>
                <ul class="skill-list">
                    <li class="skill-item">
                        <div class="skill-name">Vulnerability Testing</div>
                        <div class="skill-desc">Scanning and hardening code or platforms to protect against exploits.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">API & Token Security</div>
                        <div class="skill-desc">Securing exposed tokens, credentials, and user data.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Ethical Hacking</div>
                        <div class="skill-desc">Simulated attacks and logic validation to identify weaknesses before real threats.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Best Practices</div>
                        <div class="skill-desc">Following industry standards in GitHub, wallet connections, and data validation.</div>
                    </li>
                </ul>
            </div>

            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon">🎮</div>
                    <h3 class="skill-title">Game Development</h3>
                </div>
                <ul class="skill-list">
                    <li class="skill-item">
                        <div class="skill-name">Unreal Engine 5</div>
                        <div class="skill-desc">Developing cinematic experiences and immersive scenes, like car chases or open-world maps.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Game Mechanics</div>
                        <div class="skill-desc">Integrating logic, interactions, and asset handling in games.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Web-based Games</div>
                        <div class="skill-desc">Creating 2D/3D games or interactive NFTs for blockchain platforms.</div>
                    </li>
                </ul>
            </div>

            <div class="skill-card">
                <div class="skill-header">
                    <div class="skill-icon">🧰</div>
                    <h3 class="skill-title">Other Skills</h3>
                </div>
                <ul class="skill-list">
                    <li class="skill-item">
                        <div class="skill-name">UI/UX Design</div>
                        <div class="skill-desc">Wireframing and designing interfaces using Figma, Adobe XD.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">Project Branding</div>
                        <div class="skill-desc">Creating logos, banners, and full identity kits for blockchain startups.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">DevOps Basics</div>
                        <div class="skill-desc">Using GitHub for version control, CI/CD setup, environment deployment.</div>
                    </li>
                    <li class="skill-item">
                        <div class="skill-name">AI Prompting & Visual Generation</div>
                        <div class="skill-desc">Writing advanced prompts for tools like DALL·E and Sora.</div>
                    </li>
                </ul>
            </div>
        </div>

        <!-- Stats -->
        <div class="stats-section">
            <h2 class="stats-title">📊 GitHub Stats & Achievements</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">200+</div>
                    <div class="stat-label">Projects Completed</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">7+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">1500+</div>
                    <div class="stat-label">Commits This Year</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">75+</div>
                    <div class="stat-label">Technologies Mastered</div>
                </div>
            </div>

            <div class="tech-section">
                <h3 class="tech-title">🛠️ Tech Stack</h3>
                <div class="tech-grid">
                    <div class="tech-item">Solidity</div>
                    <div class="tech-item">Solana</div>
                    <div class="tech-item">Web3.js</div>
                    <div class="tech-item">React</div>
                    <div class="tech-item">Node.js</div>
                    <div class="tech-item">MongoDB</div>
                    <div class="tech-item">Three.js</div>
                    <div class="tech-item">Unreal Engine</div>
                    <div class="tech-item">Python</div>
                    <div class="tech-item">JavaScript</div>
                    <div class="tech-item">TypeScript</div>
                    <div class="tech-item">Express.js</div>
                    <div class="tech-item">Firebase</div>
                    <div class="tech-item">JWT</div>
                    <div class="tech-item">Phantom</div>
                    <div class="tech-item">MetaMask</div>
                    <div class="tech-item">Tailwind CSS</div>
                    <div class="tech-item">Blender</div>
                    <div class="tech-item">Figma</div>
                    <div class="tech-item">Git</div>
                </div>
            </div>
        </div>

        <!-- Contact -->
        <div class="contact-section">
            <h2 class="contact-title">🤝 Let's Connect</h2>
            <p class="contact-desc">Ready to collaborate on blockchain projects, full-stack development, or cybersecurity solutions? Let's build something amazing together!</p>
            <div class="social-links">
                <a href="#" class="social-link">📧</a>
                <a href="#" class="social-link">💼</a>
                <a href="#" class="social-link">🐦</a>
                <a href="#" class="social-link">📱</a>
                <a href="#" class="social-link">🔗</a>
            </div>
        </div>
    </div>

    <script>
        // Digital network background
        function createDigitalNetwork() {
            const bg = document.getElementById('digitalBg');
            const nodes = [];
            const nodeCount = 50;
            
            // Create nodes
            for (let i = 0; i < nodeCount; i++) {
                const node = document.createElement('div');
                node.className = 'node';
                node.style.left = Math.random() * 100 + '%';
                node.style.top = Math.random() * 100 + '%';
                node.style.animationDelay = Math.random() * 2 + 's';
                
                // Random colors
                const colors = ['#00ffff', '#ff00ff', '#00ff00', '#ffff00'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                node.style.background = color;
                node.style.boxShadow = `0 0 10px ${color}`;
                
                bg.appendChild(node);
                nodes.push(node);
            }
            
            // Create connections
            for (let i = 0; i < nodeCount / 2; i++) {
                const connection = document.createElement('div');
                connection.className = 'connection';
                connection.style.left = Math.random() * 100 + '%';
                connection.style.top = Math.random() * 100 + '%';
                connection.style.width = Math.random() * 200 + 100 + 'px';
                connection.style.transform = `rotate(${Math.random() * 360}deg)`;
                connection.style.animationDelay = Math.random() * 3 + 's';
                bg.appendChild(connection);
            }
        }

        // Initialize digital network
        createDigitalNetwork();

        // Animate stats numbers
        function animateStats() {
            const statNumbers = document.querySelectorAll('.stat-number');
            statNumbers.forEach(stat => {
                const finalValue = parseInt(stat.textContent);
                let currentValue = 0;
                const increment = finalValue / 100;
                const timer = setInterval(() => {
                    current
