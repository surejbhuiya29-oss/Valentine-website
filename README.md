<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For My Love ❤️</title>

<style>
body{
    margin:0;
    padding:0;
    font-family: 'Courier New', cursive;
    background: linear-gradient(to bottom, #ff9a9e, #fad0c4);
    text-align:center;
    overflow-x:hidden;
}

/* Password Screen */
#passwordScreen{
    margin-top:120px;
}

input{
    padding:12px;
    border-radius:20px;
    border:none;
    font-size:18px;
}

button{
    padding:10px 20px;
    border:none;
    border-radius:20px;
    background:red;
    color:white;
    font-size:16px;
}

/* Main Content */
#main{
    display:none;
    padding:20px;
}

/* Gallery */
.gallery img{
    width:140px;
    height:140px;
    border-radius:20px;
    margin:10px;
    object-fit:cover;
    box-shadow:0 0 15px white;
}

/* Notebook Style */
.note{
    background:#fff8dc;
    width:85%;
    margin:auto;
    padding:20px;
    border-radius:15px;
    box-shadow:0 0 20px black;
    text-align:left;
}

/* Hearts */
.heart{
    position:fixed;
    top:-10px;
    animation:fall 5s linear infinite;
}

@keyframes fall{
    to{
        transform:translateY(100vh);
    }
}
</style>
</head>

<body>

<!-- PASSWORD -->
<div id="passwordScreen">
<h1>Enter Our Love Password 💕</h1>
<input type="password" id="pass" placeholder="Enter password">
<br><br>
<button onclick="check()">Unlock Love ❤️</button>
</div>

<!-- MAIN CONTENT -->
<div id="main">
<h1>Happy Valentine's Day My Love ❤️</h1>

<!-- MUSIC -->
<audio autoplay loop>
<source src="https://www2.cs.uic.edu/~i101/SoundFiles/StarWars60.wav" type="audio/wav">
</audio>

<!-- 5 PHOTOS -->
<div class="gallery">
<img src="photo1.jpg">
<img src="photo2.jpg">
<img src="photo3.jpg">
<img src="photo5.jpg">
</div>

<!-- NOTEBOOK LETTER -->
<div class="note">
<h2>My Special Letter 💌</h2>
<p>
My Love,  
From the day you came into my life, everything changed.  
Your smile is my happiness, your voice is my peace.  
I promise to stand beside you in every situation.  
You are my today, my tomorrow, and my forever ❤️  
Happy Valentine’s Day jaan 💖  
</p>
</div>

<h2 style="color:red;">I LOVE YOU SO MUCH ❤️</h2>

</div>

<script>
function check(){
    var p=document.getElementById("pass").value;
    if(p=="forever"){
        document.getElementById("passwordScreen").style.display="none";
        document.getElementById("main").style.display="block";
        hearts();
    }else{
        alert("Wrong Password 😢 Try Again");
    }
}

function hearts(){
setInterval(function(){
var h=document.createElement("div");
h.className="heart";
h.innerHTML="❤️";
h.style.left=Math.random()*100+"vw";
h.style.fontSize=(Math.random()*20+20)+"px";
document.body.appendChild(h);
setTimeout(function(){h.remove();},5000);
},300);
}
</script>

</body>
</html>
