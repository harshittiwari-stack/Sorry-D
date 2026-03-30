<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>I'm Sorry ❤️</title>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', sans-serif;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  height: 100vh;
  overflow: hidden;
}

/* Floating hearts */
.heart {
  position: absolute;
  color: rgba(255,255,255,0.7);
  font-size: 20px;
  animation: float 6s linear infinite;
}

@keyframes float {
  0% { transform: translateY(100vh); opacity: 0; }
  50% { opacity: 1; }
  100% { transform: translateY(-10vh); opacity: 0; }
}

.container {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: white;
  padding: 40px;
  border-radius: 25px;
  text-align: center;
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

h1 {
  color: #ff4b5c;
  margin-bottom: 20px;
}

p {
  font-size: 18px;
  color: #555;
}

button {
  padding: 12px 25px;
  font-size: 18px;
  border: none;
  border-radius: 12px;
  cursor: pointer;
  margin: 15px;
  transition: 0.3s;
}

#yesBtn {
  background-color: #28a745;
  color: white;
}

#noBtn {
  background-color: #dc3545;
  color: white;
  position: absolute;
}

/* Success message */
#loveMsg {
  display: none;
  font-size: 22px;
  color: #ff2e63;
  margin-top: 20px;
}
</style>
</head>

<body>

<!-- Background music -->
<audio autoplay loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
</audio>

<div class="container">
  <h1>Will you accept my sorry? 🥺❤️</h1>
  <p>I know I made a mistake... but you mean everything to me 💔</p>

  <button id="yesBtn" onclick="acceptLove()">Yes ❤️</button>
  <button id="noBtn">No ❌</button>

  <div id="loveMsg">
    Thank you for forgiving me 😭❤️<br>
    I promise I’ll never hurt you again 💞<br>
    You are my everything 🌍❤️
  </div>
</div>

<script>
const noBtn = document.getElementById("noBtn");

noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * (window.innerWidth - 100);
  const y = Math.random() * (window.innerHeight - 100);
  noBtn.style.left = x + "px";
  noBtn.style.top = y + "px";
});

// YES click
function acceptLove() {
  document.getElementById("loveMsg").style.display = "block";
  launchHearts();
}

// Floating hearts generator
function launchHearts() {
  for (let i = 0; i < 30; i++) {
    let heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = (Math.random() * 20 + 15) + "px";
    heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 6000);
  }
}
</script>

</body>
</html>
