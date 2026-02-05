<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Trek With Me?</title>

<style>
* { box-sizing: border-box; }

body {
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(180deg,#87ceeb,#fceabb);
    font-family:'Segoe UI',sans-serif;
    overflow:hidden;
}

/* floating mountains emoji */
.mountain {
    position:absolute;
    bottom:-40px;
    font-size:28px;
    animation:floatUp 7s linear infinite;
}

@keyframes floatUp {
    0% { transform:translateY(0); opacity:0; }
    20% { opacity:1; }
    100% { transform:translateY(-110vh); opacity:0; }
}

.container {
    background:white;
    padding:50px 70px;
    border-radius:25px;
    text-align:center;
    box-shadow:0 25px 60px rgba(0,0,0,0.25);
}

h1 {
    color:#2e7d32;
    font-size:34px;
}

p {
    font-size:18px;
    color:#555;
    margin-bottom:35px;
}

.buttons {
    position:relative;
    height:90px;
}

button {
    padding:14px 30px;
    font-size:18px;
    border:none;
    border-radius:30px;
    cursor:pointer;
}

#yesBtn {
    background:#2e7d32;
    color:white;
    box-shadow:0 8px 20px rgba(46,125,50,0.4);
}

#noBtn {
    background:#eee;
    position:absolute;
    left:150px;
}

.message {
    display:none;
    margin-top:25px;
    font-size:24px;
    color:#2e7d32;
}
</style>
</head>

<body>

<div class="container">
    <h1>Will you go on a Himalayan trek with me? 🏔️</h1>
    <p>
        Imagine sunrise in the mountains, cold air, hot chai,<br>
        and us watching the clouds together…
    </p>

    <div class="buttons">
        <button id="yesBtn">Yes! Let's go 🥾</button>
        <button id="noBtn">No 😶</button>
    </div>

    <div class="message" id="finalMessage">
        Yayyy! Adventure partner confirmed 💚🏔️
    </div>
</div>

<script>
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");
const msg = document.getElementById("finalMessage");

// Runaway NO button 😆
noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * (window.innerWidth - 120);
    const y = Math.random() * (window.innerHeight - 80);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

// YES clicked
yesBtn.addEventListener("click", () => {
    msg.style.display = "block";
});

// floating mountains animation
function createMountain() {
    const m = document.createElement("div");
    m.classList.add("mountain");
    m.innerText = "🏔️";
    m.style.left = Math.random() * 100 + "vw";
    m.style.animationDuration = (5 + Math.random() * 3) + "s";
    document.body.appendChild(m);
    setTimeout(() => m.remove(), 7000);
}
setInterval(createMountain, 500);
</script>

</body>
</html>
