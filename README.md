<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Jaan ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    overflow:hidden;
    background:linear-gradient(135deg,#ff4d6d,#ff85a2,#ffc2d1);
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    color:white;
    position:relative;
    text-align:center;
}

.container{
    z-index:10;
    padding:20px;
    width:100%;
}

h1{
    font-size:2rem;
    font-weight:bold;
    margin-bottom:40px;
    text-shadow:2px 2px 10px rgba(0,0,0,0.3);
}

.buttons{
    position:relative;
    display:flex;
    justify-content:center;
    gap:20px;
    height:70px;
}

button{
    padding:15px 30px;
    border:none;
    border-radius:50px;
    font-size:1.2rem;
    font-weight:bold;
    cursor:pointer;
    transition:0.2s;
}

#yesBtn{
    background:#00ff88;
    color:black;
}

#noBtn{
    background:#ff1e56;
    color:white;
    position:absolute;
    left:55%;
}

.heart{
    position:absolute;
    color:rgba(255,255,255,0.7);
    animation:float 8s linear infinite;
}

@keyframes float{
    from{
        transform:translateY(100vh);
        opacity:1;
    }
    to{
        transform:translateY(-10vh);
        opacity:0;
    }
}

.success{
    display:none;
    animation:pop 1s ease;
}

.success h2{
    font-size:2.5rem;
    color:yellow;
    text-shadow:2px 2px 15px black;
}

.gif{
    margin-top:20px;
    width:220px;
    border-radius:20px;
}

.graffiti{
    position:absolute;
    font-size:2rem;
    font-weight:bold;
    animation:spin 4s linear infinite;
    opacity:0.8;
}

@keyframes spin{
    from{transform:rotate(0deg);}
    to{transform:rotate(360deg);}
}

@keyframes pop{
    from{transform:scale(0);}
    to{transform:scale(1);}
}
</style>
</head>
<body>

<div id="hearts"></div>

<div class="container" id="main">
    <h1>gussa sant huyaa jaan ? ❤️</h1>
    <div class="buttons">
        <button id="yesBtn">YES</button>
        <button id="noBtn">NO</button>
    </div>
</div>

<div class="success" id="success">
    <h2>kr diya n happy 😎</h2>
    <img class="gif" src="https://media.giphy.com/media/l3vRlT2k2L35Cnn5C/giphy.gif">
</div>

<script>
// Floating hearts
function createHeart(){
    const heart=document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML="❤️";
    heart.style.left=Math.random()*100+"vw";
    heart.style.fontSize=(Math.random()*25+20)+"px";
    heart.style.animationDuration=(Math.random()*5+5)+"s";
    document.body.appendChild(heart);

    setTimeout(()=>heart.remove(),8000);
}
setInterval(createHeart,300);

// NO button escape
const noBtn=document.getElementById("noBtn");

function moveNo(){
    const x=Math.random()*(window.innerWidth-100);
    const y=Math.random()*(window.innerHeight-100);
    noBtn.style.left=x+"px";
    noBtn.style.top=y+"px";
}

noBtn.addEventListener("mouseover",moveNo);
noBtn.addEventListener("touchstart",moveNo);

// YES button
document.getElementById("yesBtn").onclick=function(){
    document.getElementById("main").style.display="none";
    document.getElementById("success").style.display="block";

    for(let i=0;i<25;i++){
        let gra=document.createElement("div");
        gra.className="graffiti";
        gra.innerHTML=["💖","😍","🥰","LOVE","😘"][Math.floor(Math.random()*5)];
        gra.style.left=Math.random()*100+"vw";
        gra.style.top=Math.random()*100+"vh";
        document.body.appendChild(gra);
    }
}
</script>

</body>
</html>
