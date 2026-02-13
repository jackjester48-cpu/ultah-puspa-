index.html
foto1.jpg
foto2.jpg
foto3.jpg
foto4.jpg
foto5.jpg
somebodymp3

<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Untuk Puspa 🤍</title>

<style>
body {
  margin: 0;
  padding: 0;
  overflow: hidden;
  font-family: 'Segoe UI', sans-serif;
  background: black;
  color: white;
}

.slideshow {
  position: fixed;
  width: 100%;
  height: 100%;
  z-index: -1;
}

.slideshow img {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  animation: fade 25s infinite;
}

.slideshow img:nth-child(1) { animation-delay: 0s; }
.slideshow img:nth-child(2) { animation-delay: 5s; }
.slideshow img:nth-child(3) { animation-delay: 10s; }
.slideshow img:nth-child(4) { animation-delay: 15s; }
.slideshow img:nth-child(5) { animation-delay: 20s; }

@keyframes fade {
  0% {opacity: 0;}
  5% {opacity: 1;}
  20% {opacity: 1;}
  25% {opacity: 0;}
  100% {opacity: 0;}
}

.overlay {
  position: absolute;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.4);
}

.content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

button {
  padding: 12px 25px;
  border: none;
  border-radius: 30px;
  font-size: 16px;
  cursor: pointer;
  background: white;
  color: #ff6f91;
  margin-top: 15px;
}

#message {
  display: none;
  margin-top: 20px;
  font-size: 18px;
  line-height: 1.6;
  animation: fadeIn 2s ease forwards;
}

@keyframes fadeIn {
  from {opacity: 0;}
  to {opacity: 1;}
}

.heart {
  position: absolute;
  color: pink;
  font-size: 20px;
  animation: fall linear infinite;
}

@keyframes fall {
  0% { transform: translateY(-10vh); opacity: 1; }
  100% { transform: translateY(110vh); opacity: 0; }
}
</style>
</head>

<body>

<audio id="bgmusic" loop>
  <source src="somebody.mp3" type="audio/mpeg">
</audio>

<div class="slideshow">
  <img src="foto1.jpg">
  <img src="foto2.jpg">
  <img src="foto3.jpg">
  <img src="foto4.jpg">
  <img src="foto5.jpg">
</div>

<div class="overlay"></div>

<div class="content">
  <h2>Hai Puspa 🤍</h2>
  <button onclick="startExperience()">Klik dari Pangeranmu 👑</button>

  <div id="message">
    <p>
      Selamat ulang tahun 🤍  
      14 Februari... hari dimana lahir seseorang yang bikin aku bersyukur banget.
    </p>
    <p>
      Terima kasih sudah hadir di hidup aku.
      Kamu itu cukup, bahkan lebih dari cukup.
    </p>
    <p>
      Kalau dunia lagi berat,
      pangeranmu selalu ada di sini 👑✨
    </p>
    <p><b>Happy Birthday 🤍</b></p>
  </div>
</div>

<script>
function startExperience() {
  document.getElementById("message").style.display = "block";
  document.getElementById("bgmusic").play();
}

// animasi hati
function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.innerHTML = "❤";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
  document.body.appendChild(heart);

  setTimeout(() => {
    heart.remove();
  }, 5000);
}

setInterval(createHeart, 400);
</script>

</body>
</html>
