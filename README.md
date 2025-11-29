# bronzaart
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>БронзаАрт — Макс Вьюгин</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Montserrat:wght@300;400&display=swap" rel="stylesheet">

<style>
:root {
--dark:#120906;--brown:#2A1B14;--bronze:#8B5A2B;--beige:#E6D2B5;--light:#F5EFE6;
}

body{
margin:0;font-family:Montserrat,sans-serif;
background:radial-gradient(circle,#2A1B14,#120906);
color:var(--beige);overflow-x:hidden;
}

.loader{
position:fixed;inset:0;background:black;
display:flex;align-items:center;justify-content:center;
z-index:9999;animation:fadeOut 4s forwards;
}
.loader span{
font-family:Cinzel;font-size:28px;color:var(--bronze);
animation:pulse 2s infinite;
}

@keyframes fadeOut{0%,80%{opacity:1}100%{opacity:0;pointer-events:none}}
@keyframes pulse{0%{opacity:.2}50%{opacity:1}100%{opacity:.2}}

.lang-switch{
position:fixed;top:20px;right:20px;z-index:99;
background:var(--bronze);padding:8px 16px;border-radius:20px;
cursor:pointer;color:white;font-size:14px;
}

section{padding:90px 10%;}
.hero{
min-height:100vh;background:url("IMG_7456.png") center/cover no-repeat;
display:flex;align-items:center;position:relative;
}
.hero::after{
content:"";position:absolute;inset:0;background:rgba(0,0,0,.75);
}
.hero-content{position:relative;max-width:700px}
h1,h2{font-family:Cinzel;letter-spacing:2px}

.gallery{
display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
gap:30px;
}
.card{
background:rgba(0,0,0,.5);padding:15px;border-radius:14px;text-align:center;
transition:.5s;
}
.card:hover{transform:translateY(-8px);box-shadow:0 0 40px rgba(139,90,43,.6)}
.card img{width:100%;border-radius:10px}
.price{margin:12px;font-size:18px}

button{
background:var(--bronze);border:none;color:white;
padding:10px 25px;border-radius:20px;cursor:pointer;
}

form{max-width:500px;display:grid;gap:12px}
input,textarea{
background:rgba(0,0,0,.5);border:1px solid var(--bronze);
color:white;padding:12px;border-radius:6px;
}

footer{text-align:center;padding:30px;font-size:14px}

@media(max-width:768px){
section{padding:60px 6%}
}
</style>
</head>

<body>

<div class="loader"><span>Пробуждение Бронзы…</span></div>

<div class="lang-switch" onclick="toggleLang()">RU / EN</div>

<section class="hero">
<div class="hero-content">
<h1 id="title">БРОНЗААРТ</h1>
<p id="subtitle">Макс Вьюгин — художественное литьё из бронзы</p>
</div>
</section>

<section>
<h2 id="aboutTitle">О мастере</h2>
<p id="aboutText">
Я создаю бронзовые образы, соединяя древние традиции литья,
алхимию огня и современное авторское видение.
Каждая работа уникальна.
</p>
</section>

<section>
<h2 id="catalogTitle">Каталог</h2>
<div class="gallery">

<div class="card">
<img src="IMG_7456.png">
<div class="price">2128 ₽</div>
<button onclick="order('Скульптура №1 — 2128 ₽')">Заказать</button>
<button onclick="pay()">Оплатить</button>
</div>

<div class="card">
<img src="IMG_7454.png">
<div class="price">9145 ₽</div>
<button onclick="order('Скульптура №2 — 9145 ₽')">Заказать</button>
<button onclick="pay()">Оплатить</button>
</div>

<div class="card">
<img src="IMG_7457.png">
<div class="price">9421 ₽</div>
<button onclick="order('Скульптура №3 — 9421 ₽')">Заказать</button>
<button onclick="pay()">Оплатить</button>
</div>

</div>
</section>

<section>
<h2 id="orderTitle">Оформить заказ</h2>
<form>
<input id="name" placeholder="Имя">
<input id="email" placeholder="Email">
<input id="product" placeholder="Выбранная работа">
<textarea id="country" placeholder="Страна доставки"></textarea>
<button>Отправить</button>
</form>

<p id="world">Продажи по России и миру</p>
</section>

<footer>© БронзаАрт — Макс Вьюгин</footer>

<script>
function order(name){
document.getElementById("product").value=name;
}

function pay(){
alert("Онлайн-оплата будет подключена через Stripe/PayPal после размещения сайта на хостинге.");
}

let ru=true;
function toggleLang(){
ru=!ru;
document.getElementById("subtitle").innerText=ru?
"Макс Вьюгин — художественное литьё из бронзы":
"Max Vyugin — Bronze Art Sculptor";

document.getElementById("aboutTitle").innerText=ru?"О мастере":"About the Artist";
document.getElementById("aboutText").innerText=ru?
"Я создаю бронзовые образы, соединяя древние традиции литья, алхимию огня и авторское видение.":
"I create bronze sculptures combining ancient casting traditions, fire alchemy and modern авторский стиль.";

document.getElementById("catalogTitle").innerText=ru?"Каталог":"Catalog";
document.getElementById("orderTitle").innerText=ru?"Оформить заказ":"Place an Order";
document.getElementById("world").innerText=ru?"Продажи по России и миру":"Worldwide Shipping";
}
</script>

</body>
</html>
