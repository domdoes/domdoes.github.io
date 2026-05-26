---
layout: homepage
---

<style>
  .section-container {
    display: flex;
    gap: 25px;
    align-items: flex-start;
    margin-bottom: 40px;
    flex-wrap: wrap; /* Allows stacking on mobile */
  }
  .ascii-icon {
    font-size: 14px;
    line-height: 1.1;
    margin: 0;
    padding: 0;
    color: var(--accent-color); /* Uses the active theme's accent color */
    background: none;
    border: none;
  }
  .section-content {
    flex: 1;
    min-width: 250px;
  }
  .blink-cursor {
    display: inline-block;
    width: 10px;
    height: 20px;
    background-color: var(--text-color);
    animation: blink 1s step-end infinite;
    vertical-align: middle;
    margin-left: 8px;
  }
  /* Boot Screen Overlay */
  #boot-screen {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background-color: var(--bg-color);
    z-index: 99999;
    display: flex;
    flex-direction: column;
    padding: 40px;
    font-family: 'IBM Plex Mono', monospace;
    color: var(--text-color);
  }
  #boot-text {
    font-size: 18px;
    line-height: 1.8;
  }
</style>

<div id="boot-screen">
  <div id="boot-text"></div>
  <div style="margin-top: 5px;"><span class="blink-cursor"></span></div>
</div>

<script>
  // Boot Sequence Logic
  const bootScreen = document.getElementById('boot-screen');
  const bootText = document.getElementById('boot-text');
  const lines = [
    "Booting D/DOAN OS v2.0...",
    "Loading aesthetic_ui.css... [OK]",
    "Initializing automation_scripts.py... [OK]",
    "Mounting Memento_Mori.exe... [OK]",
    "Access Granted."
  ];
  
  let delay = 0;
  // Type out each line with a 400ms delay between them
  lines.forEach((line, index) => {
    setTimeout(() => {
      bootText.innerHTML += line + "<br>";
      // If it's the last line, wait 600ms then hide the boot screen
      if (index === lines.length - 1) {
        setTimeout(() => {
          bootScreen.style.display = 'none';
        }, 600); 
      }
    }, delay);
    delay += 400; 
  });
</script>

<div class="section-container">
  <pre class="ascii-icon">
   _______   
  /       \  
 |  O   O  | 
 |    ^    | 
 |  \___/  | 
  \_______/  
  </pre>
  
  <div class="section-content">
    <h2 id="about-me">C:\> TYPE ABOUT_ME.TXT<span class="blink-cursor"></span></h2>
    <p>
    I'm Dom, a finance professional and designer based in New York City. With over six years of experience as an early finance hire at Robinhood, I specialize in scaling teams, analyzing venture philosophies, and navigating the fintech space.
    </p>
    <p>
    Currently, I'm expanding my creative skill set through coursework in digital arts, design, and photography at Santiago Canyon College. I enjoy blending technical architecture with aesthetic design, whether that involves researching advanced financial options, writing Python automation scripts, or building out vector graphics in Figma.
    </p>
  </div>
</div>

<div class="section-container">
  <pre class="ascii-icon">
  .-------.  
 /   $ $   \ 
|   $$$$$   |
|  $$$$$$$  |
|   $$$$$   |
 \   $ $   / 
  '-------'  
  </pre>

  <div class="section-content">
    <h2 id="projects">C:\> DIR \PROJECTS<span class="blink-cursor"></span></h2>
    <ul>
      <li>
        <strong>Memento Mori Time-Tracker:</strong> A custom web application that visualizes a 100-year lifespan as a 24-hour clock. Focused on aesthetic UI design and lifespan data visualization.
      </li>
      <li>
        <strong>Automated Social Tracking:</strong> Python-based web scraping tools designed to efficiently track and extract social media data.
      </li>
    </ul>
  </div>
</div>

<div class="section-container">
  <pre class="ascii-icon">
 ___________ 
|  _______  |
| |1234567| |
| |_______| |
|  __ __ __ |
| |7||8||9| |
| |4||5||6| |
| |1||2||3| |
| |0||.||=| |
|___________|
  </pre>

  <div class="section-content">
    <h2 id="interests">Loading INTERESTS.CFG... [OK]<span class="blink-cursor"></span></h2>
    <p>
    Beyond finance and code, I shoot with premium rangefinder-style digital cameras and optimize health metrics using WHOOP fitness tracking.
    </p>
  </div>
</div>
