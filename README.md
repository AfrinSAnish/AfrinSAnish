<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AFRIN S ANISH — Software Alchemist</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Clash+Display:wght@400;600;700&family=Plus+Jakarta+Sans:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #6366F1;
            --secondary: #14B8A6;
            --accent: #F59E0B;
            --dark: #0F172A;
            --darker: #020617;
            --text-light: #F1F5F9;
            --text-dim: #94A3B8;
            --glow: 0 0 20px rgba(99, 102, 241, 0.3);
            --glow-cyan: 0 0 20px rgba(20, 184, 166, 0.25);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: linear-gradient(135deg, var(--darker) 0%, #0f172a 50%, #1a1a3d 100%);
            color: var(--text-light);
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }

        /* Animated background */
        body::before {
            content: '';
            position: fixed;
            width: 200%;
            height: 200%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(99, 102, 241, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(20, 184, 166, 0.08) 0%, transparent 50%);
            animation: floatBg 15s ease-in-out infinite;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: -1;
        }

        @keyframes floatBg {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(-50px, 50px); }
        }

        /* Header Navigation */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(10px);
            border-bottom: 2px solid rgba(99, 102, 241, 0.2);
            animation: slideDown 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
        }

        @keyframes slideDown {
            from { transform: translateY(-100%); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 3rem;
            max-width: 1400px;
            margin: 0 auto;
            width: 100%;
        }

        .logo {
            font-family: 'Clash Display', sans-serif;
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--primary), var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -1px;
            cursor: pointer;
            animation: titlePulse 2s ease-in-out infinite;
        }

        @keyframes titlePulse {
            0%, 100% { filter: drop-shadow(0 0 10px rgba(99, 102, 241, 0.3)); }
            50% { filter: drop-shadow(0 0 20px rgba(20, 184, 166, 0.3)); }
        }

        nav ul {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        nav a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 600;
            position: relative;
            transition: all 0.3s ease;
            font-size: 0.95rem;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            transition: width 0.3s ease;
        }

        nav a:hover::after {
            width: 100%;
        }

        /* Main Content */
        main {
            margin-top: 80px;
            position: relative;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 4rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(99, 102, 241, 0.15) 0%, transparent 70%);
            border-radius: 50%;
            animation: pulse 4s ease-in-out infinite;
            top: 10%;
            left: 10%;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(20, 184, 166, 0.12) 0%, transparent 70%);
            border-radius: 50%;
            animation: pulse 5s ease-in-out infinite;
            bottom: 10%;
            right: 10%;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .hero-content {
            position: relative;
            z-index: 10;
            animation: fadeInUp 1s ease-out;
        }

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

        .hero h1 {
            font-family: 'Clash Display', sans-serif;
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 700;
            margin-bottom: 1rem;
            line-height: 1.1;
            letter-spacing: -2px;
            animation: textGlow 2s ease-in-out infinite;
        }

        @keyframes textGlow {
            0%, 100% {
                text-shadow: 0 0 20px rgba(99, 102, 241, 0.3), 0 0 40px rgba(99, 102, 241, 0.15);
            }
            50% {
                text-shadow: 0 0 30px rgba(20, 184, 166, 0.25), 0 0 60px rgba(99, 102, 241, 0.15);
            }
        }

        .highlight {
            background: linear-gradient(135deg, var(--primary), var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .subtitle {
            font-size: 1.3rem;
            color: var(--text-dim);
            margin-bottom: 2rem;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 3rem;
        }

        .btn {
            padding: 1rem 2.5rem;
            border: 2px solid transparent;
            border-radius: 8px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            text-decoration: none;
            display: inline-block;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), #FF1493);
            color: white;
            box-shadow: 0 0 30px rgba(255, 0, 110, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 0 50px rgba(255, 0, 110, 0.6);
            filter: brightness(1.1);
        }

        .btn-secondary {
            background: transparent;
            color: var(--secondary);
            border: 2px solid var(--secondary);
        }

        .btn-secondary:hover {
            background: rgba(0, 245, 255, 0.1);
            box-shadow: 0 0 30px rgba(0, 245, 255, 0.4);
        }

        /* Sections */
        section {
            padding: 6rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
            z-index: 5;
        }

        section h2 {
            font-family: 'Clash Display', sans-serif;
            font-size: clamp(2rem, 5vw, 3.5rem);
            margin-bottom: 3rem;
            position: relative;
            display: inline-block;
        }

        section h2::before {
            content: '';
            position: absolute;
            left: -20px;
            top: 50%;
            transform: translateY(-50%);
            width: 4px;
            height: 80%;
            background: linear-gradient(180deg, var(--primary), var(--secondary), transparent);
            border-radius: 2px;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-card {
            background: rgba(99, 102, 241, 0.05);
            border: 2px solid rgba(99, 102, 241, 0.2);
            padding: 2rem;
            border-radius: 12px;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(99, 102, 241, 0.1), transparent);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { transform: translate(-100%, -100%) rotate(45deg); }
            100% { transform: translate(100%, 100%) rotate(45deg); }
        }

        .skill-card:hover {
            border-color: var(--primary);
            background: rgba(99, 102, 241, 0.1);
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(99, 102, 241, 0.15);
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            position: relative;
            z-index: 2;
            color: var(--accent);
        }

        .skill-card p {
            color: var(--text-dim);
            position: relative;
            z-index: 2;
            line-height: 1.6;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.05), rgba(20, 184, 166, 0.05));
            border: 2px solid rgba(20, 184, 166, 0.2);
            border-radius: 12px;
            padding: 2.5rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary), var(--accent));
            animation: flowLeft 2s linear infinite;
        }

        @keyframes flowLeft {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .project-card:hover {
            transform: translateY(-15px);
            border-color: var(--secondary);
            box-shadow: 0 30px 80px rgba(20, 184, 166, 0.15);
        }

        .project-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--secondary);
            position: relative;
            z-index: 2;
        }

        .project-card p {
            color: var(--text-dim);
            line-height: 1.7;
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 2;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
            position: relative;
            z-index: 2;
        }

        .tag {
            background: rgba(99, 102, 241, 0.2);
            border: 1px solid var(--primary);
            color: var(--accent);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
        }

        /* Research Section */
        .research-list {
            display: flex;
            flex-direction: column;
            gap: 2rem;
            margin-top: 3rem;
        }

        .research-item {
            background: rgba(20, 184, 166, 0.03);
            border-left: 4px solid var(--secondary);
            padding: 2rem;
            border-radius: 8px;
            position: relative;
            transition: all 0.3s ease;
        }

        .research-item:hover {
            background: rgba(20, 184, 166, 0.08);
            transform: translateX(10px);
        }

        .research-item h3 {
            color: var(--secondary);
            margin-bottom: 0.5rem;
        }

        /* Achievements Section */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .achievement-card {
            text-align: center;
            padding: 2rem;
            background: rgba(245, 158, 11, 0.05);
            border: 2px solid rgba(245, 158, 11, 0.2);
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .achievement-card:hover {
            transform: scale(1.05) rotateY(5deg);
            border-color: var(--accent);
            box-shadow: 0 20px 50px rgba(245, 158, 11, 0.15);
        }

        .achievement-card .icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            display: block;
        }

        .achievement-card h3 {
            color: var(--accent);
            margin-bottom: 0.5rem;
        }

        /* Beyond Tech Section */
        .hobbies-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
            margin-top: 3rem;
        }

        .hobby-badge {
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(20, 184, 166, 0.1));
            border: 2px solid var(--primary);
            padding: 1.5rem;
            border-radius: 10px;
            text-align: center;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .hobby-badge:hover {
            transform: rotate(2deg) scale(1.1);
            border-color: var(--secondary);
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.2), rgba(20, 184, 166, 0.2));
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 3rem 2rem;
            border-top: 2px solid rgba(99, 102, 241, 0.1);
            color: var(--text-dim);
            position: relative;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .social-links a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
        }

        .social-links a::before {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            transition: width 0.3s ease;
        }

        .social-links a:hover::before {
            width: 100%;
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s ease-out forwards;
        }

        @media (max-width: 768px) {
            nav {
                padding: 1rem 1.5rem;
            }

            nav ul {
                gap: 1rem;
                font-size: 0.9rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            section {
                padding: 3rem 1.5rem;
            }

            .skills-grid, .projects-grid, .achievements-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <div class="logo">AFRIN 🚀</div>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#research">Research</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- Hero Section -->
        <section class="hero">
            <div class="hero-content">
                <h1>
                    Hey, I'm <span class="highlight">AFRIN</span> 👋<br>
                    <span style="color: var(--secondary);">Software Alchemist</span>
                </h1>
                <p class="subtitle">19 | Kerala | Building Crazy Cool Things</p>
                <p style="margin-bottom: 2rem; color: var(--text-dim); max-width: 600px; margin-left: auto; margin-right: auto;">
                    Computer Science + Cybersecurity + Data Science | Turning caffeine into killer projects
                </p>
                <div class="cta-buttons">
                    <button class="btn btn-primary" onclick="document.getElementById('projects').scrollIntoView()">
                        See My Work
                    </button>
                    <a href="https://linkedin.com/in/afrin-s-anish-27b824374" class="btn btn-secondary" target="_blank">
                        LinkedIn →
                    </a>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about">
            <h2>About Me</h2>
            <div style="margin-top: 3rem; display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: center;">
                <div>
                    <h3 style="color: var(--secondary); margin-bottom: 1rem; font-size: 1.3rem;">The Journey</h3>
                    <p style="color: var(--text-dim); line-height: 1.8; margin-bottom: 1rem;">
                        Currently pursuing <strong>B.Tech in CSE (Cybersecurity)</strong> @ VIT Vellore while simultaneously doing my <strong>BS in Data Science</strong> @ IIT Madras. 
                        That's right — TWO degrees at the same time. 🎓
                    </p>
                    <p style="color: var(--text-dim); line-height: 1.8; margin-bottom: 1rem;">
                        Actively contributing to <strong>GSSoC 2026</strong> (AI/Agents Track) and have already turned out some serious stuff that surprised even me. JEE Advanced qualified. DSA class topper. S grade in multidisciplinary project.
                    </p>
                    <p style="color: var(--text-dim); line-height: 1.8;">
                        When I'm not coding, you'll find me perfecting my <strong>karate black belt</strong>, playing netball at state level, or experimenting with new instruments. Yeah, I'm learning ukulele too. 😂
                    </p>
                </div>
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                    <div class="achievement-card">
                        <span class="icon">🎓</span>
                        <h3>Dual Degree</h3>
                        <p style="color: var(--text-dim); font-size: 0.9rem;">VIT + IIT Madras</p>
                    </div>
                    <div class="achievement-card">
                        <span class="icon">💻</span>
                        <h3>500+</h3>
                        <p style="color: var(--text-dim); font-size: 0.9rem;">GitHub Repos</p>
                    </div>
                    <div class="achievement-card">
                        <span class="icon">🥇</span>
                        <h3>CGPA</h3>
                        <p style="color: var(--text-dim); font-size: 0.9rem;">9.0</p>
                    </div>
                    <div class="achievement-card">
                        <span class="icon">🔬</span>
                        <h3>Patent</h3>
                        <p style="color: var(--text-dim); font-size: 0.9rem;">In Progress</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills">
            <h2>Tech Arsenal 🔧</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <h3>Languages</h3>
                    <p>Python • C++ • C • Kotlin • Java</p>
                </div>
                <div class="skill-card">
                    <h3>Frontend Magic</h3>
                    <p>React • HTML/CSS • Responsive Design • UI/UX</p>
                </div>
                <div class="skill-card">
                    <h3>Backend Power</h3>
                    <p>FastAPI • Flask • RESTful APIs • Database Design</p>
                </div>
                <div class="skill-card">
                    <h3>Mobile Dev</h3>
                    <p>Kotlin • Jetpack Compose • Android Native • App Architecture</p>
                </div>
                <div class="skill-card">
                    <h3>Security & Data</h3>
                    <p>Cybersecurity Fundamentals • Data Science • Machine Learning • EDA</p>
                </div>
                <div class="skill-card">
                    <h3>Tools & More</h3>
                    <p>Git • MySQL • Firebase • Google Cybersecurity Cert • Cloud Services</p>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects">
            <h2>Insane Projects 🚀</h2>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <h3>Brain-Controlled Wheelchair 🧠</h3>
                    <p>
                        Full-stack hackathon project using EEG sensors to control a wheelchair. Built with FastAPI backend, React frontend, and an Android companion app in Kotlin. Made people go "wait, HOW?!"
                    </p>
                    <div class="project-tags">
                        <span class="tag">FastAPI</span>
                        <span class="tag">React</span>
                        <span class="tag">Kotlin</span>
                        <span class="tag">EEG</span>
                    </div>
                </div>
                <div class="project-card fade-in" style="animation-delay: 0.2s;">
                    <h3>Netflix UI Clone 📺</h3>
                    <p>
                        Pixel-perfect Netflix UI replica with smooth animations, responsive design, and interactive features. Showcases mastery of React and CSS animations.
                    </p>
                    <div class="project-tags">
                        <span class="tag">React</span>
                        <span class="tag">CSS</span>
                        <span class="tag">UI Design</span>
                        <span class="tag">Responsive</span>
                    </div>
                </div>
                <div class="project-card fade-in" style="animation-delay: 0.4s;">
                    <h3>Multiple Hackathon Wins 🏆</h3>
                    <p>
                        Built several full-stack applications from scratch during hackathons. Each one tested a different skill: system design, user experience, speed, and innovation.
                    </p>
                    <div class="project-tags">
                        <span class="tag">Full Stack</span>
                        <span class="tag">Rapid Dev</span>
                        <span class="tag">Innovation</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Research Section -->
        <section id="research">
            <h2>Research & Innovation 📚</h2>
            <div class="research-list">
                <div class="research-item">
                    <h3>🔬 Conference Paper</h3>
                    <p>Published research currently under peer review at a top conference. Deep dive into emerging tech.</p>
                </div>
                <div class="research-item">
                    <h3>📖 Review Paper</h3>
                    <p>Comprehensive literature review covering recent advancements in the field. Submitted and waiting for evaluation.</p>
                </div>
                <div class="research-item">
                    <h3>🌐 Frontiers Journal Paper</h3>
                    <p>Research paper submitted to Frontiers journal. Currently in peer review process. This one's going to be big.</p>
                </div>
                <div class="research-item">
                    <h3>🔐 Cybersecurity Paper (Upcoming)</h3>
                    <p>Working with faculty on a cybersecurity research paper. Planning to submit soon with groundbreaking insights.</p>
                </div>
            </div>
        </section>

        <!-- Achievements Section -->
        <section>
            <h2>Achievements & Recognition 🏅</h2>
            <div class="achievements-grid">
                <div class="achievement-card">
                    <span class="icon">🎯</span>
                    <h3>DSA Class Topper</h3>
                    <p style="color: var(--text-dim);">Ranked #1 in Data Structures & Algorithms</p>
                </div>
                <div class="achievement-card">
                    <span class="icon">⭐</span>
                    <h3>S Grade</h3>
                    <p style="color: var(--text-dim);">Multidisciplinary Project</p>
                </div>
                <div class="achievement-card">
                    <span class="icon">🎓</span>
                    <h3>JEE Advanced</h3>
                    <p style="color: var(--text-dim);">Qualified with flying colors</p>
                </div>
                <div class="achievement-card">
                    <span class="icon">🤝</span>
                    <h3>GSSoC 2026</h3>
                    <p style="color: var(--text-dim);">AI/Agents Track Contributor</p>
                </div>
                <div class="achievement-card">
                    <span class="icon">🥇</span>
                    <h3>SAE India</h3>
                    <p style="color: var(--text-dim);">Design & Marketing Core</p>
                </div>
                <div class="achievement-card">
                    <span class="icon">✈️</span>
                    <h3>Rotor FPV</h3>
                    <p style="color: var(--text-dim);">Junior Core Member</p>
                </div>
            </div>
        </section>

        <!-- Beyond Tech Section -->
        <section>
            <h2>Beyond Code 🎨</h2>
            <p style="color: var(--text-dim); margin-bottom: 2rem;">
                I'm not just a coder — I'm a complete human with a million interests.
            </p>
            <div class="hobbies-grid">
                <div class="hobby-badge">🥋 Karate Black Belt</div>
                <div class="hobby-badge">🏐 State Level Netball</div>
                <div class="hobby-badge">🎸 Guitar Player</div>
                <div class="hobby-badge">🎵 Ukulele Learning</div>
                <div class="hobby-badge">🎨 Digital Art</div>
                <div class="hobby-badge">✍️ Writing</div>
                <div class="hobby-badge">🎤 Singing</div>
                <div class="hobby-badge">🏀 Basketball</div>
                <div class="hobby-badge">🎭 Creative Pursuits</div>
                <div class="hobby-badge">📱 Always Learning</div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact">
            <h2>Let's Connect 🌐</h2>
            <p style="color: var(--text-dim); margin-bottom: 3rem; text-align: center;">
                Have a wild idea? Want to collaborate? Let's make something amazing together.
            </p>
            <div style="text-align: center;">
                <div class="social-links">
                    <a href="https://linkedin.com/in/afrin-s-anish-27b824374" target="_blank">LinkedIn</a>
                    <a href="https://github.com" target="_blank">GitHub</a>
                    <a href="mailto:afrin@example.com">Email</a>
                </div>
                <p style="color: var(--text-dim); margin-top: 2rem;">
                    Based in India 📍
                </p>
            </div>
        </section>
    </main>

    <footer>
        <p>Designed & Built by Afrin ✨</p>
        <p style="margin-top: 1rem; font-size: 0.9rem;">
            Made with <span style="color: var(--primary);">❤️</span> and <span style="color: var(--secondary);">☕</span>
        </p>
    </footer>

    <script>
        // Intersection Observer for fade-in animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'all 0.8s ease-out';
            observer.observe(el);
        });

        // Smooth scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });
    </script>
</body>
</html>
