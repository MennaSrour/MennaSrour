<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Menna Srour - Android Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1A1B27 0%, #2D1B69 50%, #1A1B27 100%);
            color: #FFFFFF;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Animated Header */
        .header {
            text-align: center;
            padding: 60px 0;
            position: relative;
        }

        .typing-animation {
            font-family: 'Courier New', monospace;
            font-size: 2.5rem;
            font-weight: 600;
            color: #7F52FF;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeInUp 1s ease-out forwards;
        }

        .dev-gif {
            width: 350px;
            height: 200px;
            background: linear-gradient(45deg, #7F52FF, #3DDC84);
            border-radius: 20px;
            margin: 30px auto;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            animation: float 3s ease-in-out infinite;
            position: relative;
            overflow: hidden;
        }

        .dev-gif::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            transform: rotate(-45deg);
            animation: shine 2s linear infinite;
        }

        /* About Section */
        .about-section {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            border: 1px solid rgba(127, 82, 255, 0.3);
            animation: slideInLeft 1s ease-out;
        }

        .code-block {
            background: #0D1117;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            font-family: 'Courier New', monospace;
            border-left: 4px solid #7F52FF;
            position: relative;
            overflow: hidden;
        }

        .code-block::before {
            content: 'kotlin';
            position: absolute;
            top: 10px;
            right: 15px;
            background: #7F52FF;
            color: white;
            padding: 2px 8px;
            border-radius: 4px;
            font-size: 0.8rem;
        }

        /* Tech Stack */
        .tech-stack {
            margin: 40px 0;
            text-align: center;
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }

        .tech-badge {
            background: linear-gradient(45deg, #7F52FF, #3DDC84);
            color: white;
            padding: 12px 20px;
            border-radius: 25px;
            font-weight: bold;
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-badge:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 25px rgba(127, 82, 255, 0.4);
        }

        .tech-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .tech-badge:hover::before {
            left: 100%;
        }

        /* Learning Path */
        .learning-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin: 40px 0;
        }

        .learning-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 30px;
            border: 1px solid rgba(61, 220, 132, 0.3);
            transition: transform 0.3s ease;
        }

        .learning-card:hover {
            transform: translateY(-10px);
            border-color: rgba(61, 220, 132, 0.6);
        }

        .learning-card h3 {
            color: #3DDC84;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .learning-card ul {
            list-style: none;
            padding-left: 0;
        }

        .learning-card li {
            padding: 8px 0;
            position: relative;
            padding-left: 25px;
        }

        .learning-card li::before {
            content: '▶';
            position: absolute;
            left: 0;
            color: #7F52FF;
        }

        /* Stats Section */
        .stats-section {
            text-align: center;
            margin: 40px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            border: 1px solid rgba(127, 82, 255, 0.3);
            height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
            border-color: rgba(127, 82, 255, 0.6);
        }

        .stat-placeholder {
            font-size: 3rem;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #7F52FF, #3DDC84);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Connect Section */
        .connect-section {
            text-align: center;
            margin: 40px 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
        }

        .social-link {
            background: linear-gradient(45deg, #EA4335, #0A66C2, #181717);
            color: white;
            padding: 15px 25px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
        }

        .profile-views {
            margin-top: 20px;
            font-size: 1.1rem;
            color: #7F52FF;
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

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(-45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(-45deg); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .typing-animation {
                font-size: 1.8rem;
            }
            
            .dev-gif {
                width: 280px;
                height: 160px;
                font-size: 3rem;
            }
            
            .learning-section {
                grid-template-columns: 1fr;
            }
            
            .social-links {
                flex-direction: column;
                align-items: center;
            }
            
            .tech-badges {
                justify-content: center;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #1A1B27;
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(45deg, #7F52FF, #3DDC84);
            border-radius: 4px;
        }

        /* Particle Background */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: #7F52FF;
            border-radius: 50%;
            animation: float-particle 6s linear infinite;
        }

        @keyframes float-particle {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <!-- Particle Background -->
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Header -->
        <header class="header">
            <div class="typing-animation">
                Hi there 👋 I'm Menna Srour<br>
                Android Developer
            </div>
            <div class="dev-gif">
                👩‍💻📱
            </div>
        </header>

        // About Section -->
        <section class="about-section">
            <h2>👩‍💻 About Me</h2>
            <div style="font-size: 1.2rem; line-height: 1.8; text-align: left;">
                <p>🌱 I'm currently learning <strong>Android Development with Kotlin</strong></p>
                <p>🧩 I'm exploring <strong>Jetpack Compose</strong>, <strong>MVVM</strong>, <strong>Koin</strong>, <strong>Coroutines</strong>, and <strong>Unit Testing</strong></p>
                <p>💬 Ask me about: <code style="background: rgba(127, 82, 255, 0.2); padding: 2px 6px; border-radius: 4px;">Android</code>, <code style="background: rgba(127, 82, 255, 0.2); padding: 2px 6px; border-radius: 4px;">Kotlin</code>, <code style="background: rgba(127, 82, 255, 0.2); padding: 2px 6px; border-radius: 4px;">Jetpack Compose</code>, <code style="background: rgba(127, 82, 255, 0.2); padding: 2px 6px; border-radius: 4px;">MVVM</code>, <code style="background: rgba(127, 82, 255, 0.2); padding: 2px 6px; border-radius: 4px;">Clean Architecture</code></p>
            </div>
        </section>

        <!-- Tech Stack -->
        <section class="tech-stack">
            <h2>🛠️ Tech Stack</h2>
            <div class="tech-badges">
                <div class="tech-badge">Kotlin</div>
                <div class="tech-badge">Android</div>
                <div class="tech-badge">Jetpack Compose</div>
                <div class="tech-badge">Koin</div>
                <div class="tech-badge">Retrofit</div>
            </div>
        </section>

        <!-- Learning Path -->
        <section class="learning-section">
            <div class="learning-card">
                <h3>📚 Currently Learning</h3>
                <ul>
                    <li>Jetpack Compose best practices</li>
                    <li>MVVM Architecture Pattern</li>
                    <li>Kotlin Coroutines & Flow</li>
                    <li>Unit Testing</li>
                    <li>Room Database</li>
                </ul>
            </div>
            <div class="learning-card">
                <h3>🎯 Goals for 2025</h3>
                <ul>
                    <li>Complete The Chance Scholarship</li>
                    <li>Build and publish my first app</li>
                    <li>Master Android development fundamentals</li>
                </ul>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="stats-section">
            <h2>📊 GitHub Stats</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-placeholder">📈</div>
                    <h3>GitHub Stats</h3>
                    <p>Commits, PRs, Issues & more</p>
                </div>
                <div class="stat-card">
                    <div class="stat-placeholder">🔥</div>
                    <h3>Contribution Streak</h3>
                    <p>Daily coding consistency</p>
                </div>
                <div class="stat-card">
                    <div class="stat-placeholder">💻</div>
                    <h3>Top Languages</h3>
                    <p>Kotlin</p>
                </div>
            </div>
        </section>

        <!-- Connect Section -->
        <section class="connect-section">
            <h2>📫 Let's Connect</h2>
            <div class="social-links">
                <a href="mailto:mennasrour441@gmail.com" class="social-link">Gmail</a>
                <a href="https://www.linkedin.com/in/menna-srour-713876235/" class="social-link" target="_blank">LinkedIn</a>
                <a href="https://github.com/MennaSrour" class="social-link" target="_blank">GitHub</a>
            </div>
            <div class="profile-views">
                🚀 Building amazing Android apps!
            </div>
        </section>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particles = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                
                if (Math.random() > 0.5) {
                    particle.style.background = '#3DDC84';
                }
                
                particles.appendChild(particle);
            }
        }

        // Typing animation effect
        function typeWriter() {
            const text = "Hi there 👋 I'm Menna Srour\nAndroid Developer";
            const element = document.querySelector('.typing-animation');
            let i = 0;
            
            element.innerHTML = '';
            
            function type() {
                if (i < text.length) {
                    if (text.charAt(i) === '\n') {
                        element.innerHTML += '<br>';
                    } else {
                        element.innerHTML += text.charAt(i);
                    }
                    i++;
                    setTimeout(type, 80);
                }
            }
            
            setTimeout(type, 1000);
        }

        // Intersection Observer for animations
        function observeElements() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationPlayState = 'running';
                    }
                });
            });

            document.querySelectorAll('.learning-card, .stat-card').forEach(el => {
                observer.observe(el);
            });
        }

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            typeWriter();
            observeElements();
        });

        // Add hover effects to tech badges
        document.querySelectorAll('.tech-badge').forEach(badge => {
            badge.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-5px) scale(1.05) rotateZ(2deg)';
            });
            
            badge.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1) rotateZ(0deg)';
            });
        });

        // Smooth scrolling for better UX
        document.documentElement.style.scrollBehavior = 'smooth';
    </script>
</body>
</html>
