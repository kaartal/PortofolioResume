<style scoped>
.pageWrapper {
  display: flex;
  justify-content: center; 
  align-items: center;     
  min-height: 100vh;       
  flex-direction: column; 
  padding-top: 40px;
}
.iconLanguage{
  margin-top:8px;
  height:36px;
  width:36px;
  border-radius: 9px;
}

/* TECH PART
.tech-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(110px, 1fr));
  gap: 20px;
  max-width: 600px;
  width: 100%;
}

.tech-item {
  background: rgba(14, 18, 23, 0.8); 
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  padding: 20px 10px;
  text-align: center;
  backdrop-filter: blur(6px); 
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
  transition: all 0.3s ease;
}

.tech-item:hover {
  border-color: #a855f7;
  box-shadow: 0 6px 20px rgba(168, 85, 247, 0.6); 
  transform: translateY(-6px) scale(1.01);
}

.tech-icon {
  width: 45px;
  height: 45px;
  object-fit: contain;
  margin-bottom: 12px;
}

.tech-label {
  margin: 0;
  font-size: 15px;
  font-weight: 600;
  color: #f3e8ff; /*  */

.typingTitle {
  font-family: 'Orbitron', sans-serif;
  font-weight: 700;
  font-size: 4rem;
  color: #a04dff;
  margin-bottom: 2rem;
  white-space: nowrap;
  overflow: hidden;
  border-right: 4px solid #a04dff;
  width: 13ch; 
  animation: typing 3.5s steps(9) forwards, blinkCaret 0.75s step-end infinite;
  user-select: none; 
}


.skillsGrid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
  padding: 2rem;
  margin-top:-40px;
  margin-left:-4px;
}

.skillCard {
  position: relative;
  padding: 1rem;
  background-color: #1b1b1b;
  color: #fff;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  animation: floatUpDown 4s ease-in-out infinite;
  width: 100%;
  max-width: 500px;
  height: 350px;
  margin: auto; 
}

.skillCard:hover {
  animation-play-state: paused;
}

@keyframes floatUpDown {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-6px);
  }
}

.skillCard:hover {
  transform: translateY(-6px);
}

.skillCard h3 {
  font-size: 1.1rem;
  display: flex;
  align-items: center;
  gap: 8px;
  user-select: none;
  font-family: 'Orbitron', sans-serif;
}
.skillText{
  font-size:14px;
  font-family: 'Orbitron', sans-serif;
  font-size: 16px; 
  letter-spacing: 1px; 
  line-height: 1.4; 
}¸
.skillCard p {
  font-size: 0.75rem;
  margin-top: auto;
  font-family: 'Orbitron', sans-serif;
  user-select: none;
}

.windowButtons {
  position: absolute;
  top: 15px;
  left: 20px;
  display: flex;
  gap: 6px;
  z-index:1;
}

.windowButtons .btn {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  display: inline-block;
  box-shadow: 0 0 3px rgba(0, 0, 0, 0.4);
}

