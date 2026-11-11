---
layout: default
---

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
  .hero h1 { font-size: 3.5rem; margin-bottom: 10px; background: linear-gradient(to right, #fff, #94a3b8); -webkit-background-clip: text; background-clip: text; -webkit-text-fill-color: transparent;}
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
  .hero p { color: var(--text-secondary); max-width: 680px; margin: 0 auto 16px auto; font-size: 1.1rem;}
  .social-links { font-size: 1.5rem; margin-top: 14px; }
  .social-links a { margin: 0 10px; color: var(--text-secondary); }
  .social-links a:hover { color: var(--accent); transform: scale(1.2); display: inline-block; }

  /* --- PROJECT GRID --- */
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

  .section-note {
    color: var(--text-secondary);
    margin-top: -16px;
    margin-bottom: 20px;
    font-size: 0.95rem;
  }

  .archived-grid .card {
    opacity: 0.85;
  }
  .archived-grid .card:hover {
    opacity: 1;
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

  .split-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    margin-top: 60px;
  }

  .pub-list {
    color: var(--text-secondary);
    padding-left: 20px;
  }
  .pub-list li {
    margin-bottom: 16px;
  }
  .pub-venue {
    font-size: 0.9rem;
    margin-top: 2px;
  }

  .cert-list {
    list-style: none;
    padding: 0;
  }
  .cert-list li {
    margin-bottom: 15px;
  }
  .cert-meta {
    color: var(--text-secondary);
    font-size: 0.9rem;
  }

  /* --- RESPONSIVE --- */
  @media (max-width: 768px) {
    .hero h1 { font-size: 2.5rem; }
    .job-header { flex-direction: column; }
    .split-grid { grid-template-columns: 1fr; }
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }
</style>

<div class="container">

  <div class="hero">
    <h1>Nate Sepich</h1>
    <div class="role">&lt; Senior Software Engineer /&gt;</div>
    <p>I'm a software engineer who builds AI platforms and cloud systems that hold up in production. I've spent my career in aerospace, financial services, and research.</p>
    <p>My background is in human-computer interaction, and that shapes how I build: tools should fit the people using them, not the other way around.</p>

    <div class="social-links">
      <a href="https://github.com/nate-sepich" target="_blank" rel="noopener noreferrer" aria-label="GitHub"><i class="fab fa-github"></i></a>
      <a href="https://www.linkedin.com/in/nate-sepich/" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn"><i class="fab fa-linkedin"></i></a>
      <a href="mailto:sepichnathan@gmail.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
    </div>
  </div>

  <h2>Featured Projects</h2>
  <div class="project-grid">

    <div class="card">
      <h3><a href="https://apps.apple.com/us/app/parsix/id6751127402" target="_blank" rel="noopener noreferrer">ParSix iOS App</a></h3>
      <p>Gamified Wordle puzzles into competitive tournaments with automated penalty management and real-time leaderboards.</p>
      <div class="tech-stack">
        <span class="pill">Python</span>
        <span class="pill">FastAPI</span>
        <span class="pill">AWS Lambda</span>
        <span class="pill">SwiftUI</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://github.com/nate-sepich/pantry-pal" target="_blank" rel="noopener noreferrer">PantryPal</a></h3>
      <p>Microservices-based AI kitchen management system combining inventory tracking with Ollama LLM recipe generation.</p>
      <div class="tech-stack">
        <span class="pill">Streamlit</span>
        <span class="pill">Docker</span>
        <span class="pill">Ollama LLM</span>
        <span class="pill">FastAPI</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://nate-sepich.github.io/strava-gh-viz/" target="_blank" rel="noopener noreferrer">Strava Heatmap</a></h3>
      <p>Interactive tool visualizing running activity data with a heatmap UI and real-time serverless fetching.</p>
      <div class="tech-stack">
        <span class="pill">JavaScript</span>
        <span class="pill">OAuth2</span>
        <span class="pill">Netlify Functions</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://github.com/NSEP-0/fantasy-top-huds-x" target="_blank" rel="noopener noreferrer">FantasyTopHuds Bot</a></h3>
      <p>A simple call and response bot designed and implemented for the X (Twitter) platform.</p>
      <div class="tech-stack">
        <span class="pill">JavaScript</span>
        <span class="pill">AWS Lambda</span>
        <span class="pill">DynamoDB</span>
      </div>
    </div>

  </div>

  <h2>Archived</h2>
  <p class="section-note">Personal projects kept for reference.</p>
  <div class="project-grid archived-grid">

    <div class="card">
      <h3><a href="https://github.com/nate-sepich/b.t.b" target="_blank" rel="noopener noreferrer">OCR Betting Analysis</a></h3>
      <p>OCR-based application to extract and analyze betting data using Python and LLMs.</p>
      <div class="tech-stack">
        <span class="pill">Python</span>
        <span class="pill">OCR</span>
        <span class="pill">LLM Integration</span>
      </div>
    </div>

    <div class="card">
      <h3><a href="https://github.com/nate-sepich/quantum_cognition" target="_blank" rel="noopener noreferrer">Graph Visualization</a></h3>
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
        <span class="job-title">Senior Software Engineer</span>
        <span class="job-company">Lean TECHniques</span>
      </div>
      <div class="job-date">January 2026 – Present</div>
      <ul class="job-details">
        <li>Built an Azure AI Health Check tool for assessing client AI readiness.</li>
        <li>Led a 3-person team delivering a Snowflake ML demand-forecasting pipeline for a beverage bottler.</li>
        <li>Built and deployed a Go service on Azure, and led TypeScript-based workflow discovery work.</li>
        <li>Delivered client AI demos and the &ldquo;AI for Everyone&rdquo; mini-keynote at the TAI Iowa Technology Summit.</li>
        <li>Currently doing platform engineering on a client engagement.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">AI Platform Engineer (P3)</span>
        <span class="job-company">RTX / Collins Aerospace</span>
      </div>
      <div class="job-date">July 2025 – January 2026</div>
      <ul class="job-details">
        <li>Drove enterprise AI platform enablement across AWS and Azure, standardizing access patterns.</li>
        <li>Implemented compliant logging and observability pipelines and automated deployments (IaC/GitOps).</li>
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
        <li>Co-led a team of 4 engineers delivering an AI pair-programming assistant on EKS with Helm, used by 300+ members.</li>
        <li>Architected a RAG-powered generative AI tool used by 400+ engineers, using AWS Step Functions, SQS, and Lambda.</li>
        <li>Awarded the inaugural AI team Outstanding Technical Leadership Award.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">AI Ops Engineer (P1 &amp; P2)</span>
        <span class="job-company">RTX / Collins Aerospace</span>
      </div>
      <div class="job-date">May 2022 – April 2024</div>
      <ul class="job-details">
        <li>Designed user architecture using DynamoDB and event-driven Lambda.</li>
        <li>Established the business unit's first Nexus and Jenkins CI/CD systems.</li>
      </ul>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">Graduate Research Assistant</span>
        <span class="job-company">Iowa State University</span>
      </div>
      <div class="job-date">2020 – 2022</div>
      <ul class="job-details">
        <li>Researched cybersickness and human-agent teaming at Iowa State's Virtual Reality Application Center (VRAC).</li>
        <li>Authored and co-authored peer-reviewed papers in HCI, VR, and human-agent teaming.</li>
      </ul>
    </div>

  </div>

  <h2>Skills &amp; Technology</h2>
  <div class="skills-container">
    <div class="skill-tag">Python</div>
    <div class="skill-tag">Go</div>
    <div class="skill-tag">TypeScript</div>
    <div class="skill-tag">AWS (Lambda, SageMaker, DynamoDB)</div>
    <div class="skill-tag">Azure</div>
    <div class="skill-tag">Snowflake</div>
    <div class="skill-tag">Docker &amp; Kubernetes</div>
    <div class="skill-tag">Terraform</div>
    <div class="skill-tag">CI/CD (Jenkins, GitHub)</div>
    <div class="skill-tag">RAG / LLMs</div>
    <div class="skill-tag">React.js</div>
    <div class="skill-tag">Neo4j</div>
    <div class="skill-tag">TensorFlow &amp; PyTorch</div>
  </div>

  <div class="split-grid">
    <div>
      <h2>Education</h2>
      <div style="margin-bottom: 20px;">
        <h4 style="margin-bottom: 5px;">M.S. Industrial Engineering &amp; HCI</h4>
        <div style="color: var(--accent);">Iowa State University</div>
        <div style="color: var(--text-secondary); font-size: 0.9rem;">May 2022 | GPA: 3.93</div>
      </div>
      <div>
        <h4 style="margin-bottom: 5px;">B.S. Industrial Engineering</h4>
        <div style="color: var(--accent);">Iowa State University</div>
        <div style="color: var(--text-secondary); font-size: 0.9rem;">Dec 2020 | GPA: 3.55</div>
      </div>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">Data Science Intern</span>
        <span class="job-company">Collins Aerospace</span>
      </div>
      <div class="job-date">2021</div>
    </div>

    <div class="timeline-item">
      <div class="timeline-marker"></div>
      <div class="job-header">
        <span class="job-title">Data Science Intern</span>
        <span class="job-company">Principal Financial Group</span>
      </div>
      <div class="job-date">Summer 2019 – Summer 2020</div>
      <ul class="job-details">
        <li>Developed an ETL pipeline reducing processing time by 95% using Snowflake, Matillion, and Python.</li>
        <li>Built an AWS asset-classification application.</li>
        <li>Designed Power BI dashboards for real-time portfolio decision making.</li>
      </ul>
    </div>

    <div>
      <h2>Certifications &amp; Patents</h2>
      <ul class="cert-list">
        <li>
          <strong style="color: var(--text-primary);">Claude Certified Developer – Foundations</strong>
          <div class="cert-meta">September 2026</div>
        </li>
        <li>
          <strong style="color: var(--text-primary);">Claude Code in Action &amp; Building with the Claude API</strong>
          <div class="cert-meta">April 2026</div>
        </li>
        <li>
          <strong style="color: var(--text-primary);">Microsoft Certified: Azure AI Engineer Associate (AI-102)</strong>
          <div class="cert-meta">February 2026</div>
        </li>
        <li>
          <strong style="color: var(--text-primary);">AWS Certified Cloud Practitioner</strong>
          <div class="cert-meta">April 2025</div>
        </li>
        <li>
          <strong style="color: var(--text-primary);">Certified SAFe 6 Product Owner</strong>
          <div class="cert-meta">November 2024</div>
        </li>
        <li>
          <strong style="color: var(--text-primary);">U.S. Patent 11,587,315</strong>
          <div class="cert-meta">Apparatus and methods for augmented reality measuring of equipment (Deere &amp; Co), issued February 21, 2023</div>
          <a href="https://patents.google.com/patent/US11587315B2" target="_blank" rel="noopener noreferrer" style="font-size: 0.85rem;">View Patent &rarr;</a>
        </li>
      </ul>
    </div>
  </div>

  <h2>Selected Publications</h2>
  <ul class="pub-list">
    <li>
      <a href="https://doi.org/10.1080/10447318.2023.2262824" target="_blank" rel="noopener noreferrer"><strong>Video Game Interface Design Patterns to Facilitate Human-Agent Teaming</strong></a>
      <div class="pub-venue">International Journal of Human–Computer Interaction, 2023</div>
    </li>
    <li>
      <a href="https://doi.org/10.1016/j.chb.2023.107800" target="_blank" rel="noopener noreferrer"><strong>Predicting Cybersickness Using Individual and Task Characteristics</strong></a>
      <div class="pub-venue">Computers in Human Behavior, 2023</div>
    </li>
    <li>
      <a href="https://doi.org/10.1177/1071181322661232" target="_blank" rel="noopener noreferrer"><strong>Metrics for Assessing the Quality of NFL Announcers</strong></a>
      <div class="pub-venue">Proceedings of the Human Factors and Ergonomics Society Annual Meeting, 2022</div>
    </li>
    <li>
      <a href="https://doi.org/10.3389/frvir.2022.943409" target="_blank" rel="noopener noreferrer"><strong>The Impact of Task Workload on Cybersickness</strong></a>
      <div class="pub-venue">Frontiers in Virtual Reality, 2022</div>
    </li>
    <li>
      <a href="https://doi.org/10.31274/td-20240329-877" target="_blank" rel="noopener noreferrer"><strong>Workload's Significant Impact on Cybersickness: A New Frontier</strong></a>
      <div class="pub-venue">Master's thesis, Iowa State University, 2022</div>
    </li>
    <li>
      <a href="https://doi.org/10.1109/vrw52623.2021.00037" target="_blank" rel="noopener noreferrer"><strong>Individual Differences &amp; Task Attention in Cybersickness: A Call for a Standardized Approach to Data Sharing</strong></a>
      <div class="pub-venue">IEEE Conference on Virtual Reality and 3D User Interfaces Abstracts and Workshops (VRW), 2021</div>
    </li>
    <li>
      <a href="https://doi.org/10.1177/1071181321651188" target="_blank" rel="noopener noreferrer"><strong>Human-Agent Team Game Analysis Framework: Case Studies</strong></a>
      <div class="pub-venue">Proceedings of the Human Factors and Ergonomics Society Annual Meeting, 2021</div>
    </li>
    <li>
      <a href="https://doi.org/10.1177/1071181321651185" target="_blank" rel="noopener noreferrer"><strong>The Relationship Between Personality, Recalled Cybersickness Severity, and Recalled Cybersickness Recovery Time</strong></a>
      <div class="pub-venue">Proceedings of the Human Factors and Ergonomics Society Annual Meeting, 2021</div>
    </li>
    <li>
      <a href="https://doi.org/10.1145/3385959.3418443" target="_blank" rel="noopener noreferrer"><strong>Rotational Self-motion Cues Improve Spatial Learning when Teleporting in Virtual Environments</strong></a>
      <div class="pub-venue">Symposium on Spatial User Interaction (SUI '20), 2020</div>
    </li>
  </ul>

</div>
