<!DOCTYPE html>
<html lang="ka">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>ბათუმი ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Georgian:wght@400;700;900&display=swap" rel="stylesheet">

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:"Noto Sans Georgian",sans-serif;
    overflow:hidden;
    height:100vh;

    background:
    linear-gradient(rgba(0,0,0,.45),rgba(0,0,0,.55)),
    url("https://images.unsplash.com/photo-1681287903958-7e74a53ce38a?auto=format&fit=crop&w=1600&q=80");

    background-size:cover;
    background-position:center;
    display:flex;
    justify-content:center;
    align-items:center;
}

.card{
    width:90%;
    max-width:620px;
    background:rgba(255,255,255,.12);
    backdrop-filter:blur(16px);
    border:1px solid rgba(255,255,255,.18);
    border-radius:25px;
    padding:45px;
    text-align:center;
    color:white;
    box-shadow:0 20px 60px rgba(0,0,0,.35);
    animation:fade 1s ease;
}

h1{
    font-size:2.3rem;
    margin-bottom:40px;
    line-height:1.4;
}

.buttons{
    display:flex;
    justify-content:center;
    gap:25px;
    position:relative;
    height:90px;
}

button{
    border:none;
    cursor:pointer;
    font-size:20px;
    padding:15px 40px;
    border-radius:50px;
    transition:.25s;
    font-weight:bold;
}

#yes{
    background:#22c55e;
    color:white;
}

#yes:hover{
    transform:scale(1.08);
}

#no{
    background:#ef4444;
    color:white;
    position:absolute;
}

#message{
    margin-top:35px;
    font-size:30px;
    font-weight:bold;
    display:none;
    animation:pop .5s;
}

.heart{
    position:absolute;
    color:white;
    opacity:.25;
    animation:float linear infinite;
    user-select:none;
}

@keyframes float{
0%{
transform:translateY(100vh);
opacity:0;
}
20%{
opacity:.3;
}
100%{
transform:translateY(-120vh);
opacity:0;
}
}

@keyframes fade{
from{
opacity:0;
transform:translateY(30px);
}
to{
opacity:1;
transform:none;
}
}

@keyframes pop{
from{
transform:scale(.5);
opacity:0;
}
to{
transform:scale(1);
opacity:1;
}
}
</style>
</head>

<body>

<div class="card">

<h1>
🏖️ ბათუმში ხო უეჭველი ერთად მივდივართ?
</h1>

<div class="buttons">
<button id="yes">კი ❤️</button>
<button id="no">არა 😅</button>
</div>

<div id="message">
❤️ სწორი პასუხია ❤️
</div>

</div>

<script>

const no=document.getElementById("no");
const yes=document.getElementById("yes");
const msg=document.getElementById("message");

function moveButton(){

const maxX=window.innerWidth-140;
const maxY=window.innerHeight-80;

const x=Math.random()*maxX;
const y=Math.random()*maxY;

no.style.left=x+"px";
no.style.top=y+"px";

}

no.addEventListener("mouseover",moveButton);
no.addEventListener("click",moveButton);

yes.onclick=()=>{

document.querySelector(".buttons").style.display="none";

msg.innerHTML="❤️ სწორი პასუხია ❤️";
msg.style.display="block";

confetti();

};

function confetti(){

for(let i=0;i<80;i++){

let h=document.createElement("div");

h.innerHTML=["❤️","✨","🎉","💖","🥳"][Math.floor(Math.random()*5)];

h.className="heart";

h.style.left=Math.random()*100+"vw";
h.style.fontSize=(20+Math.random()*35)+"px";
h.style.animationDuration=(5+Math.random()*5)+"s";

document.body.appendChild(h);

}

}

for(let i=0;i<25;i++){

let h=document.createElement("div");

h.className="heart";

h.innerHTML="❤";

h.style.left=Math.random()*100+"vw";
h.style.fontSize=(15+Math.random()*25)+"px";
h.style.animationDuration=(8+Math.random()*8)+"s";
h.style.animationDelay=Math.random()*8+"s";

document.body.appendChild(h);

}

</script>

</body>
</html>
