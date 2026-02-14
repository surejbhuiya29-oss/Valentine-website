<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Photo Album</title>

<style>
body{
    margin:0;
    background:linear-gradient(to bottom,#1a1a2e,#16213e);
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    overflow:hidden;
    font-family:sans-serif;
}

.book{
    width:300px;
    height:400px;
    position:relative;
    perspective:1500px;
}

.page{
    width:100%;
    height:100%;
    position:absolute;
    transform-origin:left;
    transition:transform 1s;
    background:white;
    border-radius:10px;
    box-shadow:0 10px 20px rgba(0,0,0,0.5);
    overflow:hidden;
}

.page img{
    width:100%;
    height:100%;
    object-fit:cover;
}

.page.flipped{
    transform:rotateY(-180deg);
}

.controls{
    position:absolute;
    bottom:20px;
    width:100%;
    text-align:center;
}

button{
    padding:10px 20px;
    margin:5px;
    border:none;
    border-radius:20px;
    background:#ff4e88;
    color:white;
    font-size:16px;
}
</style>
</head>

<body>

<div class="book" id="book">
    <!-- 15 Pages -->
    <div class="page"><img src="photo1.jpg"></div>
    <div class="page"><img src="photo2.jpg"></div>
    <div class="page"><img src="photo3.jpg"></div>
    <div class="page"><img src="photo4.jpg"></div>
    <div class="page"><img src="photo5.jpg"></div>
    <div class="page"><img src="photo6.jpg"></div>
    <div class="page"><img src="photo7.jpg"></div>
    <div class="page"><img src="photo8.jpg"></div>
    <div class="page"><img src="photo9.jpg"></div>
    <div class="page"><img src="photo10.jpg"></div>
    <div class="page"><img src="photo11.jpg"></div>
    <div class="page"><img src="photo12.jpg"></div>
    <div class="page"><img src="photo13.jpg"></div>
    <div class="page"><img src="photo14.jpg"></div>
    <div class="page"><img src="photo15.jpg"></div>
</div>

<div class="controls">
    <button onclick="prevPage()">⬅ Prev</button>
    <button onclick="nextPage()">Next ➡</button>
</div>

<script>
const pages = document.querySelectorAll(".page");
let current = 0;

function nextPage(){
    if(current < pages.length){
        pages[current].classList.add("flipped");
        current++;
    }
}

function prevPage(){
    if(current > 0){
        current--;
        pages[current].classList.remove("flipped");
    }
}

/* Auto Slideshow */
setInterval(()=>{
    if(current < pages.length){
        nextPage();
    }else{
        for(let i=pages.length-1;i>=0;i--){
            pages[i].classList.remove("flipped");
        }
        current=0;
    }
},3000);
</script>

</body>
</html>
