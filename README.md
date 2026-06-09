<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Gio Ahmed Hasan</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
background:#020617;
overflow-x:hidden;
color:white;
}

/* ================= CANVAS BACKGROUND ================= */
canvas{
position:fixed;
top:0;
left:0;
z-index:0;
}

/* ================= APP ================= */
.app{
position:relative;
z-index:2;
min-height:100vh;
display:flex;
flex-direction:column;
align-items:center;
padding:20px;
}

/* PROFILE */
.profile{
width:90px;
height:90px;
border-radius:50%;
margin-top:10px;
border:2px solid #38bdf8;
box-shadow:0 0 20px rgba(56,189,248,.4);
}

/* 🔥 FIRE NAME */
.title{
font-size:24px;
font-weight:bold;
margin-top:10px;
min-height:35px;
background:linear-gradient(90deg,#ff4500,#ffae00,#ff0000,#38bdf8);
background-size:300% 300%;
-webkit-background-clip:text;
-webkit-text-fill-color:transparent;
animation:fireGlow 1.5s infinite alternate;
text-shadow:0 0 20px rgba(255,100,0,.5);
}

@keyframes fireGlow{
0%{
transform:scale(1);
text-shadow:0 0 5px #38bdf8;
}

50%{
transform:scale(1.08);
text-shadow:0 0 20px #ff4500, 0 0 30px #ff0000;
}

100%{
transform:scale(1.1);
text-shadow:0 0 10px #ff6a00, 0 0 25px #ff0000;
}
}

/* GRID */
.grid{
display:grid;
grid-template-columns:repeat(2,1fr);
gap:12px;
width:100%;
max-width:520px;
margin-top:20px;
}

@media(max-width:520px){
.grid{grid-template-columns:1fr;}
}

/* CARD */
.card{
background:rgba(255,255,255,.06);
backdrop-filter:blur(15px);
border:1px solid rgba(255,255,255,.1);
border-radius:15px;
padding:12px;
cursor:pointer;
transition:.3s;
position:relative;
}

.card:hover{
transform:translateY(-5px);
border-color:#38bdf8;
box-shadow:0 0 20px rgba(56,189,248,.25);
}

.icon{
font-size:20px;
}

.card-title{
font-size:14px;
margin-top:5px;
}

/* SUBMENU */
.submenu{
max-height:0;
overflow:hidden;
transition:.4s ease;
margin-top:8px;
opacity:0;
}

.card.active .submenu{
opacity:1;
}

.submenu a{
display:block;
padding:7px;
margin:5px 0;
border-radius:10px;
background:rgba(255,255,255,.08);
text-decoration:none;
color:white;
font-size:12px;
}

.submenu a:hover{
background:#38bdf8;
color:black;
}
</style>
</head>

<body>

<!-- PARTICLES -->
<canvas id="canvas"></canvas>

<div class="app">

<img class="profile" src="https://i.postimg.cc/R0ch4s5D/Snapchat-1619378186.jpg">

<div class="title">
<span id="typing"></span>
</div>

<div class="grid">

<div class="card" onclick="toggle(this)">
<div class="icon">🪨</div>
<div class="card-title">حفريات</div>
<div class="submenu">
<a href="https://koka8721416-coder.github.io/Exam/">اختياري + صح وغلط</a>
<a href="https://koka8721416-coder.github.io/gh/">الشيت والتكليف</a>
<a href="https://koka8721416-coder.github.io/cr7/">استراكودا</a>
</div>
</div>

<div class="card" onclick="toggle(this)">
<div class="icon">🐛</div>
<div class="card-title">حشرات</div>
<div class="submenu">
<a href="https://koka8721416-coder.github.io/Ahmed-Hasan/">بنك الحشرات</a>
<a href="#">امتحانات</a>
<a href="#">الشيتات</a>
</div>
</div>

<div class="card" onclick="toggle(this)">
<div class="icon">🌿</div>
<div class="card-title">بيئة نباتية</div>
<div class="submenu">
<a href="https://koka8721416-coder.github.io/Gioo-koka5/">امتحان سابق</a>
<a href="https://koka8721416-coder.github.io/Gio-koka/">بنك الأسئلة</a>
<a href="https://koka8721416-coder.github.io/Gioo-Koka2/">امتحانات شاملة</a>
</div>
</div>

<div class="card" onclick="toggle(this)">
<div class="icon">🌱</div>
<div class="card-title">فسيولوجي نبات</div>
<div class="submenu">
<a href="https://koka8721416-coder.github.io/physiology-/">بنك الأسئلة</a>
<a href="https://koka8721416-coder.github.io/Exam-physiology-/">امتحان سابق</a>
</div>
</div>

</div>
</div>

<script>

/* TOGGLE */
function toggle(card){
document.querySelectorAll(".card").forEach(c=>{
if(c!==card){
c.classList.remove("active");
c.querySelector(".submenu").style.maxHeight=null;
}
});

let menu=card.querySelector(".submenu");
let open=card.classList.contains("active");

if(open){
card.classList.remove("active");
menu.style.maxHeight=null;
}else{
card.classList.add("active");
menu.style.maxHeight=menu.scrollHeight+"px";
}
}

/* TYPING */
let text="Gio Ahmed Hasan";
let i=0;

function typing(){
if(i<text.length){
document.getElementById("typing").innerHTML+=text.charAt(i);
i++;
setTimeout(typing,120);
}
}
typing();

/* PARTICLES */
const canvas=document.getElementById("canvas");
const ctx=canvas.getContext("2d");

canvas.width=window.innerWidth;
canvas.height=window.innerHeight;

let particles=[];

for(let i=0;i<80;i++){
particles.push({
x:Math.random()*canvas.width,
y:Math.random()*canvas.height,
r:Math.random()*2,
dx:(Math.random()-0.5),
dy:(Math.random()-0.5)
});
}

function draw(){
ctx.clearRect(0,0,canvas.width,canvas.height);

ctx.fillStyle="rgba(56,189,248,.6)";

particles.forEach(p=>{
p.x+=p.dx;
p.y+=p.dy;

if(p.x<0||p.x>canvas.width)p.dx*=-1;
if(p.y<0||p.y>canvas.height)p.dy*=-1;

ctx.beginPath();
ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
ctx.fill();
});

requestAnimationFrame(draw);
}
draw();

window.addEventListener("resize",()=>{
canvas.width=window.innerWidth;
canvas.height=window.innerHeight;
});

</script>

</body>
</html>
