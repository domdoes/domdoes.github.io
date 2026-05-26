---
layout: homepage
---

<style>
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

<h2 id="about-me">C:\> TYPE ABOUT_ME.TXT</h2>
<p>
I'm Dom, a finance nerd based in New York City. With over six years of experience as an early finance hire at Robinhood, I specialize in scaling teams, analyzing venture philosophies, and navigating the fintech space.
</p>
<p>
Currently, I'm expanding my creative skill set through coursework in digital arts, design, and photography. I enjoy blending technical architecture with aesthetic design, whether that involves researching advanced financial options, writing Python automation scripts, or building out vector graphics in Figma.
</p>

<h2 id="projects">C:\> DIR \PROJECTS</h2>
<ul>
  <li>
    <strong>Memento Mori Time-Tracker:</strong> A custom web application that visualizes a 100-year lifespan as a 24-hour clock. Focused on aesthetic UI design and lifespan data visualization.
  </li>
  <li>
    <strong>Automated Social Tracking:</strong> Python-based tools designed to efficiently.
  </li>
</ul>

<h2 id="interests">Loading INTERESTS.CFG... [OK]</h2>
<p>
Beyond finance and code, I shoot with premium digital cameras and optimize health metrics using WHOOP fitness tracking.
</p>
