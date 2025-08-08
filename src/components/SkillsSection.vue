<template>
  <div class="page-wrapper">
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
          <div class="line line1">public class App &#123;</div>
          <div class="line line2">  static void Main() &#123;</div>
          <div class="line line3">    Console.WriteLine("Hello .NET");</div>
          <div class="line line4">    var version = Environment.Version;</div>
          <div class="line line5">    Console.WriteLine(version);</div>
          <div class="line line6">    var now = DateTime.Now;</div>
          <div class="line line7">    Console.WriteLine(now);</div>
          <div class="line line8">    AppDomain.CurrentDomain.UnhandledException += (s, e) => &#123;</div>
          <div class="line line9">      Console.WriteLine("Unhandled exception");</div>
          <div class="line line10">    &#125;;</div>
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
          <div class="line line1">#!/bin/bash</div>
          <div class="line line2">echo "Linux server started"</div>
          <div class="line line3">sudo apt update</div>
          <div class="line line4">sudo systemctl start nginx</div>
          <div class="line line5">df -h</div>
          <div class="line line6">uptime</div>
          <div class="line line7">whoami</div>
          <div class="line line8">ps aux | grep nginx</div>
          <div class="line line9">journalctl -xe</div>
          <div class="line line10">echo "Ready."</div>
        </div>
        <p>
          Skilled in managing Linux-based systems, primarily Ubuntu and Debian distributions. Comfortable with shell scripting.
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
          <div class="line line1">function binarySearch(arr, x) &#123;</div>
          <div class="line line2">  let left = 0, right = arr.length - 1;</div>
          <div class="line line3">  while (left &lt;= right) &#123;</div>
          <div class="line line4">    const mid = Math.floor((left + right) / 2);</div>
          <div class="line line5">    if (arr[mid] === x) return mid;</div>
          <div class="line line6">    else if (arr[mid] &lt; x) left = mid + 1;</div>
          <div class="line line7">    else right = mid - 1;</div>
          <div class="line line8">  &#125;</div>
          <div class="line line9">  return -1;</div>
          <div class="line line10">&#125;</div>
        </div>
        <p>
          Passionate about data structures and algorithms. I apply algorithmic thinking to solve complex problems efficiently.
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
          <div class="line line1">#include &lt;iostream&gt;</div>
          <div class="line line2">int main() &#123;</div>
          <div class="line line3">  std::cout &lt;&lt; "Hello C++";</div>
          <div class="line line4">  int a = 5, b = 10;</div>
          <div class="line line5">  std::cout &lt;&lt; a + b &lt;&lt; std::endl;</div>
          <div class="line line6">  if (a &lt; b) &#123;</div>
          <div class="line line7">    std::cout &lt;&lt; "a is smaller";</div>
          <div class="line line8">  &#125; else &#123;</div>
          <div class="line line9">    std::cout &lt;&lt; "b is smaller";</div>
          <div class="line line10">  &#125;</div>
        </div>
        <p>
          Solid experience in C++ for systems-level and performance-critical programming. Familiar with object-oriented design,
          memory management.
        </p>
      </div>

    </div>
  </div>
</template>

<!-- Dodaj u index.html ili head dijela projekta -->
<!--
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css"/>
-->

<style scoped>
.page-wrapper {
  display: flex;
  justify-content: center; 
  align-items: center;     
  min-height: 100vh;       
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
  height: 300px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 500px;
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
  z-index: 2;
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

/* Ikone boje */
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
}
</style>
