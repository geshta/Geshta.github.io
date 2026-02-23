<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Geshta Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --primary: #00f0ff;
  --secondary: #ff0080;
  --accent: #7000ff;
  --dark: #0a0e27;
  --darker: #050714;
  --card-bg: rgba(15, 20, 40, 0.7);
  --glow: 0 0 20px rgba(0, 240, 255, 0.3);
}

body {
  font-family: 'Space Mono', monospace;
  background: var(--darker);
  color: #ffffff;
  overflow-x: hidden;
  position: relative;
}

/* Animated background */
body::before {
  content: "";
  position: fixed;
  inset: 0;
  background: 
    radial-gradient(circle at 10% 20%, rgba(0, 240, 255, 0.1), transparent 40%),
    radial-gradient(circle at 90% 80%, rgba(255, 0, 128, 0.08), transparent 40%),
    radial-gradient(circle at 50% 50%, rgba(112, 0, 255, 0.05), transparent 50%);
  z-index: -2;
  animation: bgPulse 15s ease-in-out infinite;
}

@keyframes bgPulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.7; }
}

/* Floating particles */
.particles {
  position: fixed;
  inset: 0;
  z-index: -1;
  overflow: hidden;
  pointer-events: none;
}

.particle {
  position: absolute;
  width: 2px;
  height: 2px;
  background: var(--primary);
  border-radius: 50%;
  animation: float 20s infinite;
  opacity: 0.3;
}

.particle:nth-child(2n) { background: var(--secondary); animation-duration: 25s; }
.particle:nth-child(3n) { background: var(--accent); animation-duration: 30s; }

@keyframes float {
  0% { transform: translateY(100vh) translateX(0) scale(0); opacity: 0; }
  10% { opacity: 0.3; }
  90% { opacity: 0.3; }
  100% { transform: translateY(-100vh) translateX(100px) scale(1); opacity: 0; }
}

/* Header */
header {
  text-align: center;
  padding: 80px 20px 40px;
  position: relative;
}

.profile-container {
  position: relative;
  display: inline-block;
  animation: fadeInScale 1.2s cubic-bezier(0.34, 1.56, 0.64, 1);
}

@keyframes fadeInScale {
  0% { opacity: 0; transform: scale(0.5); }
  100% { opacity: 1; transform: scale(1); }
}

.profile {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  border: 4px solid var(--primary);
  box-shadow: 
    0 0 40px rgba(0, 240, 255, 0.6),
    0 0 80px rgba(0, 240, 255, 0.3),
    inset 0 0 20px rgba(0, 240, 255, 0.2);
  position: relative;
  animation: profilePulse 3s ease-in-out infinite;
}

@keyframes profilePulse {
  0%, 100% { box-shadow: 0 0 40px rgba(0, 240, 255, 0.6), 0 0 80px rgba(0, 240, 255, 0.3), inset 0 0 20px rgba(0, 240, 255, 0.2); }
  50% { box-shadow: 0 0 60px rgba(0, 240, 255, 0.8), 0 0 120px rgba(0, 240, 255, 0.5), inset 0 0 30px rgba(0, 240, 255, 0.3); }
}

.profile-ring {
  position: absolute;
  inset: -15px;
  border: 2px solid transparent;
  border-radius: 50%;
  border-top-color: var(--secondary);
  border-right-color: var(--accent);
  animation: rotate 4s linear infinite;
}

@keyframes rotate {
  100% { transform: rotate(360deg); }
}

h1 {
  font-family: 'Orbitron', sans-serif;
  font-size: 3rem;
  font-weight: 900;
  margin: 20px 0 10px;
  background: linear-gradient(135deg, var(--primary), var(--secondary), var(--accent));
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: fadeInUp 1s ease 0.3s both;
  text-transform: uppercase;
  letter-spacing: 3px;
}

.tagline {
  font-size: 1.1rem;
  color: #a0aec0;
  animation: fadeInUp 1s ease 0.5s both;
  letter-spacing: 1px;
}

@keyframes fadeInUp {
  0% { opacity: 0; transform: translateY(30px); }
  100% { opacity: 1; transform: translateY(0); }
}

/* Main Content */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
}

