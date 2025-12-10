---
layout: default
title: Home
---

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

<style>
  /* --- GLOBAL VARIABLES & RESET --- */
  :root {
    --bg-color: #0f172a;       /* Deep Slate */
    --card-bg: #1e293b;        /* Lighter Slate */
    --text-primary: #f8fafc;   /* Off-white */
    --text-secondary: #94a3b8; /* Muted Grey */
    --accent: #38bdf8;         /* Cyan */
    --accent-glow: rgba(56, 189, 248, 0.15);
    --border: #334155;
  }

  body {
    background-color: var(--bg-color);
    color: var(--text-primary);
    font-family: 'Inter', sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
  }

  a { color: var(--accent); text-decoration: none; transition: all 0.2s; }
  a:hover { color: #7dd3fc; text-decoration: underline; }
  
  h1, h2, h3, h4 { color: var(--text-primary); margin-top: 0; }
  h1 { font-weight: 800; letter-spacing: -1px; }
  h2 { 
    border-bottom: 2px solid var(--border); 
    padding-bottom: 10px; 
    margin-top: 60px; 
    margin-bottom: 30px;
    font-size: 1.8rem;
  }

  /* --- LAYOUT UTILITIES --- */
  .container {
    max-width: 1000px;
    margin: 0 auto;
    padding: 40px 20px;
  }

  /* --- HERO SECTION --- */
  .hero {
    text-align: center;
    padding: 80px 20px;
    animation: fadeIn 1s ease-in;
  }
  .hero h1 { font-size: 3.5rem; margin-bottom: 10px; background: linear-gradient(to right, #fff, #94a3b8); -webkit-background-clip: text; -webkit-text-fill-color: transparent;}
  .hero .role { 
    font-family: 'JetBrains Mono', monospace; 
    color: var(--accent); 
    font-size: 1.25rem; 
    margin-bottom: 20px;
    display: inline-block;
    padding: 5px 15px;
    background: var(--accent-glow);
    border-radius: 5px;
  }
  .hero p { color: var(--text-secondary); max-width: 600px; margin: 0 auto 30px auto; font-size: 1.1rem;}
  .social-links { font-size: 1.5rem; }
  .social-links a { margin: 0 10px; color: var(--text-secondary); }
  .social-links a:hover { color: var(--accent); transform: scale(1.2); display: inline-block; }

  /* --- PROJECT GRID (BENTO STYLE) --- */
  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 25px;
  }
  
  .card {
    background-color: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 25px;
    transition: transform 0.2s, box-shadow 0.2s, border-color 0.2s;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  
  .card:hover {
    transform: translateY(-5px);
    border-color: var(--accent);
    box-shadow: 0 10px 30px -10px rgba(0,0,0,0.5);
  }

  .card h3 { font-size: 1.3rem; margin-bottom: 10px; }
  .card p { color: var(--text-secondary); font-size: 0.95rem; flex-grow: 1; }
  
  .tech-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 15px;
  }
  
  .pill {
    background: var(--accent-glow);
    color: var(--accent);
    padding: 4px 10px;
    border-radius: 4px;
    font-size: 0.75rem;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
  }

  /* --- EXPERIENCE TIMELINE --- */
  .timeline {
    position: relative;
    border-left: 2px solid var(--border);
    margin-left: 20px;
    padding-left: 30px;
  }
  
  .timeline-item {
    position: relative;
    margin-bottom: 50px;
  }
  
  .timeline-marker {
    position: absolute;
    left: -37px;
    top: 5px;
    width: 12px;
    height: 12px;
    background: var(--accent);
    border-radius: 50%;
    border: 4px solid var(--bg-color);
  }

  .job-header { display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; }
  .job-title { font-size: 1.3rem; font-weight: 700; color: var(--text-primary); }
  .job-company { color: var(--accent); font-family: 'JetBrains Mono', monospace; font-weight: bold; }
  .job-date { color: var(--text-secondary); font-size: 0.9rem; font-style: italic; }
  .job-details li { margin-bottom: 8px; color: #cbd5e1; }

  /* --- SKILLS SECTION --- */
  .skills-container {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
  }
  .skill-tag {
    background: var(--card-bg);
    border: 1px solid var(--border);
    padding: 8px 16px;
    border-radius: 8px;
    color: var(--text-primary);
    font-weight: 500;
  }

  /* --- RESPONSIVE --- */
  @media (max-width: 768px) {
    .hero h1 { font-size: 2.5rem; }
    .job-header { flex-direction: column; }
  }
  
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
</style>

<div class="container">

  <div class="hero">
    <h1>Nate Sepich</h1>
    <div class="role">&lt; AI Platform Engineer /&gt;</div>
    <p>Building scalable, secure solutions that drive measurable performance improvements. Expert in AI integration, Automation, and DevOps.</p>
    
    <div class="social-links">
      <a href="https://github.com/nate-sepich" target="_blank"><i class="fab fa-github"></i></a>
      <a href="https://www.linkedin.com/in/nate-sepich/" target="_blank"><i class="fab fa-linkedin"></i></a>
      <a href="mailto:sepichnathan@gmail.com"><i class="fas fa-envelope"></i></a>
    </div>
  </div>

  <h2>Featured Projects</h2>
  <div class="project-grid">

    <div class="card">
      <h3><a href="https://apps.apple.com/us/app/parsix/id6751127402" target="_blank">ParSix iOS App</a></h3>
      <p>Gamified Wordle puzzles into competitive tournaments with automated penalty management and real-time leaderboards.</p>
      <div class="tech-stack">
        <span class="pill">Python</span>
        <span class="pill">FastAPI</span>
        <span class="pill">AWS Lambda</span>
        <span class="pill">SwiftUI</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://github.com/nate-sepich/pantry-pal" target="_blank">PantryPal</a></h3>
      <p>Microservices-based AI kitchen management system combining inventory tracking with Ollama LLM recipe generation.</p>
      <div class="tech-stack">
        <span class="pill">Streamlit</span>
        <span class="pill">Docker</span>
        <span class="pill">Ollama LLM</span>
        <span class="pill">FastAPI</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://github.com/NSEP-0/fantasy-top-huds-x" target="_blank">FantasyTopHuds Bot</a></h3>
      <p>A simple call and response bot designed and implemented for the X (Twitter) platform.</p>
      <div class="tech-stack">
        <span class="pill">JavaScript</span>
        <span class="pill">AWS Lambda</span>
        <span class="pill">DynamoDB</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://nate-sepich.github.io/strava-gh-viz/" target="_blank">Strava Heatmap</a></h3>
      <p>Interactive tool visualizing running activity data with a heatmap UI and real-time serverless fetching.</p>
      <div class="tech-stack">
        <span class="pill">JavaScript</span>
        <span class="pill">OAuth2</span>
        <span class="pill">Netlify Functions</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://github.com/nate-sepich/b.t.b" target="_blank">OCR Betting Analysis</a></h3>
      <p>OCR-based application to extract and analyze betting data using Python and LLMs.</p>
      <div class="tech-stack">
        <span class="pill">Python</span>
        <span class="pill">OCR</span>
        <span class="pill">LLM Integration</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://github.com/nate-sepich/quantum_cognition" target="_blank">Graph Visualization</a></h3>
      <p>Automated graph creation for knowledge visualization using Neo4j and Large Language Models.</p>
      <div class="tech-stack">
        <span class="pill">Neo4j</span>
        <span class="pill">LLM</span>
        <span class="pill">Graph Viz</span>
      </div>
    </div>

  </div>

  <h2>Work Experience</h2>
  <div class="timeline">
    
    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">AI Platform Engineer (P3)</span>
        <span class="job-company">RTX / Collins Aerospace</span>
      </div>
      <div class="job-date">July 2025 – Present</div>
      <ul class="job-details">
        <li>Drove enterprise AI platform enablement across AWS/Azure, standardizing access patterns.</li>
        <li>Implemented compliant logging/observability pipelines and automated deployments (IaC/GitOps).</li>
        <li>Authored platform standards (CI/CD, IaC templates) reducing support tickets.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">Senior Ops Engineer (P3)</span>
        <span class="job-company">RTX / Collins Aerospace</span>
      </div>
      <div class="job-date">May 2024 – July 2025</div>
      <ul class="job-details">
        <li>Co-led a team of 4 engineers delivering an AI-Enabled Paired programming assistant to 300+ members.</li>
        <li>Architected a RAG-powered generative AI tool using AWS Step Functions, SQS, and Lambda.</li>
        <li>Awarded inaugural AI team Outstanding Technical Leadership Award.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">AI Ops Engineer (P1 & P2)</span>
        <span class="job-company">RTX / Collins Aerospace</span>
      </div>
      <div class="job-date">May 2022 – April 2024</div>
      <ul class="job-details">
        <li>Designed user architecture using DynamoDB and event-driven Lambda.</li>
        <li>Established business unit's first Nexus and Jenkins CI/CD systems.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">Data Science Intern</span>
        <span class="job-company">Principal Financial Group</span>
      </div>
      <div class="job-date">Summer 2019 – Summer 2020</div>
      <ul class="job-details">
        <li>Developed an ETL pipeline reducing processing time by 95% using Matillion and Python.</li>
        <li>Designed Power BI dashboards for real-time portfolio decision making.</li>
      </ul>
    </div>

  </div>

  <h2>Skills & Technology</h2>
  <div class="skills-container">
    <div class="skill-tag">Python</div>
    <div class="skill-tag">AWS (Lambda, SageMaker, DynamoDB)</div>
    <div class="skill-tag">Azure (OpenAI)</div>
    <div class="skill-tag">Docker & Kubernetes</div>
    <div class="skill-tag">Terraform</div>
    <div class="skill-tag">CI/CD (Jenkins, GitHub)</div>
    <div class="skill-tag">React.js</div>
    <div class="skill-tag">Neo4j</div>
    <div class="skill-tag">TensorFlow & PyTorch</div>
  </div>

  <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 40px; margin-top: 60px;">
    <div>
      <h2>Education</h2>
      <div style="margin-bottom: 20px;">
        <h4 style="margin-bottom: 5px;">M.S. Industrial Engineering & HCI</h4>
        <div style="color: var(--accent);">Iowa State University</div>
        <div style="color: var(--text-secondary); font-size: 0.9rem;">May 2022 | GPA: 3.93</div>
      </div>
      <div>
        <h4 style="margin-bottom: 5px;">B.S. Industrial Engineering</h4>
        <div style="color: var(--accent);">Iowa State University</div>
        <div style="color: var(--text-secondary); font-size: 0.9rem;">Dec 2020 | GPA: 3.55</div>
      </div>
    </div>

    <div>
      <h2>Certifications & Patents</h2>
      <ul style="list-style: none; padding: 0;">
        <li style="margin-bottom: 15px;">
          <strong style="color: var(--text-primary);">AWS Certified Cloud Practitioner</strong>
          <div style="color: var(--text-secondary); font-size: 0.9rem;">April 2025</div>
        </li>
        <li style="margin-bottom: 15px;">
          <strong style="color: var(--text-primary);">Certified SAFe 6 Product Owner</strong>
          <div style="color: var(--text-secondary); font-size: 0.9rem;">Nov 2024</div>
        </li>
        <li>
          <strong style="color: var(--text-primary);">Patent US 11587315</strong>
          <div style="color: var(--text-secondary); font-size: 0.9rem;">AR Measuring of Equipment (Deere & Co)</div>
          <a href="https://patents.justia.com/patent/11587315" target="_blank" style="font-size: 0.85rem;">View Patent &rarr;</a>
        </li>
      </ul>
    </div>
  </div>

  <h2>Selected Publications</h2>
  <ul style="color: var(--text-secondary);">
    <li><strong>The Impact of Task Workload on Cybersickness</strong> - Frontiers in Virtual Reality (2022)</li>
    <li><strong>Video Game Interface Design Patterns...</strong> - Intl. Journal of HCI (2023)</li>
    <li><strong>Predicting Cybersickness...</strong> - Computers in Human Behavior (2023)</li>
  </ul>

</div>