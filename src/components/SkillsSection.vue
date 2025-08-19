<template>
  <div class="page-wrapper">
    <!-- Naslov sa animacijom kucanja -->
    <h1 class="typing-title">my skills</h1>

    <div class="skillsGrid">

      <!-- BACKEND -->
      <div class="skill-card">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <i class="fab fa-microsoft icon-csharp"></i> backend
        </h3>
        <div class="typing-code">
          <div class="line line1">using System;</div>
          <div class="line line2">public class App {</div>
          <div class="line line3">    static void Main() {</div>
          <div class="line line4">        Console.WriteLine("Hello .NET");</div>
          <div class="line line5">        var version = Environment.Version;</div>
          <div class="line line6">        Console.WriteLine(version);</div>
          <div class="line line7">        var now = DateTime.Now;</div>
          <div class="line line8">        Console.WriteLine(now);</div>
          <div class="line line9">        AppDomain.CurrentDomain.UnhandledException += (s, e) => {</div>
          <div class="line line10">            Console.WriteLine("Unhandled exception");</div>
          <div class="line line11">        };</div>
          <div class="line line12">    }</div>
          <div class="line line13">}</div>
        </div>
        <p>
          Proficient in backend development using the .NET ecosystem, including C#, ASP.NET Core, and Entity Framework.
        </p>
      </div>

      <!-- FRONTEND -->
      <div class="skill-card">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <i class="fab fa-html5 icon-html"></i>
          <i class="fab fa-css3-alt icon-css"></i>
          <i class="fab fa-js icon-js"></i> frontend
        </h3>
        <div class="typing-code">
          <div class="line line1">&lt;!DOCTYPE html&gt;</div>
          <div class="line line2">&lt;html lang="en"&gt;</div>
          <div class="line line3">&lt;head&gt;</div>
          <div class="line line4">    &lt;meta charset="UTF-8"&gt;</div>
          <div class="line line5">    &lt;title&gt;Frontend Test&lt;/title&gt;</div>
          <div class="line line6">&lt;/head&gt;</div>
          <div class="line line7">&lt;body&gt;</div>
          <div class="line line8">    &lt;h1&gt;Hello Frontend&lt;/h1&gt;</div>
          <div class="line line9">&lt;script&gt;</div>
          <div class="line line10">    console.log("Frontend ready");</div>
          <div class="line line11">&lt;/script&gt;</div>
          <div class="line line12">&lt;/body&gt;</div>
          <div class="line line13">&lt;/html&gt;</div>
        </div>
        <p>
          Skilled in managing HTML, CSS, and JavaScript for frontend development, including dynamic DOM manipulation and responsive design.
        </p>
      </div>

      <!-- DATABASE -->
      <div class="skill-card">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <i class="fas fa-database icon-db"></i>
          <span class="db-icons">MySQL | SQL</span> database
        </h3>
        <div class="typing-code">
          <div class="line line1">CREATE TABLE Users (</div>
          <div class="line line2">    Id INT PRIMARY KEY AUTO_INCREMENT,</div>
          <div class="line line3">    Name VARCHAR(100),</div>
          <div class="line line4">    Email VARCHAR(100) UNIQUE</div>
          <div class="line line5">);</div>
          <div class="line line6"></div>
          <div class="line line7">INSERT INTO Users (Name, Email) VALUES ('Halid', 'halid@example.com');</div>
          <div class="line line8">SELECT * FROM Users;</div>
        </div>
        <p>
          Passionate about databases, creating efficient schemas, and writing optimized SQL queries for data management.
        </p>
      </div>

      <!-- LINUX -->
      <div class="skill-card">
        <div class="windowButtons">
          <span class="btn red"></span>
          <span class="btn yellow"></span>
          <span class="btn green"></span>
        </div>
        <h3>
          <i class="fab fa-ubuntu icon-ubuntu"></i>
          <i class="fas fa-terminal icon-terminal"></i> linux
        </h3>
        <div class="typing-code">
          <div class="line line1">#!/bin/bash</div>
          <div class="line line2">echo "Hello Linux"</div>
          <div class="line line3">a=5</div>
          <div class="line line4">b=10</div>
          <div class="line line5">echo "Sum: $((a + b))"</div>
          <div class="line line6">if [ $a -lt $b ]; then</div>
          <div class="line line7">    echo "a is smaller"</div>
          <div class="line line8">else</div>
          <div class="line line9">    echo "b is smaller"</div>
          <div class="line line10">fi</div>
        </div>
        <p>
          Solid experience in Bash scripting, Linux system administration, and automating tasks on Ubuntu and Debian systems.
        </p>
      </div>

    </div>
  </div>
</template>


<style scoped>
.page-wrapper {
  display: flex;
  justify-content: center; 
  align-items: center;     
  min-height: 100vh;       
  flex-direction: column; 
}

.typing-title {
  font-family: 'Orbitron', sans-serif;
  font-weight: 700;
  font-size: 3rem;
  color: #a04dff;
  margin-bottom: 2rem;
  white-space: nowrap;
  overflow: hidden;
  border-right: 4px solid #a04dff;
  width: 13ch; 
  animation: typing 3.5s steps(9) forwards, blinkCaret 0.75s step-end infinite;
}




.skillsGrid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
  padding: 2rem;
}

.skill-card {
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
  width: 500px;
  animation: floatUpDown 4s ease-in-out infinite;
   width: 100%;
  max-width: 500px;
  min-height: 300px;
}

.skill-card:hover {
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

.skill-card:hover {
  transform: translateY(-6px);
}

.skill-card h3 {
  font-size: 1.1rem;
  display: flex;
  align-items: center;
  gap: 8px;
}

.skill-card p {
  font-size: 0.75rem;
  margin-top: auto;
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
  width: 10px;
  height: 10px;
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
  font-size: 0.8rem;
  color: #ccc;
  margin-left: 4px;
}

.typing-code {
  position: relative;
  font-family: 'Courier New', monospace;
  font-size: 0.7rem;
  color: rgba(255, 255, 255, 0.05);
  line-height: 1.1rem;
  white-space: nowrap;
  overflow: hidden;
  height: 200px;
}

.typing-code .line {
  overflow: hidden;
  white-space: nowrap;
  border-right: 2px solid transparent;
  width: 0;
  animation: typing 2s steps(30, end) forwards;
  margin-bottom: 0.1rem;
  color: rgba(255, 255, 255, 0.05);
}

.typing-code .line1 { animation-delay: 0s; }
.typing-code .line2 { animation-delay: 2.5s; }
.typing-code .line3 { animation-delay: 5s; }
.typing-code .line4 { animation-delay: 7.5s; }
.typing-code .line5 { animation-delay: 10s; }
.typing-code .line6 { animation-delay: 12.5s; }
.typing-code .line7 { animation-delay: 15s; }
.typing-code .line8 { animation-delay: 17.5s; }
.typing-code .line9 { animation-delay: 20s; }
.typing-code .line10 { animation-delay: 22.5s; }

@keyframes typing {
  from { width: 0; border-color: transparent; }
  to { border-color: transparent; width: max-content; }
}

@media (max-width: 768px) {
  .skillsGrid {
    grid-template-columns: repeat(1, 1fr);
    padding: 2rem;
  }

  .skill-card {
    width: 95%;
  }
}

@media (max-width: 1024px) {
  .skillsGrid {
    grid-template-columns: repeat(2, 1fr);
    padding: 2rem;
  }

  .skill-card {
    width: 94%;
  }
}
</style>