.card {
  background: var(--card-bg);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(0, 240, 255, 0.2);
  border-radius: 20px;
  padding: 35px;
  margin-bottom: 30px;
  position: relative;
  overflow: hidden;
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  animation: slideInLeft 0.8s ease both;
}

.card:nth-child(even) {
  animation: slideInRight 0.8s ease both;
}

.card:nth-child(1) { animation-delay: 0.1s; }
.card:nth-child(2) { animation-delay: 0.2s; }
.card:nth-child(3) { animation-delay: 0.3s; }
.card:nth-child(4) { animation-delay: 0.4s; }
.card:nth-child(5) { animation-delay: 0.5s; }
.card:nth-child(6) { animation-delay: 0.6s; }
.card:nth-child(7) { animation-delay: 0.7s; }

@keyframes slideInLeft {
  0% { opacity: 0; transform: translateX(-100px); }
  100% { opacity: 1; transform: translateX(0); }
}

@keyframes slideInRight {
  0% { opacity: 0; transform: translateX(100px); }
  100% { opacity: 1; transform: translateX(0); }
}

.card::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(0, 240, 255, 0.1), rgba(255, 0, 128, 0.1));
  opacity: 0;
  transition: opacity 0.5s ease;
}

.card:hover::before {
  opacity: 1;
}

.card:hover {
  transform: translateY(-10px);
  border-color: var(--primary);
  box-shadow: 
    0 20px 60px rgba(0, 0, 0, 0.5),
    0 0 40px rgba(0, 240, 255, 0.3);
}

.card::after {
  content: "";
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
  transition: left 0.7s ease;
}

.card:hover::after {
  left: 100%;
}

h2 {
  font-family: 'Orbitron', sans-serif;
  font-size: 1.8rem;
  color: var(--primary);
  margin-bottom: 20px;
  position: relative;
  display: inline-block;
  text-transform: uppercase;
  letter-spacing: 2px;
}

h2::after {
  content: "";
  position: absolute;
  bottom: -8px;
  left: 0;
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--primary), var(--secondary));
  transition: width 0.5s ease;
}

.card:hover h2::after {
  width: 100%;
}

/* Project Gallery - Horizontal Carousel */
.gallery {
  position: relative;
  overflow: hidden;
  margin-top: 25px;
  padding: 20px 0;
  mask-image: linear-gradient(90deg, transparent, black 10%, black 90%, transparent);
  -webkit-mask-image: linear-gradient(90deg, transparent, black 10%, black 90%, transparent);
}

.gallery-track {
  display: flex;
  gap: 25px;
  animation: scroll 30s linear infinite;
  width: max-content;
}

.gallery-track:hover {
  animation-play-state: paused;
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

.gallery-item {
  position: relative;
  overflow: hidden;
  border-radius: 15px;
  min-width: 350px;
  height: 250px;
  cursor: pointer;
  transition: all 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
  flex-shrink: 0;
}

.gallery-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.7s ease;
  border-radius: 15px;
  border: 2px solid rgba(0, 240, 255, 0.3);
}

.gallery-item:hover {
  transform: translateY(-15px) scale(1.1);
  z-index: 10;
}

.gallery-item:hover img {
  transform: scale(1.15);
  border-color: var(--primary);
  box-shadow: 
    0 0 40px rgba(0, 240, 255, 0.8),
    0 20px 60px rgba(0, 0, 0, 0.6);
}

.gallery-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(180deg, transparent, rgba(0, 0, 0, 0.95));
  display: flex;
  align-items: flex-end;
  padding: 20px;
  opacity: 0;
  transition: opacity 0.4s ease;
  font-weight: 700;
  font-size: 1.1rem;
  color: var(--primary);
  letter-spacing: 1px;
}

.gallery-item:hover .gallery-overlay {
  opacity: 1;
}

/* Skills */
.skills-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
  margin-top: 20px;
}

.skill-tag {
  background: linear-gradient(135deg, rgba(0, 240, 255, 0.2), rgba(112, 0, 255, 0.2));
  border: 2px solid var(--primary);
  padding: 12px 24px;
  border-radius: 50px;
  font-weight: 700;
  transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
  position: relative;
  overflow: hidden;
  cursor: pointer;
}

.skill-tag::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  transform: translate(-50%, -50%);
  transition: width 0.6s ease, height 0.6s ease;
}

.skill-tag:hover::before {
  width: 300px;
  height: 300px;
}