.windowButtons .red { background-color: #ff5f56; }
.windowButtons .yellow { background-color: #ffbd2e; }
.windowButtons .green { background-color: #27c93f; }

.icon-html { color: #e34f26; }
.icon-css { color: #2965f1; }
.icon-js { color: #f7df1e; }
.icon-csharp { color: #9b4f96; }
.icon-db { color: #f29111; }
.icon-ubuntu { color: #dd4814; }
.icon-terminal { color: #6c757d; }

.db-icons {
  font-size: 0.6rem;
  color: #ccc;
  margin-left: 4px;
}

.writingCode {
  position: relative;
  font-family: 'Courier New', monospace;
  font-size: 0.8rem;
  color: rgba(255, 255, 255, 0.05);
  line-height: 1.1rem;
  white-space: nowrap;
  overflow: hidden;
  height: 200px;
  user-select: none;
}

.writingCode .line {
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid transparent;
  width: 0;
  animation: typing 2s steps(30, end) forwards;
  margin-bottom: 0.1rem;
  color: rgba(255, 255, 255, 0.05);
  user-select: none;
}

.writingCode .line1 { animation-delay: 0s; }

.writingCode .line2 { animation-delay: 2.5s; }
.writingCode .line3 { animation-delay: 5s; }

.writingCode .line4 { animation-delay: 7.5s; }
.writingCode .line5 { animation-delay: 10s; }


.writingCode .line6 { animation-delay: 12.5s; }
.writingCode .line7 { animation-delay: 15s; }
.writingCode .line8 { animation-delay: 17.5s; }
.writingCode .line9 { animation-delay: 20s; }
.writingCode .line10 { animation-delay: 22.5s; }

@keyframes typing {
  from { width: 0; border-color: transparent; }
  to { border-color: transparent; width: max-content; }
}

@media (max-width: 1024px) {
  .skillsGrid {
    grid-template-columns: repeat(2, 1fr);
  }
  .skillCard {
    max-width: 95%;
    gap:5px;
  }
}

@media (max-width: 768px) {
  .skillsGrid {
    grid-template-columns: 1fr; 
    padding: 2rem;
  }

  .skillCard {
    width: 94% !important;
    max-width: none !important;
    margin: 0; 
  }
}

</style>

<template>
  <div class="pageWrapper">
    <h1 class="typingTitle">my skills</h1>
    <div class="skillsGrid">

      <!-- BACKEND -->
      <div class="skillCard">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <img src="@/assets/c.png" alt=".NET logo" class="iconLanguage" /> 
          <img src="@/assets/c++.png" alt="C# logo" class="iconLanguage" />
          <img src="@/assets/c-sharp.png" alt="C# logo" class="iconLanguage" />
          
        </h3>
        <div class="writingCode">
          <div class="line line1">using System;</div>
          <div class="line line2">public class App {</div>
          <div class="line line3">static void Main() {</div>
          <div class="line line4">Console.WriteLine("Hello .NET");</div>
          <div class="line line5">var version = Environment.Version;</div>
          <div class="line line6">Console.WriteLine(version);</div>
          <div class="line line7">var now = DateTime.Now;</div>
          <div class="line line8">Console.WriteLine(now);</div>
          <div class="line line9">ppDomain.CurrentDomain.UnhandledException += (s, e) => {</div>
          <div class="line line10">Console.WriteLine("Unhandled exception");</div>
          <div class="line line11">};</div>
          <div class="line line12">}</div>
          <div class="line line13">}</div>
        </div>
        <p class="skillText">
          Proficient in backend development using the .NET ecosystem, including C#, ASP.NET Core, and Entity Framework.
        </p>
      </div>

      <!-- FRONTEND -->
      <div class="skillCard">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <img src="@/assets/html.png" alt="HTML logo" class="iconLanguage" />
          <img src="@/assets/css.png" alt="CSS logo" class="iconLanguage" />
          <img src="@/assets/javascript.png" alt="JavaScript logo" class="iconLanguage" />
           
        </h3>
        <div class="writingCode">
          <div class="line line1">&lt;!DOCTYPE html&gt;</div>
          <div class="line line2">&lt;html lang="en"&gt;</div>
          <div class="line line3">&lt;head&gt;</div>
          <div class="line line4">&lt;meta charset="UTF-8"&gt;</div>
          <div class="line line5">&lt;title&gt;Frontend Test&lt;/title&gt;</div>
          <div class="line line6">&lt;/head&gt;</div>
          <div class="line line7">&lt;body&gt;</div>
          <div class="line line8">&lt;h1&gt;Hello Frontend&lt;/h1&gt;</div>
          <div class="line line9">&lt;script&gt;</div>
          <div class="line line10">console.log("Frontend ready");</div>
          <div class="line line11">&lt;/script&gt;</div>
          <div class="line line12">&lt;/body&gt;</div>
          <div class="line line13">&lt;/html&gt;</div>
        </div>
        <p class="skillText">
          Skilled in managing HTML, CSS, and JavaScript for frontend development, and responsive design.
        </p>
      </div>

      <!-- DATABASE -->
      <div class="skillCard">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <img src="@/assets/mysql.png" alt="Microsoft logo" class="iconLanguage" />
          <img src="@/assets/sql.png" alt="Microsoft logo" class="iconLanguage" /> database
        </h3>
        <div class="writingCode">
          <div class="line line1">CREATE TABLE Users (</div>
          <div class="line line2">Id INT PRIMARY KEY AUTO_INCREMENT,</div>
          <div class="line line3">Name VARCHAR(100),</div>
          <div class="line line4">Email VARCHAR(100) UNIQUE</div>
          <div class="line line5">);</div>
          <div class="line line6"></div>
          <div class="line line7">INSERT INTO Users (Name, Email) VALUES ('Halid', 'halid@example.com');</div>
          <div class="line line8">SELECT * FROM Users;</div>
        </div>
        <p class="skillText">
          Passionate about databases, creating efficient schemas, and writing optimized SQL queries for data management.
        </p>
      </div>

      <!-- LINUX -->
      <div class="skillCard">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <img src="@/assets/linux.png" alt="Microsoft logo" class="iconLanguage" />
          <img src="@/assets/ubuntu.png" alt="Microsoft logo" class="iconLanguage" /> 
        </h3>
        <div class="writingCode">
          <div class="line line1">#!/bin/bash</div>
          <div class="line line2">echo "Hello Linux"</div>
          <div class="line line3">a=5</div>
          <div class="line line4">b=10</div>
          <div class="line line5">echo "Sum: $((a + b))"</div>
          <div class="line line6">if [ $a -lt $b ]; then</div>
          <div class="line line7">echo "a is smaller"</div>
          <div class="line line8">else</div>
          <div class="line line9">echo "b is smaller"</div>
          <div class="line line10">fi</div>
        </div>
        <p class="skillText">
  Solid experience in Bash scripting, Linux system administration, and automating tasks on Ubuntu and Debian systems.
</p>
      </div>
      <!-- TECH INFO -->
      <!-- </div>
      <div class="tech-container">
    <div class="tech-item">
      <img src="@/assets/git (2).png" alt="Next.js" class="tech-icon">
      <p class="tech-label">Git</p>
    </div>
    <div class="tech-item">
      <img src="@/assets/terminal.png" alt="React" class="tech-icon">
      <p class="tech-label">Shell</p>
    </div>
    <div class="tech-item">
      <img src="@/assets/.net.png" alt="Remix" class="tech-icon">
      <p class="tech-label">.NET</p>
    </div>
    <div class="tech-item">
      <img src="@/assets/vuejs.png" alt="Redux" class="tech-icon">
      <p class="tech-label">Vue.js</p>
    </div>
  </div> -->
  </div>
    </div>
</template>


