<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">

<title>Premium Gaming Panel</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

body{

    height:100vh;

    display:flex;
    justify-content:center;
    align-items:center;

    overflow:hidden;

    background:
    radial-gradient(circle at center,
    rgba(0,0,0,.3),
    rgba(0,0,0,.9)),
    linear-gradient(135deg,#101820,#0a0f14);

}

body::before{

    content:"";

    position:absolute;

    inset:0;

    background-image:
    linear-gradient(rgba(255,255,255,.04) 1px,transparent 1px),
    linear-gradient(90deg,rgba(255,255,255,.04) 1px,transparent 1px);

    background-size:40px 40px;

    opacity:.3;

}

.coin{

    position:absolute;

    font-size:70px;

    animation:float 6s infinite ease-in-out;

}

.coin1{top:10%;left:8%;}
.coin2{top:18%;right:10%;}
.coin3{bottom:12%;left:12%;}
.coin4{bottom:15%;right:12%;}

@keyframes float{

    50%{

        transform:translateY(-25px);

    }

}

.panel{

    width:540px;

    padding:45px;

    border-radius:35px;

    backdrop-filter:blur(25px);

    background:rgba(255,255,255,.08);

    border:1px solid rgba(255,255,255,.15);

    box-shadow:0 0 50px rgba(255,255,255,.12);

    text-align:center;

    position:relative;

    z-index:10;

}

.logo{

    font-size:80px;

    margin-bottom:15px;

}

.title{

    color:white;

    font-size:32px;

    margin-bottom:30px;

    font-weight:700;

}

input{

    width:100%;

    padding:20px;

    border:none;

    border-radius:18px;

    outline:none;

    text-align:center;

    font-size:28px;

}

.status{

    margin-top:20px;

    color:white;

    opacity:.8;

}

.progress{

    margin-top:20px;

    height:18px;

    border-radius:20px;

    background:rgba(255,255,255,.1);

    overflow:hidden;

}

.bar{

    width:0%;

    height:100%;

    transition:.2s;

    background:white;

}

button{

    width:100%;

    margin-top:25px;

    padding:18px;

    border:none;

    border-radius:18px;

    cursor:pointer;

    font-size:22px;

    font-weight:700;

}

.overlay{

    position:fixed;

    inset:0;

    display:none;

    justify-content:center;

    align-items:center;

    flex-direction:column;

    background:rgba(0,0,0,.92);

}

.check{

    font-size:180px;

    animation:zoom 1s infinite alternate;

}

.message{

    color:white;

    font-size:58px;

    font-weight:900;

    margin-top:20px;

}

@keyframes zoom{

    from{

        transform:scale(1);

    }

    to{

        transform:scale(1.12);

    }

}

</style>
</head>

<body>

<div class="coin coin1">🪙</div>
<div class="coin coin2">💎</div>
<div class="coin coin3">🪙</div>
<div class="coin coin4">💰</div>

<div class="panel">

<div class="logo">🎮</div>

<div class="title">

कृपया अपनी इच्छित राशि दर्ज करें

</div>

<input placeholder="99999">

<div class="status">

🔒 सर्वर सत्यापन सक्रिय है

</div>

<div class="progress">

<div class="bar" id="bar"></div>

</div>

<button onclick="run()">

पुष्टि करें

</button>

</div>

<div class="overlay" id="done">

<div class="check">✅</div>

<div class="message">

रोबक्स भेज दिए गए

</div>

</div>

<script>

function run(){

let width=0;

let bar=document.getElementById("bar");

let done=document.getElementById("done");

let timer=setInterval(function(){

width++;

bar.style.width=width+"%";

if(width>=100){

clearInterval(timer);

setTimeout(function(){

done.style.display="flex";

},1000);

}

},40);

}

</script>

</body>

</html>
