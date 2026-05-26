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
    justify-content: flex-end; /* Pushes skyline to bottom */
    overflow: hidden;
  }

  /* Container for the typing text */
  #boot-text-container {
    position: absolute;
    top: 40px;
    left: 40px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 18px;
    line-height: 1.8;
    color: var(--text-color);
    z-index: 2; /* Keeps text above the skyline */
  }

  /* Skyline ASCII Art */
  #boot-skyline {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 8px; /* Small text to fit the grid */
    line-height: 1;
    color: var(--text-color);
    opacity: 0.8;
    white-space: pre;
    text-align: center;
    margin-bottom: -10px; /* Anchors it to the very bottom */
    z-index: 1;
  }
</style>

<div id="boot-screen">
  
  <div id="boot-text-container">
    <div id="boot-text"></div>
    <div style="margin-top: 5px;"><span class="blink-cursor"></span></div>
  </div>

  <div id="boot-skyline">
                                                |
                                                |
                                                |
                                                |
                                                |
                                               _|_
                                              |   |
                                              |   |
                                              |   |
                                             _|___|_
                                            |       |
                                            |_______|
                                            |       |
                                            |_______|
                                            |       |
                                            |_______|
                                            |       |
                                            |_______|
                                            |       |
                                            |_______|
                       ___                  |       |
                      |   |                 |_______|                  ___
                      |   |                 |       |                 |   |
                      |___|                 |_______|                 |___|
                      |   |      ___        |       |        ___      |   |
                      |   |     |   |       |_______|       |   |     |   |
                      |___|     |___|       |       |       |___|     |___|
                      |   |     |   |       |_______|       |   |     |   |
                      |   |     |   |       |       |       |   |     |   |
                      |___|     |___|       |_______|       |___|     |___|
          ___         |   |     |   |       |       |       |   |     |   |         ___
         |   |        |   |     |   |       |_______|       |   |     |   |        |   |
         |___|        |___|     |___|       |       |       |___|     |___|        |___|
         |   |        |   |     |   |       |_______|       |   |     |   |        |   |
         |   |        |   |     |   |       |       |       |   |     |   |        |   |
         |___|        |___|     |___|       |_______|       |___|     |___|        |___|
  _______|   |________|   |_____|   |_______|       |_______|   |_____|   |________|   |_______
 |                                                                                             |
 |:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::|
 |:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::|
  </div>

</div>

<script>
  // Boot Sequence Logic
  const bootScreen = document.getElementById('boot-screen');
  const bootText = document.getElementById('boot-text');
  const lines = [
    "Starting system...",
    "VGA Compatible ROM BIOS",
    "Copyright (C) 1984",
    "640KB OK",
    "",
    "> ABOUT ME data integrity check... OK",
    "> SELECTED PROJECTS active checks... [VALIDATED]",
    "> INTERESTS & EQUIPMENT verification... OK",
    "> (SITE CONTENT LOADING...)",
    "LOAD COMPLETE. User: domdoes"
  ];
  
  let delay = 0;
  // Type out each line with a 200ms delay between them (slightly faster to fit more lines in 2 seconds)
  lines.forEach((line, index) => {
    setTimeout(() => {
      bootText.innerHTML += line + "<br>";
      // If it's the last line, wait 800ms then hide the boot screen
      if (index === lines.length - 1) {
        setTimeout(() => {
          bootScreen.style.display = 'none';
        }, 800); 
      }
    }, delay);
    delay += 200; 
  });
</script>

<h2 id="about-me">C:\> TYPE ABOUT_ME.TXT</h2>
<p>
I'm Dom, a finance professional and designer based in New York City. With over six years of experience as an early finance hire at Robinhood, I specialize in scaling teams, analyzing venture philosophies, and navigating the fintech space.
</p>
<p>
Currently, I'm expanding my creative skill set through coursework in digital arts, design, and photography at Santiago Canyon College. I enjoy blending technical architecture with aesthetic design, whether that involves researching advanced financial options, writing Python automation scripts, or building out vector graphics in Figma.
</p>

<h2 id="projects">C:\> DIR \PROJECTS</h2>
<ul>
  <li>
    <strong>Memento Mori Time-Tracker:</strong> A custom web application that visualizes a 100-year lifespan as a 24-hour clock. Focused on aesthetic UI design and lifespan data visualization.
  </li>
  <li>
    <strong>Automated Social Tracking:</strong> Python-based web scraping tools designed to efficiently track and extract social media data.
  </li>
</ul>

<h2 id="interests">Loading INTERESTS.CFG... [OK]</h2>
<p>
Beyond finance and code, I shoot with premium rangefinder-style digital cameras and optimize health metrics using WHOOP fitness tracking.
</p>
