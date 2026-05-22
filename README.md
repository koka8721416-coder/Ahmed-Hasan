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
    background:linear-gradient(-45deg,#020617,#0f172a,#1e293b,#2563eb);
    background-size:400% 400%;
    animation:bg 12s ease infinite;
    min-height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    position:relative;
}

/* خلفية متحركة */

@keyframes bg{
    0%{background-position:0% 50%;}
    50%{background-position:100% 50%;}
    100%{background-position:0% 50%;}
}

/* الحشرات */

.bug{
    position:absolute;
    font-size:30px;
    opacity:0.5;
    animation:moveBug linear infinite;
}

.b1{
    top:10%;
    left:-10%;
    animation-duration:15s;
}

.b2{
    top:40%;
    left:-15%;
    animation-duration:18s;
}

.b3{
    top:75%;
    left:-10%;
    animation-duration:12s;
}

.b4{
    top:20%;
    left:-12%;
    animation-duration:20s;
}

@keyframes moveBug{
    from{
        transform:translateX(0) rotate(0deg);
    }
    to{
        transform:translateX(120vw) rotate(360deg);
    }
}

/* الكونتينر */

.container{
    width:90%;
    max-width:430px;
    text-align:center;
    z-index:2;
}

/* العنوان */

.title{
    color:white;
    font-size:32px;
    font-weight:bold;
    margin-bottom:35px;
    animation:glow 2s infinite alternate;
}

@keyframes glow{
    from{
        text-shadow:0 0 10px #38bdf8;
    }
    to{
        text-shadow:0 0 25px #ffffff;
    }
}

/* الكروت */

.card{
    background:rgba(255,255,255,0.12);
    backdrop-filter:blur(12px);
    border:1px solid rgba(255,255,255,0.2);
    border-radius:25px;
    padding:25px;
    margin:22px 0;
    cursor:pointer;
    transition:0.4s;
    overflow:hidden;
    position:relative;
    animation:float 3s ease-in-out infinite;
}

.card:hover{
    transform:translateY(-10px) scale(1.03);
    box-shadow:0 0 30px rgba(255,255,255,0.25);
}

/* لمعة */

.card::before{
    content:"";
    position:absolute;
    top:0;
    left:-100%;
    width:100%;
    height:100%;
    background:linear-gradient(
        120deg,
        transparent,
        rgba(255,255,255,0.3),
        transparent
    );
    animation:shine 3s infinite;
}

@keyframes shine{
    100%{
        left:120%;
    }
}

.icon{
    font-size:55px;
    margin-bottom:15px;
    animation:jump 2s infinite;
}

.card-title{
    color:white;
    font-size:24px;
    font-weight:bold;
}

@keyframes jump{
    0%{transform:translateY(0);}
    50%{transform:translateY(-8px);}
    100%{transform:translateY(0);}
}

@keyframes float{
    0%{transform:translateY(0);}
    50%{transform:translateY(-5px);}
    100%{transform:translateY(0);}
}

/* القائمة الفرعية */

.submenu{
    display:none;
    margin-top:18px;
    animation:fade 0.6s ease;
}

.submenu a{
    display:block;
    text-decoration:none;
    background:rgba(255,255,255,0.15);
    color:white;
    margin:12px 0;
    padding:15px;
    border-radius:15px;
    transition:0.3s;
    font-size:18px;
    font-weight:bold;
}

.submenu a:hover{
    background:#38bdf8;
    transform:scale(1.03);
}

@keyframes fade{
    from{
        opacity:0;
        transform:translateY(20px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

</style>
</head>

<body>

<!-- الحشرات -->

<div class="bug b1">🐞</div>
<div class="bug b2">🦋</div>
<div class="bug b3">🐜</div>
<div class="bug b4">🐝</div>

<div class="container">

<div class="title">
Create by Gio Ahmed Hasan
</div>

<!-- حفريات -->

<div class="card" onclick="toggleMenu()">

<div class="icon">🪨</div>

<div class="card-title">
حفريات
</div>

<div class="submenu" id="submenu">

<a href="https://koka8721416-coder.github.io/Exam/" target="_blank">
79 اختياري + 50 صح وغلط
</a>

<a href="https://koka8721416-coder.github.io/gh/" target="_blank">
السابق + الشيت + التكليف حفريات
</a>

</div>

</div>

<!-- حشرات -->

<div class="card"
onclick="window.open('https://koka8721416-coder.github.io/Ahmed-Hasan/')">

<div class="icon">🐞</div>

<div class="card-title">
حشرات
</div>

</div>

</div>

<script>

function toggleMenu(){

let menu = document.getElementById("submenu");

if(menu.style.display === "block"){
    menu.style.display = "none";
}
else{
    menu.style.display = "block";
}

}

</script>

</body>
</html>