.skill-tag:hover {
  transform: translateY(-5px) scale(1.1);
  box-shadow: 0 10px 30px rgba(0, 240, 255, 0.4);
  border-color: var(--secondary);
}

/* Research Publication */
.publication-img {
  width: 100%;
  max-width: 400px;
  border-radius: 15px;
  border: 3px solid var(--primary);
  margin: 20px 0;
  transition: all 0.5s ease;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.5);
}

.publication-img:hover {
  transform: scale(1.05) rotate(-2deg);
  box-shadow: 0 20px 60px rgba(0, 240, 255, 0.4);
}

/* Buttons */
.resume-btn {
  display: inline-block;
  background: linear-gradient(135deg, var(--primary), var(--accent));
  color: #000;
  padding: 15px 40px;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 700;
  font-size: 1.1rem;
  transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
  position: relative;
  overflow: hidden;
  margin-top: 20px;
  text-transform: uppercase;
  letter-spacing: 2px;
  border: 2px solid var(--primary);
}

.resume-btn::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.3);
  transform: translate(-50%, -50%);
  transition: width 0.6s ease, height 0.6s ease;
}

.resume-btn:hover::before {
  width: 400px;
  height: 400px;
}

.resume-btn:hover {
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 15px 40px rgba(0, 240, 255, 0.5);
}

/* Contact Links */
.contact-info {
  display: grid;
  gap: 15px;
  margin-top: 20px;
}

.contact-item {
  display: flex;
  align-items: center;
  padding: 15px;
  background: rgba(0, 240, 255, 0.05);
  border-left: 4px solid var(--primary);
  border-radius: 10px;
  transition: all 0.4s ease;
  font-size: 1.05rem;
}

.contact-item:hover {
  background: rgba(0, 240, 255, 0.15);
  transform: translateX(10px);
  border-left-width: 8px;
}

.contact-item strong {
  color: var(--primary);
  margin-right: 10px;
  min-width: 80px;
}

.contact-item a {
  color: #ffffff;
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-item a:hover {
  color: var(--primary);
}

/* Education */
.education-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
  margin-top: 15px;
}

.education-degree {
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--primary);
}

