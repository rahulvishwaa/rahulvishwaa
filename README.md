<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Preview</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: #0d1117;
            color: #c9d1d9;
            padding: 20px;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: #161b22;
            padding: 40px;
            border-radius: 12px;
            border: 1px solid #30363d;
        }
        
        h1 {
            text-align: center;
            font-size: 2.5em;
            margin-bottom: 20px;
            color: #58a6ff;
        }
        
        .typing-effect {
            text-align: center;
            font-size: 1.3em;
            color: #2e9ef7;
            margin-bottom: 30px;
            min-height: 40px;
            font-weight: 600;
        }
        
        .badges {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .badges img {
            margin: 5px;
        }
        
        hr {
            border: none;
            border-top: 1px solid #30363d;
            margin: 40px 0;
        }
        
        h2 {
            color: #58a6ff;
            font-size: 2em;
            margin: 30px 0 20px 0;
            display: flex;
            align-items: center;
        }
        
        h3 {
            color: #8b949e;
            font-size: 1.3em;
            margin: 20px 0 10px 0;
        }
        
        .about-section {
            margin-bottom: 30px;
        }
        
        .about-section ul {
            list-style: none;
            padding-left: 0;
        }
        
        .about-section li {
            padding: 8px 0;
            padding-left: 30px;
            position: relative;
        }
        
        .about-section li:before {
            content: "🏗️";
            position: absolute;
            left: 0;
        }
        
        .about-section li:nth-child(2):before { content: "☁️"; }
        .about-section li:nth-child(3):before { content: "🤖"; }
        .about-section li:nth-child(4):before { content: "🌐"; }
        .about-section li:nth-child(5):before { content: "📊"; }
        
        .achievements {
            background: #0d1117;
            padding: 20px;
            border-radius: 8px;
            border-left: 4px solid #2e9ef7;
            margin: 20px 0;
        }
        
        .achievements h3 {
            color: #58a6ff;
        }
        
        .achievements ul {
            list-style: none;
            padding-left: 0;
        }
        
        .achievements li {
            padding: 8px 0;
            padding-left: 25px;
            position: relative;
        }
        
        .achievements li:before {
            content: "✅";
            position: absolute;
            left: 0;
        }
        
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }
        
        .tech-badge {
            background: #238636;
            color: white;
            padding: 8px 16px;
            border-radius: 6px;
            font-weight: 600;
            font-size: 0.9em;
            display: inline-block;
        }
        
        .tech-badge.cloud { background: #0078d4; }
        .tech-badge.automation { background: #ee0000; }
        .tech-badge.learning { background: #7b42bc; }
        
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .stat-card {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
        }
        
        .stat-card img {
            width: 100%;
            border-radius: 6px;
        }
        
        .experience-card {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 20px;
            margin: 20px 0;
        }
        
        .experience-card h3 {
            color: #58a6ff;
            margin-top: 0;
        }
        
        .experience-date {
            color: #8b949e;
            font-style: italic;
            font-size: 0.9em;
        }
        
        .code-block {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 8px;
            padding: 20px;
            font-family: 'Courier New', monospace;
            color: #79c0ff;
            margin: 20px 0;
            overflow-x: auto;
        }
        
        .connect-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin: 20px 0;
        }
        
        .connect-btn {
            background: #0077b5;
            color: white;
            padding: 10px 20px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 600;
            display: inline-block;
            transition: transform 0.2s;
        }
        
        .connect-btn:hover {
            transform: translateY(-2px);
        }
        
        .connect-btn.email { background: #d14836; }
        .connect-btn.github { background: #24292e; }
        
        .footer {
            text-align: center;
            margin-top: 50px;
            padding-top: 30px;
            border-top: 1px solid #30363d;
            color: #8b949e;
            font-style: italic;
        }
        
        .cert-badges {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin: 20px 0;
        }
        
        .cert-badge {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 10px 20px;
            border-radius: 6px;
            font-weight: 600;
            font-size: 0.9em;
        }
        
        .cert-badge.redhat { background: linear-gradient(135deg, #ee0000 0%, #cc0000 100%); }
        .cert-badge.aws { background: linear-gradient(135deg, #ff9900 0%, #ff7700 100%); }
        .cert-badge.azure { background: linear-gradient(135deg, #0078d4 0%, #0056a3 100%); }
    </style>
</head>
<body>
    <div class="container">
        <h1>Hi there, I'm Rahul Vishwakarma 👋</h1>
        
        <div class="typing-effect" id="typing"></div>
        
        <div class="badges">
            <img src="https://komarev.com/ghpvc/?username=rahulvishwaa&label=Profile%20Views&color=0e75b6&style=for-the-badge" alt="Profile views" />
            <img src="https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin" alt="LinkedIn"/>
            <img src="https://img.shields.io/badge/Email-Contact-red?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
        </div>
        
        <hr>
        
        <h2>🚀 About Me</h2>
        <div class="about-section">
            <p>I'm a <strong>Results-driven Systems Administrator</strong> with <strong>5+ years</strong> of hands-on experience managing enterprise-scale infrastructure. Currently working at <strong>Amdocs DVCI</strong>, I specialize in:</p>
            
            <ul>
                <li>Managing <strong>5,000+ Linux RHEL servers</strong> across production, test, and development environments</li>
                <li>Architecting and maintaining <strong>VMware vSphere infrastructure</strong> with 99.9% uptime</li>
                <li>Building automation solutions that reduce manual tasks by <strong>60%</strong> using Ansible & Bash</li>
                <li>Cloud infrastructure management on <strong>AWS</strong> and <strong>Azure</strong></li>
                <li>Leading datacenter migrations and infrastructure optimization projects</li>
            </ul>
        </div>
        
        <div class="achievements">
            <h3>💡 Key Achievements</h3>
            <ul>
                <li>Reduced manual Linux administration tasks by <strong>60%</strong> through Ansible automation</li>
                <li>Decreased VM provisioning time by <strong>40%</strong> with standardized OVA/OVF templates</li>
                <li>Successfully migrated <strong>500+ VMs</strong> across datacenters with zero downtime</li>
                <li>Maintained <strong>99.9% uptime</strong> for critical VMware infrastructure</li>
                <li>Achieved <strong>95% first-time resolution rate</strong> for incident tickets</li>
            </ul>
        </div>
        
        <hr>
        
        <h2>🛠️ Technology Stack</h2>
        
        <h3>🖥️ Virtualization & Infrastructure</h3>
        <div class="tech-stack">
            <span class="tech-badge">VMware vSphere</span>
            <span class="tech-badge">ESXi</span>
            <span class="tech-badge">vCenter</span>
            <span class="tech-badge">VxRail</span>
            <span class="tech-badge">PowerFlex</span>
            <span class="tech-badge">HA/DRS</span>
        </div>
        
        <h3>🐧 Linux & Unix</h3>
        <div class="tech-stack">
            <span class="tech-badge">Red Hat Enterprise Linux</span>
            <span class="tech-badge">RHEL 6/7/8</span>
            <span class="tech-badge">Bash Scripting</span>
            <span class="tech-badge">LVM</span>
            <span class="tech-badge">NFS</span>
        </div>
        
        <h3>☁️ Cloud Platforms</h3>
        <div class="tech-stack">
            <span class="tech-badge cloud">AWS EC2</span>
            <span class="tech-badge cloud">Azure Virtual Machines</span>
            <span class="tech-badge cloud">Cloud Infrastructure</span>
        </div>
        
        <h3>🤖 Automation & DevOps</h3>
        <div class="tech-stack">
            <span class="tech-badge automation">Ansible</span>
            <span class="tech-badge automation">AWX</span>
            <span class="tech-badge automation">Jenkins</span>
            <span class="tech-badge automation">PowerCLI</span>
            <span class="tech-badge automation">Git</span>
        </div>
        
        <h3>📦 Currently Learning</h3>
        <div class="tech-stack">
            <span class="tech-badge learning">Kubernetes</span>
            <span class="tech-badge learning">OpenShift</span>
            <span class="tech-badge learning">Terraform</span>
            <span class="tech-badge learning">Docker</span>
        </div>
        
        <hr>
        
        <h2>🎓 Certifications</h2>
        <div class="cert-badges">
            <span class="cert-badge redhat">RHCSA - Red Hat Certified</span>
            <span class="cert-badge aws">AWS Cloud Practitioner</span>
            <span class="cert-badge azure">Azure Administrator (AZ-104)</span>
        </div>
        
        <hr>
        
        <h2>📊 GitHub Statistics</h2>
        <div class="stats-container">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=rahulvishwaa&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true" alt="GitHub Stats"/>
            </div>
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=rahulvishwaa&layout=compact&langs_count=8&theme=tokyonight" alt="Top Languages"/>
            </div>
        </div>
        
        <div style="text-align: center; margin: 20px 0;">
            <img src="https://github-readme-streak-stats.herokuapp.com/?user=rahulvishwaa&theme=tokyonight" alt="GitHub Streak" style="max-width: 100%; border-radius: 8px;"/>
        </div>
        
        <hr>
        
        <h2>💼 Professional Experience</h2>
        
        <div class="experience-card">
            <h3>🔷 Unix Engineer @ Amdocs DVCI</h3>
            <p class="experience-date">May 2024 - Present | Pune, India</p>
            <p>Managing enterprise infrastructure at scale with focus on automation and reliability.</p>
        </div>
        
        <div class="experience-card">
            <h3>🔷 Senior Project Engineer @ Wipro Technologies</h3>
            <p class="experience-date">Oct 2019 - May 2024 | Pune, India</p>
            <p>Led datacenter migrations and managed hyper-converged infrastructure for enterprise clients.</p>
        </div>
        
        <hr>
        
        <h2>🎯 What I'm Up To</h2>
        <div class="code-block">
current_role: Unix Engineer at Amdocs DVCI
focus_areas:
  - Container Orchestration (Kubernetes, OpenShift)
  - Infrastructure as Code (Terraform)
  - Cloud-Native Technologies
  - Automation & CI/CD Pipelines
location: Pune, India
servers_managed: 5000+
coffee_consumed: Too much ☕
        </div>
        
        <hr>
        
        <h2>📫 Let's Connect</h2>
        <div class="connect-buttons">
            <a href="https://linkedin.com/in/rvishwa1999" class="connect-btn" target="_blank">LinkedIn</a>
            <a href="mailto:rahulvishwakarmadmo@gmail.com" class="connect-btn email">Email</a>
            <a href="https://github.com/rahulvishwaa" class="connect-btn github" target="_blank">GitHub</a>
        </div>
        
        <div class="footer">
            <p>⚡ "Automating the world, one script at a time" ⚡</p>
        </div>
    </div>
    
    <script>
        const texts = [
            "VMware & Linux Systems Administrator",
            "DevOps & Cloud Infrastructure Engineer",
            "5+ Years of Enterprise Experience",
            "Automation Enthusiast"
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing');
        
        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }
            
            let typeSpeed = isDeleting ? 50 : 100;
            
            if (!isDeleting && charIndex === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                typeSpeed = 500;
            }
            
            setTimeout(type, typeSpeed);
        }
        
        type();
    </script>
</body>
</html>
