<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LompedDevv - VFX & SFX Maker ✨</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-light: #87CEEB;
            --primary-dark: #1e3a8a;
            --accent: #60a5fa;
            --white: #ffffff;
            --glass: rgba(255, 255, 255, 0.1);
            --glass-border: rgba(255, 255, 255, 0.2);
            --shadow: rgba(0, 0, 0, 0.1);
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(-45deg, var(--primary-light), var(--primary-dark), #3b82f6, #1d4ed8);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            color: white;
            overflow-x: hidden;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating Elements */
        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .floating-emoji {
            position: absolute;
            font-size: 2rem;
            opacity: 0.6;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { 
                transform: translateY(0px) rotate(0deg);
                opacity: 0.6;
            }
            50% { 
                transform: translateY(-20px) rotate(180deg);
                opacity: 0.8;
            }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 10;
        }

        /* Navigation */
        .nav {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 50px;
            padding: 15px 30px;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .nav:hover {
            background: rgba(255, 255, 255, 0.15);
            transform: translateX(-50%) translateY(-2px);
            box-shadow: 0 10px 40px var(--shadow);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 30px;
            align-items: center;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 8px 16px;
            border-radius: 25px;
            position: relative;
            overflow: hidden;
        }



        .nav-links a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.05);
        }

        .logo {
            font-size: 1.2rem;
            font-weight: 700;
            margin-right: 20px;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-content {
            animation: fadeInUp 1s ease 0.2s both;
        }

        .hero-emoji {
            font-size: 5rem;
            margin-bottom: 20px;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ffffff, #87CEEB, #60a5fa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: textShine 3s ease infinite;
        }

        @keyframes textShine {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero p {
            font-size: 1.4rem;
            margin-bottom: 40px;
            opacity: 0.9;
            font-weight: 300;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 18px 35px;
            background: linear-gradient(45deg, rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0.1));
            backdrop-filter: blur(20px);
            border: 2px solid rgba(255, 255, 255, 0.3);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.6s ease;
        }

        .cta-button:hover::before {
            left: 100%;
        }

        .cta-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
            background: linear-gradient(45deg, rgba(255, 255, 255, 0.3), rgba(255, 255, 255, 0.2));
        }

        /* Sections */
        .section {
            padding: 120px 0;
            position: relative;
        }

        .section-title {
            text-align: center;
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            position: relative;
        }

        .section-emoji {
            font-size: 4rem;
            display: block;
            margin-bottom: 20px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.2rem;
            opacity: 0.8;
            margin-bottom: 80px;
            font-weight: 300;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 80px;
            align-items: center;
        }

        .profile-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            padding: 50px;
            border-radius: 30px;
            text-align: center;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .profile-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.6s ease;
            opacity: 0;
        }

        .profile-card:hover::before {
            opacity: 1;
            transform: rotate(45deg) translate(20px, 20px);
        }

        .profile-card:hover {
            transform: translateY(-10px) rotate(2deg);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
        }

        .profile-emoji {
            font-size: 4rem;
            margin-bottom: 20px;
            display: block;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
        }

        .skill-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            padding: 40px;
            border-radius: 25px;
            text-align: center;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(135, 206, 235, 0.1), rgba(30, 58, 138, 0.1));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .skill-card:hover::after {
            opacity: 1;
        }

        .skill-card:hover {
            transform: translateY(-8px) scale(1.02);
            border-color: rgba(255, 255, 255, 0.4);
        }

        .skill-emoji {
            font-size: 3rem;
            margin-bottom: 20px;
            display: block;
            transition: transform 0.3s ease;
        }

        .skill-card:hover .skill-emoji {
            transform: scale(1.2) rotate(10deg);
        }

        .skill-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .skill-description {
            opacity: 0.8;
            line-height: 1.6;
        }

        /* Portfolio Section */
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .project-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 25px;
            padding: 40px;
            transition: all 0.5s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.8s ease;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: translateY(-15px) rotate(1deg);
            border-color: rgba(255, 255, 255, 0.4);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
        }

        .project-emoji {
            font-size: 3.5rem;
            margin-bottom: 20px;
            display: block;
            transition: all 0.3s ease;
        }

        .project-card:hover .project-emoji {
            transform: scale(1.3) rotate(-5deg);
            filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.5));
        }

        .project-title {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #ffffff, #87CEEB);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .project-description {
            font-size: 1.1rem;
            line-height: 1.7;
            opacity: 0.9;
        }

        /* Contact Section */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
            margin-top: 80px;
        }

        .contact-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            padding: 50px;
            border-radius: 30px;
            text-align: center;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .contact-card::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.1), transparent);
            transition: all 0.6s ease;
            transform: translate(-50%, -50%);
            border-radius: 50%;
        }

        .contact-card:hover::after {
            width: 300px;
            height: 300px;
        }

        .contact-card:hover {
            transform: translateY(-10px) scale(1.05);
            border-color: rgba(255, 255, 255, 0.5);
        }

        .contact-emoji {
            font-size: 4rem;
            margin-bottom: 25px;
            display: block;
            transition: all 0.3s ease;
        }

        .contact-card:hover .contact-emoji {
            transform: scale(1.2) rotate(360deg);
        }

        .contact-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 15px;
        }

        .contact-info {
            font-size: 1.3rem;
            font-weight: 600;
            opacity: 0.9;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
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

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .slide-left {
            opacity: 0;
            transform: translateX(-50px);
            transition: all 0.8s ease;
        }

        .slide-left.visible {
            opacity: 1;
            transform: translateX(0);
        }

        .slide-right {
            opacity: 0;
            transform: translateX(50px);
            transition: all 0.8s ease;
        }

        .slide-right.visible {
            opacity: 1;
            transform: translateX(0);
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .nav {
                position: fixed;
                top: 10px;
                width: 90%;
                padding: 10px 20px;
            }

            .nav-links {
                gap: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }

            .logo {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .section-title {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .portfolio-grid {
                grid-template-columns: 1fr;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }

            .collaborators-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.1);
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(45deg, var(--primary-light), var(--primary-dark));
            border-radius: 10px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(45deg, var(--accent), var(--primary-dark));
        }
    </style>
</head>
<body>
    <!-- Floating Elements -->
    <div class="floating-elements" id="floatingElements"></div>

    <!-- Navigation -->
    <nav class="nav">
        <div class="logo">LompedDevv ✨</div>
        <ul class="nav-links">
            <li><a href="#home">🏠 Início</a></li>
            <li><a href="#about">👨‍💻 Sobre</a></li>
            <li><a href="#portfolio">🎮 Trabalhos</a></li>
            <li><a href="#contact">📞 Contato</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <div class="hero-emoji">🎨✨🎮</div>
                <h1>LompedDevv</h1>
                <p>VFX Maker • SFX Maker • UI Designer • Programador Roblox Studio</p>
                <a href="#portfolio" class="cta-button">
                    <span>🚀</span>
                    Ver Meus Trabalhos
                </a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section" id="about">
        <div class="container">
            <h2 class="section-title">
                <span class="section-emoji">🌟</span>
                Sobre Mim
            </h2>
            <p class="section-subtitle">Criando experiências mágicas no universo Roblox</p>
            
            <div class="about-content">
                <div class="slide-left">
                    <div class="profile-card">
                        <span class="profile-emoji">👨‍🎨</span>
                        <h3>Desenvolvedor Criativo</h3>
                        <p>Especializado em transformar ideias em experiências visuais e sonoras incríveis. Com paixão por criar mundos digitais que encantam e envolvem jogadores do mundo inteiro.</p>
                    </div>
                </div>
                
                <div class="slide-right">
                    <div class="skills-grid">
                        <div class="skill-card">
                            <span class="skill-emoji">✨</span>
                            <h4 class="skill-title">VFX Creator</h4>
                            <p class="skill-description">Efeitos visuais espetaculares que dão vida aos jogos</p>
                        </div>
                        <div class="skill-card">
                            <span class="skill-emoji">🎵</span>
                            <h4 class="skill-title">SFX Designer</h4>
                            <p class="skill-description">Paisagens sonoras imersivas e efeitos únicos</p>
                        </div>
                        <div class="skill-card">
                            <span class="skill-emoji">🎨</span>
                            <h4 class="skill-title">UI/UX Artist</h4>
                            <p class="skill-description">Interfaces elegantes com animações suaves</p>
                        </div>
                        <div class="skill-card">
                            <span class="skill-emoji">⚡</span>
                            <h4 class="skill-title">Programador</h4>
                            <p class="skill-description">Código otimizado e sistemas robustos</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section class="section" id="portfolio">
        <div class="container">
            <h2 class="section-title">
                <span class="section-emoji">🏆</span>
                Meus Trabalhos
            </h2>
            <p class="section-subtitle">Projetos que impactaram milhares de jogadores</p>
            
            <div class="portfolio-grid">
                <div class="project-card fade-in">
                    <span class="project-emoji">🐾</span>
                    <h3 class="project-title">Pet Simulator X</h3>
                    <p class="project-description">Desenvolvimento completo de efeitos visuais espetaculares, interface de usuário intuitiva e sistemas de gameplay envolventes. Contribuí para criar uma das experiências mais populares do Roblox, com milhões de jogadores ativos.</p>
                </div>
                
                <div class="project-card fade-in">
                    <span class="project-emoji">⚽</span>
                    <h3 class="project-title">Soccer Zero</h3>
                    <p class="project-description">Criação de efeitos especiais dinâmicos para jogadas épicas, desenvolvimento de interface responsiva e implementação de efeitos sonoros ultra-realistas. Uma experiência de futebol que redefine os padrões de qualidade no Roblox.</p>
                </div>
                
                <div class="project-card fade-in">
                    <span class="project-emoji">🎾</span>
                    <h3 class="project-title">Tennis Zero</h3>
                    <p class="project-description">Desenvolvimento de mecânicas visuais avançadas para tênis, incluindo trails fluidos da bola, efeitos de impacto cinematográficos e interface competitiva profissional. Cada detalhe foi pensado para máxima imersão.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section" id="contact">
        <div class="container">
            <h2 class="section-title">
                <span class="section-emoji">🤝</span>
                Vamos Trabalhar Juntos
            </h2>
            <p class="section-subtitle">Entre em contato e vamos criar algo incrível</p>
            
            <div class="contact-grid">
                <div class="contact-card fade-in">
                    <span class="contact-emoji">💬</span>
                    <h4 class="contact-title">Discord</h4>
                    <p class="contact-info">lompedd</p>
                </div>
                
                <div class="contact-card fade-in">
                    <span class="contact-emoji">🎮</span>
                    <h4 class="contact-title">Roblox</h4>
                    <p class="contact-info">LompedDevv</p>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target.scrollIntoView({
                    behavior: 'smooth',
                    block: 'start'
                });
            });
        });

        // Scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe all animation elements
        document.querySelectorAll('.fade-in, .slide-left, .slide-right').forEach(el => {
            observer.observe(el);
        });

        // Create floating emojis
        function createFloatingEmojis() {
            const container = document.getElementById('floatingElements');
            const emojis = ['✨', '🎮', '🎨', '⚡', '🌟', '💫', '🎵', '🚀'];
            
            for (let i = 0; i < 15; i++) {
                const emoji = document.createElement('div');
                emoji.classList.add('floating-emoji');
                emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];
                
                // Random position
                emoji.style.left = Math.random() * 100 + '%';
                emoji.style.top = Math.random() * 100 + '%';
                
                // Random animation delay and duration
                emoji.style.animationDelay = Math.random() * 6 + 's';
                emoji.style.animationDuration = (Math.random() * 4 + 4) + 's';
                
                container.appendChild(emoji);
            }
        }

        // Initialize floating emojis
        createFloatingEmojis();

        // Parallax effect for hero
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            const rate = scrolled * -0.5;
            
            if (hero) {
                hero.style.transform = `translateY(${rate}px)`;
            }
        });

        // Add sparkle effect on hover for project cards
        document.querySelectorAll('.project-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                createSparkles(this);
            });
        });

        function createSparkles(element) {
            for (let i = 0; i < 5; i++) {
                const sparkle = document.createElement('div');
                sparkle.style.position = 'absolute';
                sparkle.style.width = '4px';
                sparkle.style.height = '4px';
                sparkle.style.background = 'white';
                sparkle.style.borderRadius = '50%';
                sparkle.style.pointerEvents = 'none';
                sparkle.style.left = Math.random() * 100 + '%';
                sparkle.style.top = Math.random() * 100 + '%';
                sparkle.style.animation = 'sparkle 1s ease-out forwards';
                
                element.appendChild(sparkle);
                
                setTimeout(() => {
                    sparkle.remove();
                }, 1000);
            }
        }

        // Add sparkle animation
        const sparkleStyle = document.createElement('style');
        sparkleStyle.textContent = `
            @keyframes sparkle {
                0% {
                    opacity: 1;
                    transform: scale(0);
                }
                50% {
                    opacity: 1;
                    transform: scale(1);
                }
                100% {
                    opacity: 0;
                    transform: scale(0);
                }
            }
        `;
        document.head.appendChild(sparkleStyle);

        // Typing effect for hero text (optional enhancement)
        function typeWriter(element, text, speed = 100) {
            let i = 0;
            element.textContent = '';
            
            function type() {
                if (i < text.length) {
                    element.textContent += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            
            type();
        }

        // Initialize typing effect after page load
        window.addEventListener('load', () => {
            const heroTitle = document.querySelector('.hero h1');
            if (heroTitle) {
                const originalText = heroTitle.textContent;
                typeWriter(heroTitle, originalText, 150);
            }
        });
    </script>
</body>
</html>