.education-cgpa {
  font-size: 2rem;
  font-weight: 700;
  font-family: 'Orbitron', sans-serif;
  background: linear-gradient(135deg, var(--primary), var(--secondary));
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Footer */
footer {
  text-align: center;
  padding: 40px 20px;
  color: #6b7280;
  font-size: 0.9rem;
  border-top: 1px solid rgba(0, 240, 255, 0.2);
  margin-top: 60px;
}

/* Responsive */
@media (max-width: 768px) {
  h1 {
    font-size: 2rem;
  }
  
  .tagline {
    font-size: 1rem;
  }
  
  .card {
    padding: 25px;
  }
  
  h2 {
    font-size: 1.5rem;
  }
  
  .gallery-item {
    min-width: 280px;
    height: 200px;
  }
}

/* Smooth scrolling */
html {
  scroll-behavior: smooth;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  background: var(--darker);
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(180deg, var(--primary), var(--accent));
  border-radius: 10px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(180deg, var(--secondary), var(--primary));
}
</style>
</head>
<body>

<!-- Floating particles -->
<div class="particles">
  <div class="particle" style="left: 10%; animation-delay: 0s;"></div>
  <div class="particle" style="left: 20%; animation-delay: 2s;"></div>
  <div class="particle" style="left: 30%; animation-delay: 4s;"></div>
  <div class="particle" style="left: 40%; animation-delay: 1s;"></div>
  <div class="particle" style="left: 50%; animation-delay: 3s;"></div>
  <div class="particle" style="left: 60%; animation-delay: 5s;"></div>
  <div class="particle" style="left: 70%; animation-delay: 2.5s;"></div>
  <div class="particle" style="left: 80%; animation-delay: 4.5s;"></div>
  <div class="particle" style="left: 90%; animation-delay: 1.5s;"></div>
</div>

<header>
  <div class="profile-container">
    <div class="profile-ring"></div>
    <img src="images/Profile.png" class="profile" alt="Geshta Profile">
  </div>
  <h1>M Geshta Berling</h1>
  <p class="tagline">CSE (AIML) Student | Developer | AI Enthusiast</p>
</header>

<div class="container">
  <!-- About Me -->
  <div class="card">
    <h2>About Me</h2>
    <p>Computer Science Engineering student passionate about software development, automation, and AI-based applications. Experienced in Python, Java, desktop applications, and real-world project deployment.</p>
  </div>

  <!-- Milk Delivery App Project -->
  <div class="card">
    <h2>Milk Delivery App Project</h2>
    <p>Comprehensive desktop application for milk delivery management with automated billing, reporting, and customer management.</p>
    <div class="gallery">
      <div class="gallery-track">
        <div class="gallery-item">
          <img src="images/Home_Tab.png" alt="Home Tab">
          <div class="gallery-overlay">
            <span>Home Interface</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Account.png" alt="Account">
          <div class="gallery-overlay">
            <span>Account Management</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Message_tab.png" alt="Messages">
          <div class="gallery-overlay">
            <span>Messaging System</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Reports_tab.png" alt="Reports">
          <div class="gallery-overlay">
            <span>Reports Dashboard</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Month_Selection.png" alt="Month Selection">
          <div class="gallery-overlay">
            <span>Month Selector</span>
          </div>
        </div>
        <!-- Duplicate images for seamless infinite scroll -->
        <div class="gallery-item">
          <img src="images/Home_Tab.png" alt="Home Tab">
          <div class="gallery-overlay">
            <span>Home Interface</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Account.png" alt="Account">
          <div class="gallery-overlay">
            <span>Account Management</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Message_tab.png" alt="Messages">
          <div class="gallery-overlay">
            <span>Messaging System</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Reports_tab.png" alt="Reports">
          <div class="gallery-overlay">
            <span>Reports Dashboard</span>
          </div>
        </div>
        <div class="gallery-item">
          <img src="images/Month_Selection.png" alt="Month Selection">
          <div class="gallery-overlay">
            <span>Month Selector</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Research Publication -->
  <div class="card">
    <h2>Research Publication</h2>
    <img src="images/IEEE_Publication.png" class="publication-img" alt="IEEE Publication">
    <p style="margin-top: 15px;">IEEE International Conference Research Paper Presentation - Contributing to academic research in Computer Science and AI.</p>
  </div>

  <!-- Skills -->
  <div class="card">
    <h2>Skills & Technologies</h2>
    <div class="skills-grid">
      <div class="skill-tag">Python</div>
      <div class="skill-tag">Java</div>
      <div class="skill-tag">AI/ML</div>
      <div class="skill-tag">GitHub</div>
      <div class="skill-tag">Automation</div>
      <div class="skill-tag">Excel Processing</div>
      <div class="skill-tag">HTML/CSS</div>
    </div>
  </div>

  <!-- Education -->
  <div class="card">
    <h2>Education</h2>
    <div class="education-content">
      <div>
        <div class="education-degree">B.Tech CSE (AIML)</div>
        <p style="color: #a0aec0; margin-top: 5px;">Artificial Intelligence & Machine Learning</p>
      </div>
      <div class="education-cgpa">CGPA: 8.82</div>
    </div>
  </div>

  <!-- Resume -->
  <div class="card">
    <h2>Resume</h2>
    <p>Download my complete resume to learn more about my experience, projects, and achievements.</p>
    <a class="resume-btn" href="Resume.pdf" download>Download Resume</a>
  </div>

  <!-- Contact -->
  <div class="card">
    <h2>Get In Touch</h2>
    <div class="contact-info">
      <div class="contact-item">
        <strong>Email:</strong>
        <a href="mailto:mgeshta77@gmail.com">mgeshta77@gmail.com</a>
      </div>
      <div class="contact-item">
        <strong>Phone:</strong>
        <span>+91 7305853778</span>
      </div>
      <div class="contact-item">
        <strong>GitHub:</strong>
        <a href="https://github.com/geshta" target="_blank">github.com/geshta</a>
      </div>
      <div class="contact-item">
        <strong>LinkedIn:</strong>
        <a href="https://www.linkedin.com/in/geshta-berling-6195342b6" target="_blank">linkedin.com/in/geshta-berling</a>
      </div>
    </div>
  </div>
</div>

<footer>
  © 2026 M Geshta Berling | All Rights Reserved
</footer>

</body>
</html>
