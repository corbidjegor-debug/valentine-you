#   
  
<!DOCTYPE html>  
<html lang="ru">  
<head>  
<meta charset="UTF-8">  
<title>Для Наташи ❤️</title>  
  
<style>  
body {  
  margin: 0;  
  height: 100vh;  
  background: url('photo.jpg') center/cover no-repeat;  
  display: flex;  
  justify-content: center;  
  align-items: center;  
  font-family: Arial, sans-serif;  
  overflow: hidden;  
  position: relative;  
}  
  
.overlay {  
  position: absolute;  
  width: 100%;  
  height: 100%;  
  background: rgba(0,0,0,0.55);  
  backdrop-filter: blur(3px);  
}  
  
.card {  
  position: relative;  
  text-align: center;  
  color: white;  
  padding: 40px;  
  border-radius: 20px;  
  animation: fadeIn 1.5s ease;  
  z-index: 2;  
}  
  
h1 {  
  font-size: 38px;  
  margin-bottom: 20px;  
}  
  
button {  
  padding: 12px 25px;  
  font-size: 18px;  
  border: none;  
  border-radius: 25px;  
  cursor: pointer;  
  margin: 10px;  
  transition: 0.3s;  
}  
  
#yes {  
  background: #ff4b7d;  
  color: white;  
}  
  
#no {  
  background: white;  
  color: #ff4b7d;  
  position: absolute;  
}  
  
.heart {  
  position: absolute;  
  color: #ff4b7d;  
  font-size: 20px;  
  animation: fall linear forwards;  
  z-index: 1;  
}  
  
@keyframes fall {  
  to {  
    transform: translateY(110vh);  
    opacity: 0;  
  }  
}  
  
@keyframes fadeIn {  
  from {opacity: 0; transform: translateY(20px);}  
  to {opacity: 1; transform: translateY(0);}  
}  
</style>  
</head>  
  
<body>  
  
<div class="overlay"></div>  
  
<div class="card">  
  <h1>Наташа, будешь моей валентинкой? ❤️</h1>  
  <button id="yes">Да</button>  
  <button id="no">Нет</button>  
</div>  
  
<script>  
// убегающая кнопка  
const noBtn = document.getElementById("no");  
  
noBtn.addEventListener("mouseover", () => {  
  const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);  
  const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);  
  noBtn.style.left = x + "px";  
  noBtn.style.top = y + "px";  
});  
  
// действие кнопки "Да"  
document.getElementById("yes").addEventListener("click", () => {  
  document.body.innerHTML = `  
    <div style="  
      display:flex;  
      height:100vh;  
      justify-content:center;  
      align-items:center;  
      background:url('photo.jpg') center/cover no-repeat;  
      position:relative;  
      color:white;  
      font-size:40px;  
      font-family:Arial;  
      text-align:center;  
    ">  
      <div style="  
        background:rgba(0,0,0,0.6);  
        padding:40px;  
        border-radius:20px;  
      ">  
        Наташа, ты делаешь мою жизнь теплее ❤️  
      </div>  
    </div>  
  `;  
});  
  
// падающие сердечки  
function createHeart() {  
  const heart = document.createElement("div");  
  heart.classList.add("heart");  
  heart.innerText = "❤️";  
  heart.style.left = Math.random() * 100 + "vw";  
  heart.style.animationDuration = (3 + Math.random() * 4) + "s";  
  heart.style.fontSize = (16 + Math.random() * 20) + "px";  
  document.body.appendChild(heart);  
  
  setTimeout(() => {  
    heart.remove();  
  }, 7000);  
}  
  
setInterval(createHeart, 300);  
</script>  
  
</body>  
</html>  
