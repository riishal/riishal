<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rishal - Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            animation: float 6s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(50px); opacity: 0; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 2;
        }

        .header {
            text-align: center;
            padding: 80px 20px;
            animation: fadeInDown 1s ease-out;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .profile-image {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 5px solid rgba(255, 255, 255, 0.3);
            margin: 0 auto 30px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            animation: pulse 2s infinite;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3); }
            50% { transform: scale(1.05); box-shadow: 0 30px 80px rgba(0, 0, 0, 0.4); }
        }

        h1 {
            font-size: 3.5em;
            margin-bottom: 20px;
            background: linear-gradient(90deg, #fff, #f0f0f0, #fff);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shine 3s linear infinite;
        }

        @keyframes shine {
            to { background-position: 200% center; }
        }

        .typing-text {
            font-size: 1.5em;
            color: rgba(255, 255, 255, 0.9);
            min-height: 40px;
        }

        .cursor {
            display: inline-block;
            width: 3px;
            height: 1.2em;
            background: white;
            margin-left: 5px;
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }

        .stat-card:nth-child(1) { animation-delay: 0.1s; }
        .stat-card:nth-child(2) { animation-delay: 0.2s; }
        .stat-card:nth-child(3) { animation-delay: 0.3s; }
        .stat-card:nth-child(4) { animation-delay: 0.4s; }

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

        .stat-card:hover {
            transform: translateY(-10px) scale(1.05);
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .stat-icon {
            font-size: 3em;
            margin-bottom: 15px;
            display: inline-block;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .stat-card h3 {
            font-size: 2em;
            margin: 10px 0;
        }

        .skills {
            margin: 60px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5em;
            margin-bottom: 40px;
            animation: fadeIn 1s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .skill-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
            cursor: pointer;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }

        .skill-item:nth-child(1) { animation-delay: 0.1s; }
        .skill-item:nth-child(2) { animation-delay: 0.15s; }
        .skill-item:nth-child(3) { animation-delay: 0.2s; }
        .skill-item:nth-child(4) { animation-delay: 0.25s; }
        .skill-item:nth-child(5) { animation-delay: 0.3s; }
        .skill-item:nth-child(6) { animation-delay: 0.35s; }
        .skill-item:nth-child(7) { animation-delay: 0.4s; }
        .skill-item:nth-child(8) { animation-delay: 0.45s; }

        .skill-item:hover {
            transform: translateY(-5px) rotate(5deg);
            background: rgba(255, 255, 255, 0.25);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .skill-icon {
            font-size: 3em;
            margin-bottom: 10px;
            display: inline-block;
        }

        .contact {
            text-align: center;
            margin: 80px 0 40px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .social-btn {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5em;
            text-decoration: none;
            color: white;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.3);
            animation: fadeIn 1s ease-out;
        }

        .social-btn:hover {
            transform: translateY(-5px) scale(1.1);
            background: rgba(255, 255, 255, 0.3);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .email-btn {
            display: inline-block;
            padding: 15px 40px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border-radius: 50px;
            text-decoration: none;
            color: white;
            font-size: 1.1em;
            margin-top: 20px;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .email-btn:hover {
            transform: scale(1.05);
            background: rgba(255, 255, 255, 0.3);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .wave {
            display: inline-block;
            animation: wave 2s infinite;
            transform-origin: 70% 70%;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            10%, 30% { transform: rotate(14deg); }
            20% { transform: rotate(-8deg); }
            40%, 60% { transform: rotate(0deg); }
        }

        @media (max-width: 768px) {
            h1 { font-size: 2.5em; }
            .typing-text { font-size: 1.2em; }
            .section-title { font-size: 2em; }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>

    <div class="container">
        <div class="header">
            <div class="profile-image">
                <span class="wave">👋</span>
            </div>
            <h1>Hi, I'm Rishal</h1>
            <div class="typing-text" id="typing-text">
                <span id="typed"></span><span class="cursor"></span>
            </div>
        </div>

        <div class="stats">
            <div class="stat-card">
                <div class="stat-icon">💻</div>
                <h3>Web Dev</h3>
                <p>Building responsive & modern websites</p>
            </div>
            <div class="stat-card">
                <div class="stat-icon">📱</div>
                <h3>App Dev</h3>
                <p>Creating beautiful mobile experiences</p>
            </div>
            <div class="stat-card">
                <div class="stat-icon">🚀</div>
                <h3>Flutter</h3>
                <p>Currently mastering Flutter & Dart</p>
            </div>
            <div class="stat-card">
                <div class="stat-icon">🎨</div>
                <h3>UI/UX</h3>
                <p>Crafting delightful user interfaces</p>
            </div>
        </div>

        <div class="skills">
            <h2 class="section-title">Tech Stack</h2>
            <div class="skill-grid">
                <div class="skill-item">
                    <div class="skill-icon">🎯</div>
                    <h3>Flutter</h3>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">💙</div>
                    <h3>Dart</h3>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">☕</div>
                    <h3>Java</h3>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">⚡</div>
                    <h3>JavaScript</h3>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🔥</div>
                    <h3>Firebase</h3>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🤖</div>
                    <h3>Android</h3>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">🌿</div>
                    <h3>Git</h3>
                </div>
                <div class="skill-item">
                    <div class="skill-icon">📮</div>
                    <h3>Postman</h3>
                </div>
            </div>
        </div>

        <div class="contact">
            <h2 class="section-title">Let's Connect</h2>
            <div class="social-links">
                <a href="https://linkedin.com/in/rishal-muhammed-9bb017262" class="social-btn" target="_blank">💼</a>
                <a href="https://instagram.com/riishal._" class="social-btn" target="_blank">📸</a>
                <a href="https://github.com/riishal" class="social-btn" target="_blank">🐙</a>
            </div>
            <a href="mailto:rishalrishal515@gmail.com" class="email-btn">📧 Get In Touch</a>
        </div>
    </div>

    <script>
        // Typing animation
        const phrases = [
            "A passionate Web Developer",
            "A passionate App Developer",
            "A Flutter Enthusiast",
            "Building amazing experiences"
        ];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typedElement = document.getElementById('typed');

        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typedElement.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typedElement.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentPhrase.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
            }

            const typingSpeed = isDeleting ? 50 : 100;
            setTimeout(type, typingSpeed);
        }

        type();

        // Create particles
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.width = Math.random() * 5 + 2 + 'px';
            particle.style.height = particle.style.width;
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDuration = Math.random() * 3 + 4 + 's';
            particle.style.animationDelay = Math.random() * 5 + 's';
            particlesContainer.appendChild(particle);
        }

        // Mouse trail effect
        document.addEventListener('mousemove', (e) => {
            const trail = document.createElement('div');
            trail.className = 'particle';
            trail.style.left = e.clientX + 'px';
            trail.style.top = e.clientY + 'px';
            trail.style.width = '5px';
            trail.style.height = '5px';
            trail.style.position = 'fixed';
            trail.style.pointerEvents = 'none';
            trail.style.animation = 'float 1s ease-out forwards';
            document.body.appendChild(trail);
            
            setTimeout(() => trail.remove(), 1000);
        });
    </script>
</body>
</html>
