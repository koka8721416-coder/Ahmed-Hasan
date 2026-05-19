<!DOCTYPE html>
<html lang="ar" dir="rtl">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>منصة أساسيات علم الحشرات</title>

<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap" rel="stylesheet">

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Cairo',sans-serif;
}

body{
    background:linear-gradient(135deg,#07111f,#10243f,#0f172a);
    min-height:100vh;
    overflow-x:hidden;
    color:white;
    position:relative;
}

/* خلفية متحركة */

.bg{
    position:fixed;
    width:100%;
    height:100%;
    top:0;
    left:0;
    overflow:hidden;
    z-index:-1;
}

.bug{
    position:absolute;
    font-size:35px;
    animation:fly linear infinite;
    opacity:0.18;
}

.bug:nth-child(1){
    top:10%;
    left:-10%;
    animation-duration:18s;
}

.bug:nth-child(2){
    top:35%;
    left:-15%;
    animation-duration:22s;
}

.bug:nth-child(3){
    top:70%;
    left:-12%;
    animation-duration:25s;
}

.bug:nth-child(4){
    top:55%;
    left:-8%;
    animation-duration:16s;
}

@keyframes fly{
    from{
        transform:translateX(0) rotate(0deg);
    }
    to{
        transform:translateX(130vw) rotate(360deg);
    }
}

/* الهيدر */

header{
    text-align:center;
    padding:40px 20px 20px;
}

header h1{
    font-size:42px;
    color:#38bdf8;
    text-shadow:0 0 15px rgba(56,189,248,0.6);
}

header p{
    margin-top:10px;
    color:#cbd5e1;
    font-size:18px;
}

/* الكروت */

.container{
    display:flex;
    justify-content:center;
    align-items:center;
    gap:30px;
    flex-wrap:wrap;
    padding:50px 20px;
}

.card{
    width:320px;
    height:220px;
    background:rgba(255,255,255,0.07);
    border:1px solid rgba(255,255,255,0.1);
    backdrop-filter:blur(10px);
    border-radius:30px;
    cursor:pointer;
    transition:0.4s;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    box-shadow:0 10px 30px rgba(0,0,0,0.4);
    position:relative;
    overflow:hidden;
}

.card::before{
    content:'';
    position:absolute;
    width:150%;
    height:150%;
    background:linear-gradient(
        45deg,
        transparent,
        rgba(56,189,248,0.25),
        transparent
    );
    top:-50%;
    left:-50%;
    transform:rotate(25deg);
    transition:0.5s;
}

.card:hover::before{
    left:100%;
}

.card:hover{
    transform:translateY(-10px) scale(1.04);
    background:#0ea5e9;
}

.card .icon{
    font-size:55px;
    margin-bottom:15px;
}

.card h2{
    font-size:28px;
    margin-bottom:10px;
}

.card p{
    font-size:16px;
    color:#e2e8f0;
}

/* عرض الصفحات */

.viewer{
    width:100%;
    height:85vh;
    display:none;
    padding:10px;
}

iframe{
    width:100%;
    height:100%;
    border:none;
    border-radius:20px;
    background:white;
}

/* زر الرجوع */

.backBtn{
    display:none;
    margin:10px auto 20px;
    padding:14px 35px;
    border:none;
    border-radius:15px;
    background:#ef4444;
    color:white;
    font-size:18px;
    cursor:pointer;
    transition:0.3s;
    box-shadow:0 5px 15px rgba(0,0,0,0.3);
}

.backBtn:hover{
    background:#dc2626;
    transform:scale(1.05);
}

/* موبايل */

@media(max-width:768px){

    header h1{
        font-size:30px;
    }

    .card{
        width:90%;
        height:200px;
    }

}

</style>
</head>

<body>

<!-- الحشرات المتحركة -->
<div class="bg">
    <div class="bug">🪲</div>
    <div class="bug">🐞</div>
    <div class="bug">🦋</div>
    <div class="bug">🐜</div>
</div>

<header>
    <h1>🪲 منصة أساسيات علم الحشرات 🦋</h1>
    <p>اختر القسم اللي عايز تدخله</p>
</header>

<div class="container" id="menu">

    <div class="card"
    onclick="openPage('https://koka8721416-coder.github.io/koka2/')">

        <div class="icon">📄</div>
        <h2>امتحان سابق حشرات</h2>
        <p>اختبر نفسك في الامتحانات السابقة</p>

    </div>

    <div class="card"
    onclick="openPage('https://koka8721416-coder.github.io/koka/')">

        <div class="icon">📚</div>
        <h2>بنك أسئلة 100 سؤال</h2>
        <p>راجع أهم الأسئلة على المنهج</p>

    </div>

    <div class="card"
    onclick="openPage('https://koka8721416-coder.github.io/gioo/')">

        <div class="icon">🔥</div>
        <h2>30 سؤال اختياري صعبين</h2>
        <p>أسئلة قوية للمراجعة النهائية</p>

    </div>

</div>

<button class="backBtn" id="backBtn" onclick="goBack()">
⬅ الرجوع للرئيسية
</button>

<div class="viewer" id="viewer">
    <iframe id="frame"></iframe>
</div>

<script>

function openPage(link){

    document.getElementById("frame").src = link;

    document.getElementById("viewer").style.display = "block";

    document.getElementById("backBtn").style.display = "block";

    document.getElementById("menu").style.display = "none";

}

function goBack(){

    document.getElementById("viewer").style.display = "none";

    document.getElementById("backBtn").style.display = "none";

    document.getElementById("menu").style.display = "flex";

    document.getElementById("frame").src = "";

}

</script>

</body>
</html>
