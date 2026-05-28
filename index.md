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
    justify-content: flex-end; 
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
    font-size: 12px; /* Increased by 50% (was 8px) */
    line-height: 1;
    color: var(--text-color);
    opacity: 0.65;
    text-align: left; /* CRITICAL: Stops the browser from shifting individual lines */
    align-self: center; /* Centers the entire block as one solid piece */
    margin: 0 0 -10px 0; 
    padding: 0;
    background: none;
    border: none;
    z-index: 1;
  }
</style>

<div id="boot-screen">
  
  <div id="boot-text-container">
    <div id="boot-text"></div>
    <div style="margin-top: 5px;"><span class="blink-cursor"></span></div>
  </div>

  <pre id="boot-skyline">
                                                       |
                                                       |
                                                       |
                                                       |
                                                       |
                                                      | |
                                                      | |
                                                     _|_|_
                                                    |: : :|
                                                    |: : :|
                                                    |: : :|
                                                   |: : : :|
                                                   |: : : :|
                                                   |: : : :|
                                                  |: : : : :|
                                                  |: : : : :|
                                                  |: : : : :|
                                                 |: : : : : :|
                                                 |: : : : : :|
                                                 |: : : : : :|
                                      ____      |: : : : : : :|      .---.
                                     |::::|     |: : : : : : :|     /:::::\
                                     |::::|     |: : : : : : :|    |:::::::|
                            ____     |::::|    |: : : : : : : :|   |:::::::|     ____
                           |::::|    |::::|    |: : : : : : : :|   |:::::::|    |::::|
                           |::::|    |::::|    |: : : : : : : :|   |:::::::|    |::::|
                  __       |::::|    |::::|   |: : : : : : : : :|  |:::::::|    |::::|       __
                 |::|      |::::|    |::::|   |: : : : : : : : :|  |:::::::|    |::::|      |::|
         __      |::|      |::::|    |::::|   |: : : : : : : : :|  |:::::::|    |::::|      |::|      __
        |::|     |::|      |::::|    |::::|  |: : : : : : : : : :| |:::::::|    |::::|      |::|     |::|
        |::|     |::|      |::::|    |::::|  |: : : : : : : : : :| |:::::::|    |::::|      |::|     |::|
      __|::|_____|::|______|::::|____|::::|__|: : : : : : : : : :|_|:::::::|____|::::|______|::|_____|::|__
     |:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::|
     |:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::|
     =======================================================================================================
     == == == = = = === = = ==== == = = == === = = = ==== == == = = == = = == = ==== === = == = = == === =
       =  = =    = =   =   ==  = = =   = =   =  =     ==  =  = = =   =  =     = = =  == =   = =  =   = =
  </pre>

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
    "LOAD COMPLETE. User: Dom_Doan"
  ];
  
  let delay = 0;
  // Type out each line with a 200ms delay between them 
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
I'm Dom, a finance nerd based in New York City. I was the first finance hire at Robinhood and spent 6+ years helping scale the company from early stage growth to IPO readiness. In that time, I scaled finance teams across Corporate Finance, Product Finance, Infrastructure & Engineering, Investor Relations, and Growth & Marketing.
</p>
<p>
Now, I’m looking to return to startup life. I miss it, the ambition, the figuring it out, and the people it attracts. I want to work alongside people who will look back at what we built together and say: we took risks, we tried boldly, we failed honestly, and we tried again. I want to help build the future we all deserve.
</p>

<h2 id="projects">C:\> DIR \PROJECTS</h2>
<ul>
  <li>
    <strong><a href="https://domdoes.github.io/life-clock/">Memento Mori Time-Tracker</a>:</strong> A custom web application that visualizes a 100-year lifespan as a 24-hour clock. Focused on aesthetic UI design and lifespan data visualization.
  </li>
  <li>
    <strong>Automated Social Tracking:</strong> Python-based web scraping tools designed to track and extract data to get updates from some of my favorite NYC places (not a resy bot lol).
  </li>
</ul>

<h2 id="interests">C:\> TYPE INTERESTS.CFG</h2>
<p>
Beyond finance and code, I'm taking some language and photography classes. But I'm a true finance nerd and have visited 12 different central banks. Hot take: I think the GOAT of central banks is the Federal Reserve. 
</p>

<h2 id="philosophy">C:\> TYPE PHILOSOPHY.SYS</h2>
<ul>
  <li>Character is destiny</li>
  <li>My friends have always been the best of me</li>
  <li>Life is easier with all my social media notifications turned off</li>
</ul>

</p>
