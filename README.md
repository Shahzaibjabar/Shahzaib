<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Shahzaib · Cybersecurity Developer</title>
    <!-- Font Awesome for icons (optional, but we use it for clean icons) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <style>
        /* ---------- RESET & BASE ---------- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #0b0f1a 0%, #1a1f2e 100%);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 2rem 1rem;
        }

        .profile-card {
            max-width: 900px;
            width: 100%;
            background: rgba(255, 255, 255, 0.04);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-radius: 3rem;
            padding: 2.5rem 2rem;
            box-shadow: 0 30px 50px rgba(0, 0, 0, 0.7), inset 0 1px 2px rgba(255, 255, 255, 0.06);
            border: 1px solid rgba(255, 255, 255, 0.03);
            transition: all 0.3s ease;
        }

        /* ---------- TYPOGRAPHY ---------- */
        .glow-text {
            background: linear-gradient(135deg, #a8ff78, #78ffd6, #4facfe);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 800;
        }

        .typing-wrapper {
            display: inline-block;
            font-size: 2.2rem;
            font-weight: 700;
            color: #e0e7ff;
            letter-spacing: 1px;
        }

        .typing-wrapper .static {
            color: #cbd5e1;
        }

        .typing-wrapper .dynamic {
            display: inline-block;
            overflow: hidden;
            white-space: nowrap;
            border-right: 3px solid #4facfe;
            animation: blink-caret 0.75s step-end infinite, typewriter 3s steps(30) 1s forwards;
            width: 0;
            color: #fff;
            font-weight: 700;
        }

        @keyframes typewriter {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink-caret {
            50% { border-color: transparent; }
        }

        /* small screens: reduce font size */
        @media (max-width: 600px) {
            .typing-wrapper {
                font-size: 1.3rem;
            }
            .typing-wrapper .dynamic {
                border-right-width: 2px;
            }
        }

        h2 {
            font-size: 1.8rem;
            font-weight: 600;
            color: #e2e8f0;
            margin-bottom: 1.2rem;
            letter-spacing: -0.5px;
            position: relative;
        }

        h2::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, #4facfe, #00f2fe);
            border-radius: 4px;
            margin-top: 8px;
        }

        /* ---------- ABOUT SECTION ---------- */
        .about-list {
            list-style: none;
            padding: 0;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0.8rem 1.5rem;
            margin: 1.5rem 0 2rem 0;
        }

        .about-list li {
            color: #cbd5e1;
            font-size: 1.05rem;
            padding: 0.4rem 0;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.03);
        }

        .about-list li i {
            color: #4facfe;
            width: 22px;
            font-size: 1.1rem;
        }

        @media (max-width: 600px) {
            .about-list {
                grid-template-columns: 1fr;
            }
        }

        /* ---------- TOOLS SECTION ---------- */
        .tools-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem 2.5rem;
            padding: 1.5rem 0 0.5rem 0;
        }

        .tool-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: transform 0.2s ease;
        }

        .tool-item:hover {
            transform: translateY(-6px);
        }

        .tool-item img {
            width: 60px;
            height: 60px;
            object-fit: contain;
            filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.4));
            transition: filter 0.3s;
        }

        .tool-item:hover img {
            filter: drop-shadow(0 6px 14px rgba(79, 172, 254, 0.5));
        }

        .tool-item span {
            margin-top: 8px;
            color: #94a3b8;
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 0.5px;
            text-transform: uppercase;
        }

        /* ---------- STATS SECTION ---------- */
        .stats-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.5rem;
            margin: 2rem 0 0.5rem 0;
        }

        .stats-container img {
            max-width: 100%;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5);
            transition: transform 0.2s ease, box-shadow 0.2s ease;
            background: #0d1117;
            padding: 4px;
        }

        .stats-container img:hover {
            transform: scale(1.02);
            box-shadow: 0 12px 36px rgba(79, 172, 254, 0.2);
        }

        .stats-container .stats-card {
            flex: 1 1 280px;
            min-width: 240px;
        }

        .lang-card {
            flex: 1 1 200px;
            min-width: 200px;
        }

        /* ---------- DIVIDER ---------- */
        .divider {
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #4facfe, #00f2fe, transparent);
            margin: 2rem 0;
            opacity: 0.3;
        }

        /* ---------- FOOTER ---------- */
        .footer-text {
            text-align: center;
            color: #64748b;
            font-size: 0.95rem;
            margin-top: 1.8rem;
            letter-spacing: 0.5px;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
            padding-top: 1.8rem;
        }

        .footer-text i {
            color: #f472b6;
            margin: 0 4px;
        }

        /* ---------- RESPONSIVE ---------- */
        @media (max-width: 480px) {
            .profile-card {
                padding: 1.5rem 1rem;
                border-radius: 2rem;
            }
            .typing-wrapper {
                font-size: 1rem;
            }
            .tools-grid {
                gap: 1.2rem;
            }
            .tool-item img {
                width: 48px;
                height: 48px;
            }
        }
    </style>
