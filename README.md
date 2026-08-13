<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Shahzaib · Cybersecurity Dev</title>
  <style>
    /* ----- RESET & BASE ----- */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #0b0f1a, #1a1f2e);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 2rem 1rem;
    }

    .card {
      max-width: 880px;
      width: 100%;
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border-radius: 3rem;
      padding: 2.5rem 2rem;
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.7), inset 0 1px 2px rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(255, 255, 255, 0.03);
    }

    /* ----- TYPOGRAPHY & ANIMATION ----- */
    .glow {
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

    @media (max-width: 600px) {
      .typing-wrapper { font-size: 1.3rem; }
      .typing-wrapper .dynamic { border-right-width: 2px; }
    }

    h2 {
      font-size: 1.8rem;
      font-weight: 600;
      color: #e2e8f0;
      margin: 1.8rem 0 1rem 0;
      letter-spacing: -0.5px;
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    h2::after {
      content: '';
      flex: 1;
      height: 3px;
      background: linear-gradient(90deg, #4facfe, #00f2fe);
      border-radius: 4px;
      margin-left: 0.5rem;
    }

    /* ----- ABOUT LIST ----- */
    .about-grid {
      list-style: none;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 0.6rem 1.5rem;
      padding: 0.5rem 0 1rem 0;
    }

    .about-grid li {
      color: #cbd5e1;
      font-size: 1.05rem;
      padding: 0.4rem 0;
      display: flex;
      align-items: center;
      gap: 0.7rem;
      border-bottom: 1px solid rgba(255, 255, 255, 0.03);
    }

    .about-grid li span {
      font-weight: 600;
      color: #e2e8f0;
    }

    @media (max-width: 600px) {
      .about-grid { grid-template-columns: 1fr; }
    }

    /* ----- TOOLS (only 4) ----- */
    .tools {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 2.5rem 3rem;
      padding: 1.2rem 0 0.2rem 0;
    }

    .tool {
      display: flex;
      flex-direction: column;
      align-items: center;
      transition: transform 0.2s;
    }

    .tool:hover {
      transform: translateY(-6px);
    }

    .tool img {
      width: 58px;
      height: 58px;
      object-fit: contain;
      filter: drop-shadow(0 4px 8px rgba(0,0,0,0.4));
      transition: filter 0.3s;
    }

    .tool:hover img {
      filter: drop-shadow(0 6px 14px rgba(79, 172, 254, 0.5));
    }

    .tool span {
      margin-top: 6px;
      color: #94a3b8;
      font-size: 0.85rem;
      font-weight: 500;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    /* ----- STATS ----- */
    .stats-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1.5rem;
      margin: 1rem 0 0.5rem 0;
    }

    .stats-row img {
      max-width: 100%;
      height: auto;
      border-radius: 12px;
      box-shadow: 0 8px 24px rgba(0,0,0,0.5);
      background: #0d1117;
      padding: 4px;
      transition: transform 0.2s, box-shadow 0.2s;
    }

    .stats-row img:hover {
      transform: scale(1.02);
      box-shadow: 0 12px 36px rgba(79, 172, 254, 0.2);
    }

    .stat-card {
      flex: 1 1 260px;
      min-width: 220px;
    }

    .lang-card {
      flex: 1 1 200px;
      min-width: 180px;
    }

    /* ----- DIVIDER & FOOTER ----- */
    .divider {
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, transparent, #4facfe, #00f2fe, transparent);
      margin: 1.8rem 0;
      opacity: 0.25;
    }

    .footer {
      text-align: center;
      color: #64748b;
      font-size: 0.95rem;
      margin-top: 2rem;
      padding-top: 1.5rem;
      border-top: 1px solid rgba(255,255,255,0.04);
    }

    .footer span {
      color: #f472b6;
    }

    /* ----- RESPONSIVE TWEAKS ----- */
    @media (max-width: 480px) {
      .card { padding: 1.5rem 1rem; border-radius: 2rem; }
      .typing-wrapper { font-size: 1rem; }
      .tools { gap: 1.5rem; }
      .tool img { width: 46px; height: 46px; }
    }
  </style>
</head>
<body>
  <div class="card">

    <!-- ===== HEADER with pure CSS typing ===== -->
    <div style="text-align: center; margin-bottom: 0.2rem;">
      <div class="typing-wrapper">
        <span class="static">👋 Hi, I'm </span>
        <span class="dynamic">Shahzaib</span>
      </div>
      <p style="color: #94a3b8; font-size: 1.1rem; margin-top: 8px; font-weight: 300;">
        🔒 Cybersecurity Researcher · Developer
      </p>
    </div>

    <div class="divider"></div>

    <!-- ===== ABOUT ===== -->
    <h2>🧑‍💻 About Me</h2>
    <ul class="about-grid">
      <li>⚡ Currently working on <span>Cybersecurity Tools</span></li>
      <li>🎓 Learning <span>Penetration Testing &amp; Malware Analysis</span></li>
      <li>🤝 Open to collaborate on <span>Security Projects</span></li>
      <li>💬 Ask me about <span>Python, Java, Linux, MySQL</span></li>
      <li>🏆 Fun fact: I love <span>CTF challenges</span></li>
    </ul>

    <div class="divider"></div>

    <!-- ===== LANGUAGES & TOOLS (only Java, Linux, MySQL, Python) ===== -->
    <h2>🛠️ Languages &amp; Tools</h2>
    <div class="tools">
      <div class="tool">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java" />
        <span>Java</span>
      </div>
      <div class="tool">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="Linux" />
        <span>Linux</span>
      </div>
      <div class="tool">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="MySQL" />
        <span>MySQL</span>
      </div>
      <div class="tool">
        <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" />
        <span>Python</span>
      </div>
    </div>

    <div class="divider"></div>

    <!-- ===== GITHUB STATS (no extra badges) ===== -->
    <h2>📊 GitHub Stats</h2>
    <div class="stats-row">
      <div class="stat-card">
        <img src="https://github-readme-stats.vercel.app/api?username=Shahzaib-Rather&show_icons=true&count_private=true&hide_border=true&title_color=4facfe&icon_color=00f2fe&text_color=c9d1d9&bg_color=0d1117" alt="GitHub Stats" />
      </div>
      <div class="stat-card">
        <img src="https://github-readme-streak-stats.herokuapp.com/?user=Shahzaib-Rather&hide_border=true&stroke=4facfe&ring=4facfe&fire=00f2fe&currStreakLabel=4facfe&background=0d1117" alt="GitHub Streak" />
      </div>
    </div>
    <div style="display: flex; justify-content: center; margin-top: 0.8rem;">
      <div class="lang-card">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Shahzaib-Rather&layout=compact&hide_border=true&title_color=4facfe&text_color=c9d1d9&bg_color=0d1117" alt="Top Languages" style="width:100%;" />
      </div>
    </div>

    <!-- ===== FOOTER ===== -->
    <div class="footer">
      💻 Keep learning, keep hacking · <span>🔐</span> Stay cyber safe
    </div>

  </div>
</body>
</html>
