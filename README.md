<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For You 💜</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', sans-serif;
}

body {
  height: 100vh;
  background: linear-gradient(135deg, #2a0a3d, #120018);
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  color: white;
}

/* Floating brown hearts */
.heart {
  position: absolute;
  bottom: -40px;
  font-size: 20px;
  opacity: 0.6;
  animation: floatUp linear infinite;
}

@keyframes floatUp {
  0% { transform: translateY(0); opacity: 0; }
  10% { opacity: 0.6; }
  100% { transform: translateY(-110vh); opacity: 0; }
}

/* Card */
.card {
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(16px);
  border-radius: 22px;
  padding: 50px 60px;
  text-align: center;
  box-shadow: 0 0 35px rgba(186, 104, 200, 0.25);
  max-width: 500px;
  position: absolute;
  transition: 0.6s ease;
}

.hidden {
  opacity: 0;
  transform: scale(0.9);
  pointer-events: none;
}

/* Buttons */
.buttons {
  margin-top: 30px;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 12px;
}

button {
  border: none;
  padding: 10px 22px;
  border-radius: 25px;
  cursor: pointer;
  font-size: 15px;
  transition: 0.25s ease;
}

/* YES */
.yes {
  background: linear-gradient(135deg, #7b1fa2, #ba68c8);
  color: white;
  box-shadow: 0 0 15px rgba(186,104,200,0.4);
}

.yes:hover { transform: scale(1.05); }

/* NO */
.no {
  background: rgba(255,255,255,0.15);
  color: #eee;
}

.no:hover { transform: scale(0.95); }

/* Message */
.message {
  margin-top: 18px;
  font-size: 16px;
  color: #ce93d8;
  min-height: 24px;
}

/* Vanish animation */
.vanish {
  animation: disappear 0.35s ease forwards;
}

@keyframes disappear {
  to {
    opacity: 0;
    transform: scale(0.3);
  }
}

/* Letter */
.letter {
  text-align: left;
  line-height: 1.6;
  font-size: 16px;
  color: #f3e5f5;
  margin-top: 20px;
}

.signature {
  margin-top: 25px;
  text-align: right;
  color: #ce93d8;
  font-style: italic;
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div class="card" id="page1">
  <h1>Hii, Isabella Chloe V. Binarao💜</h1>
  <p>I wanted to ask you something gently…</p>
  <h2 style="margin-top:15px;">
    Will you Marry mee? 💜
  </h2>

  <div class="buttons">
    <!-- YES x2 -->
    <button class="yes" onclick="showLetter()">Yes 💜</button>
    <button class="yes" onclick="showLetter()">YESS NA YES, YIZZZ GALINGGG, YESS THE BEST, YESS AS IN OOOO😊</button>

    <!-- NO x3 -->
    <button class="no" onclick="answerNo(this)">No 😢</button>
    <button class="no" onclick="answerNo(this)">AYAW KO NGA 🤔</button>
    <button class="no" onclick="answerNo(this)">IHHHHH😌</button>
  </div>

  <div class="message" id="response"></div>
</div>

<!-- PAGE 2 -->
<div class="card hidden" id="page2">
  <h1>💌 A Letter For You</h1>

  <div class="letter">
    <p>Maybe this started as something simple…</p>
    <p>But somewhere along the way, you became truly special to me.</p>
    <p>Your smile, your presence, your energy, they stay with me.</p>
    <p>If you’re willing, I’d love to create beautiful memories with you.</p>
    <p>No pressure. Just honesty from my heart, ILOVEEEUUUSOMUCHH 💜</p>

    <div class="signature">
      — PEACHH 💜
    </div>
  </div>
</div>

<script>
const page1 = document.getElementById("page1");
const page2 = document.getElementById("page2");
const response = document.getElementById("response");

/* Floating hearts */
function createHeart() {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "🤎";

  heart.style.left = Math.random() * 100 + "vw";
  heart.style.animationDuration = (4 + Math.random()*4) + "s";
  heart.style.fontSize = (16 + Math.random()*18) + "px";

  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 8000);
}
setInterval(createHeart, 400);

/* YES → Letter */
function showLetter() {
  page1.classList.add("hidden");
  page2.classList.remove("hidden");
}

/* NO → Vanish */
function answerNo(btn) {
  const lines = [
    "SUNTUKAN? ",
    "talaga ba? 😌",
    "Bat ayaww mooo?"

  ];

  response.innerHTML = lines[Math.floor(Math.random() * lines.length)];

  btn.classList.add("vanish");

  setTimeout(() => {
    btn.style.display = "none";
  }, 350);
}
</script>

</body>
</html>