</head>
<body>
    <div class="profile-card">

        <!-- ===== HEADER with typing animation (pure CSS) ===== -->
        <div style="text-align: center; margin-bottom: 0.5rem;">
            <div class="typing-wrapper">
                <span class="static">👋 Hi, I'm </span>
                <span class="dynamic">Shahzaib</span>
            </div>
            <p style="color: #94a3b8; font-size: 1.1rem; margin-top: 10px; font-weight: 300;">
                <i class="fas fa-shield-alt" style="color: #4facfe; margin-right: 6px;"></i>
                Cybersecurity Researcher · Developer
            </p>
        </div>

        <div class="divider"></div>

        <!-- ===== ABOUT ME ===== -->
        <h2><i class="fas fa-user-astronaut" style="margin-right: 12px; color: #4facfe;"></i> About Me</h2>
        <ul class="about-list">
            <li><i class="fas fa-bolt"></i> Currently working on <strong>Cybersecurity Tools</strong></li>
            <li><i class="fas fa-graduation-cap"></i> Learning <strong>Penetration Testing</strong></li>
            <li><i class="fas fa-code-branch"></i> Open to collaborate on <strong>Security Projects</strong></li>
            <li><i class="fas fa-comment-dots"></i> Ask me about <strong>Python, Java, Linux, MySQL</strong></li>
            <li><i class="fas fa-trophy"></i> Fun fact: I love <strong>CTF challenges</strong></li>
        </ul>

        <div class="divider"></div>

        <!-- ===== LANGUAGES & TOOLS (only the four you listed) ===== -->
        <h2><i class="fas fa-tools" style="margin-right: 12px; color: #4facfe;"></i> Languages & Tools</h2>
        <div class="tools-grid">
            <!-- Java -->
            <div class="tool-item">
                <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java" />
                <span>Java</span>
            </div>
            <!-- Linux -->
            <div class="tool-item">
                <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="Linux" />
                <span>Linux</span>
            </div>
            <!-- MySQL -->
            <div class="tool-item">
                <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="MySQL" />
                <span>MySQL</span>
            </div>
            <!-- Python -->
            <div class="tool-item">
                <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" />
                <span>Python</span>
            </div>
        </div>

        <div class="divider"></div>

        <!-- ===== GITHUB STATS (kept, no social badges) ===== -->
        <h2><i class="fas fa-chart-line" style="margin-right: 12px; color: #4facfe;"></i> GitHub Stats</h2>
        <div class="stats-container">
            <div class="stats-card">
                <img src="https://github-readme-stats.vercel.app/api?username=Shahzaib-Rather&show_icons=true&count_private=true&hide_border=true&title_color=4facfe&icon_color=00f2fe&text_color=c9d1d9&bg_color=0d1117" alt="GitHub Stats" />
            </div>
            <div class="stats-card">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=Shahzaib-Rather&hide_border=true&stroke=4facfe&ring=4facfe&fire=00f2fe&currStreakLabel=4facfe&background=0d1117" alt="GitHub Streak" />
            </div>
        </div>
        <div style="display: flex; justify-content: center; margin-top: 0.8rem;">
            <div class="lang-card">
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Shahzaib-Rather&layout=compact&hide_border=true&title_color=4facfe&text_color=c9d1d9&bg_color=0d1117" alt="Top Languages" style="width: 100%;" />
            </div>
        </div>

        <!-- ===== FOOTER ===== -->
        <div class="footer-text">
            <i class="fas fa-code"></i> Keep learning, keep hacking · 
            <i class="fas fa-lock" style="color: #4facfe;"></i> Stay cyber safe
        </div>

    </div>
</body>
</html>
