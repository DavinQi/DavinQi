## Hi ~

<div align="center">
  <h1>👋 Hi, I'm DavinQi</h1>
  <p>Full-Stack Developer | love code | love ai </p>
  <p>☕ 主力 Java 后端开发者 | 🎨 热爱编程 | 🤖 痴迷 AI 编程 的开发老兵</h3>
</div>

---


### 🧑‍💻 About Me
- 🔧 **Primary Language**: Java (Backend, Microservices, Concurrent Programming)
- 🎨 **Interests**: Frontend Development & AI Programming
- 🤖 **Passion**: AI development, LLM applications and AIGC
- 💡 Enjoy combining backend logic, frontend interaction and AI capabilities
- ✨ Belief: Code = Creativity + Technical Aesthetics
  
### 🧑‍💻 关于我
- 🔧 **主力开发语言**：Java（后端、微服务、并发编程）
- 🎨 **兴趣方向**：前端开发 + AI编程 
- 🤖 **狂热爱好**：AI 编程、大模型应用、AIGC开发
- 💡 喜欢 **后端逻辑 + 前端交互 + AI能力**  
- ✨ 相信：代码 = 创造力 + 技术美学

---

### 🚀 技术栈
<div align="center">
<img src="https://img.shields.io/badge/Java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E">
<img src="https://img.shields.io/badge/Vue.js-%234FC08D.svg?style=for-the-badge&logo=vuedotjs&logoColor=white">
<img src="https://img.shields.io/badge/AI%20Programming-%230089DE.svg?style=for-the-badge&logo=tensorflow&logoColor=white">
<img src="https://img.shields.io/badge/Python-%2314354C.svg?style=for-the-badge&logo=python&logoColor=white">
</div>

---

# 🎮 JS 小游戏：点击收集代码球（GitHub 主页直接运行）
<div align="center">
<canvas id="gameCanvas" width="350" height="300" style="border:2px solid #fff; background:#111; border-radius:10px;"></canvas>
<p>🎮 点击屏幕收集「Java / 前端 / AI」代码球</p>
</div>

<script>
let canvas = document.getElementById('gameCanvas');
let ctx = canvas.getContext('2d');
let score = 0;
let balls = [];

// 代码球类型
const types = [
  { text:"☕ Java", color:"#f89820" },
  { text:"🎨 前端", color:"#5ed9f7" },
  { text:"🤖 AI", color:"#ffffff" }
];

// 生成随机球
function spawnBall() {
  let type = types[Math.floor(Math.random()*types.length)];
  balls.push({
    x: Math.random() * (canvas.width-30) + 15,
    y: Math.random() * (canvas.height-30) + 15,
    r: 18,
    color: type.color,
    text: type.text
  });
}

// 点击收集
canvas.onclick = (e) => {
  let rect = canvas.getBoundingClientRect();
  let x = e.clientX - rect.left;
  let y = e.clientY - rect.top;
  for(let i=balls.length-1; i>=0; i--){
    let b = balls[i];
    let d = Math.hypot(x-b.x, y-b.y);
    if(d < b.r){
      balls.splice(i,1);
      score++;
    }
  }
}

// 游戏循环
function loop() {
  ctx.fillStyle = "#111";
  ctx.fillRect(0,0,canvas.width,canvas.height);
  if(Math.random()<0.03) spawnBall();
  balls.forEach(b => {
    ctx.beginPath();
    ctx.arc(b.x,b.y,b.r,0,Math.PI*2);
    ctx.fillStyle = b.color;
    ctx.fill();
    ctx.fillStyle = "#000";
    ctx.font = "12px Arial";
    ctx.fillText(b.text, b.x-12, b.y+4);
  });
  ctx.fillStyle = "#fff";
  ctx.font = "18px Arial";
  ctx.fillText("得分：" + score, 10, 30);
  requestAnimationFrame(loop);
}
loop();
</script>

---

### 💬 联系方式
- 📧 Email：你的邮箱
- 🌐 GitHub：github.com/你的用户名
