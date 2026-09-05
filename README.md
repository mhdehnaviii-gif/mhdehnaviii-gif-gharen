<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>gharen</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Nastaliq+Urdu:wght@400;500;600&display=swap" rel="stylesheet">

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html{
    scroll-behavior:smooth;
}

body{
    min-height:100vh;
    overflow-x:hidden;
    background:#6f7337;
    color:#f3e8bd;
    font-family:"Noto Nastaliq Urdu",serif;
}

/* ===== BACKGROUND ===== */

.background{
    position:fixed;
    inset:0;
    overflow:hidden;
    z-index:-5;
    background:
        radial-gradient(circle at 20% 20%,rgba(190,170,70,.28),transparent 28%),
        radial-gradient(circle at 80% 70%,rgba(0,75,55,.32),transparent 32%),
        linear-gradient(135deg,#77783b,#596c39,#7c7837);
}

.light{
    position:absolute;
    width:38vw;
    height:38vw;
    min-width:240px;
    min-height:240px;
    border-radius:50%;
    filter:blur(75px);
    opacity:.30;
    mix-blend-mode:screen;
    animation:float 18s ease-in-out infinite alternate;
}

.light.one{
    background:#d4c467;
    top:-10%;
    left:-10%;
}

.light.two{
    background:#176c57;
    right:-10%;
    top:20%;
    animation-delay:-5s;
}

.light.three{
    background:#b8a74e;
    bottom:-15%;
    left:25%;
    animation-delay:-10s;
}

.light.four{
    background:#064d3e;
    bottom:10%;
    right:20%;
    animation-delay:-14s;
}

@keyframes float{
    0%{
        transform:translate(0,0) scale(1);
    }
    50%{
        transform:translate(14vw,8vh) scale(1.25);
    }
    100%{
        transform:translate(-8vw,-10vh) scale(.9);
    }
}

/* moving light ring */

.orbit{
    position:absolute;
    width:80vw;
    height:80vw;
    border:1px solid rgba(232,220,157,.10);
    border-radius:50%;
    left:50%;
    top:50%;
    transform:translate(-50%,-50%);
    animation:rotate 35s linear infinite;
}

.orbit::before,
.orbit::after{
    content:"";
    position:absolute;
    width:13px;
    height:13px;
    border-radius:50%;
    background:#e1cf70;
    box-shadow:0 0 30px 10px rgba(224,206,94,.25);
}

.orbit::before{
    top:5%;
    left:18%;
}

.orbit::after{
    bottom:8%;
    right:13%;
}

@keyframes rotate{
    to{
        transform:translate(-50%,-50%) rotate(360deg);
    }
}

/* ===== MAIN ===== */

main{
    width:min(900px,92%);
    margin:auto;
    padding:55px 0 80px;
}

/* ===== INTRO ===== */

.intro{
    min-height:72vh;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    animation:appear 2s ease both;
}

.quote{
    max-width:700px;
}

.quote-text{
    font-size:clamp(16px,3vw,24px);
    line-height:2.5;
    color:#eee4bd;
    text-shadow:
        0 0 20px rgba(238,221,150,.18);
}

.author{
    margin-top:12px;
    font-size:clamp(11px,2vw,15px);
    color:#d9cf9b;
}

@keyframes appear{
    from{
        opacity:0;
        transform:translateY(20px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

/* ===== SITE NAME ===== */

.brand{
    text-align:center;
    margin-bottom:35px;
    color:#e7da9b;
    font-size:clamp(25px,6vw,42px);
    text-shadow:0 0 25px rgba(232,211,112,.18);
}

/* ===== BOX ===== */

.box{
    width:100%;
    margin:18px auto;
    border:1px solid rgba(226,214,151,.27);
    background:rgba(31,64,50,.20);
    backdrop-filter:blur(15px);
    -webkit-backdrop-filter:blur(15px);
    border-radius:20px;
    box-shadow:
        0 20px 60px rgba(15,40,30,.18),
        inset 0 1px rgba(255,255,255,.08);
    overflow:hidden;
    transition:.4s ease;
}

.box:hover{
    border-color:rgba(228,211,133,.45);
    transform:translateY(-2px);
}

/* ===== BOX TITLE ===== */

.box-title{
    width:100%;
    border:0;
    outline:0;
    cursor:pointer;
    padding:20px 25px;
    background:transparent;
    color:#f0e5b8;
    font-family:"Noto Nastaliq Urdu",serif;
    font-size:clamp(20px,4vw,28px);
    text-align:center;
    transition:.3s;
}

.box-title:hover{
    background:rgba(223,208,130,.07);
}

.arrow{
    display:inline-block;
    margin-right:10px;
    font-family:Arial,sans-serif;
    font-size:15px;
    transition:.4s;
}

.box.open .arrow{
    transform:rotate(180deg);
}

/* ===== CONTENT ===== */

.content{
    max-height:0;
    overflow:hidden;
    opacity:0;
    transition:
        max-height .7s ease,
        opacity .5s ease,
        padding .5s ease;
    padding:0 25px;
}

.box.open .content{
    max-height:900px;
    opacity:1;
    padding:5px 25px 30px;
}

/* ===== INNER BUTTONS ===== */

.inner{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:14px;
    margin-top:10px;
}

.inner-button{
    min-height:75px;
    display:flex;
    align-items:center;
    justify-content:center;
    border:1px solid rgba(222,208,139,.23);
    border-radius:15px;
    background:rgba(20,57,44,.23);
    color:#e7dcaa;
    font-family:"Noto Nastaliq Urdu",serif;
    font-size:20px;
    cursor:pointer;
    transition:.35s;
}

.inner-button:hover{
    transform:translateY(-4px);
    background:rgba(211,198,118,.10);
    border-color:rgba(230,215,143,.45);
    box-shadow:0 10px 35px rgba(0,0,0,.13);
}

@media(max-width:600px){
    .inner{
        grid-template-columns:1fr;
    }

    main{
        padding-top:30px;
    }

    .intro{
        min-height:65vh;
    }
}

/* ===== POETRY PLACEHOLDER ===== */

.poetry-note{
    text-align:center;
    margin-top:20px;
    color:#cfc590;
    font-size:15px;
    opacity:.8;
}

/* ===== SONGS ===== */

.song-name{
    text-align:center;
    padding:8px 0;
    color:#eadfae;
    font-size:20px;
}

/* ===== SHORT STORY ===== */

.empty{
    text-align:center;
    padding:15px 0 5px;
    color:#c8c18f;
    font-size:17px;
}

/* ===== FOOTER ===== */

footer{
    text-align:center;
    margin-top:65px;
    color:rgba(231,220,171,.45);
    font-family:Arial,sans-serif;
    font-size:11px;
    letter-spacing:3px;
}

/* ===== STARS ===== */

.stars span{
    position:fixed;
    width:3px;
    height:3px;
    border-radius:50%;
    background:#e8dc9c;
    opacity:.3;
    animation:twinkle 4s infinite ease-in-out;
    z-index:-2;
}

.stars span:nth-child(1){top:12%;left:18%;}
.stars span:nth-child(2){top:28%;left:82%;animation-delay:1s;}
.stars span:nth-child(3){top:65%;left:10%;animation-delay:2s;}
.stars span:nth-child(4){top:82%;left:75%;animation-delay:1.5s;}
.stars span:nth-child(5){top:48%;left:48%;animation-delay:3s;}
.stars span:nth-child(6){top:18%;left:60%;animation-delay:2.4s;}
.stars span:nth-child(7){top:75%;left:40%;animation-delay:.7s;}

@keyframes twinkle{
    0%,100%{
        opacity:.15;
        transform:scale(.8);
    }
    50%{
        opacity:.8;
        transform:scale(1.8);
    }
}
</style>
</head>

<body>

<div class="background">
    <div class="light one"></div>
    <div class="light two"></div>
    <div class="light three"></div>
    <div class="light four"></div>
    <div class="orbit"></div>
</div>

<div class="stars">
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
</div>

<main>

    <!-- INTRO -->
    <section class="intro">
        <div class="quote">
            <div class="quote-text">
                من از هراس مردن<br>
                در دست تو خُفتم.
            </div>

            <div class="author">
                احمدرضا احمدی
            </div>
        </div>
    </section>


    <!-- BRAND -->
    <div class="brand">
        خُرده نویسه‌ها
    </div>


    <!-- POETRY -->
    <section class="box">

        <button class="box-title" onclick="toggleBox(this)">
            شعر
            <span class="arrow">⌄</span>
        </button>

        <div class="content">

            <div class="inner">

                <button class="inner-button" onclick="openPoetry('classic')">
                    شعر کلاسیک
                </button>

                <button class="inner-button" onclick="openPoetry('modern')">
                    شعر نو
                </button>

            </div>

            <div id="poetry-message" class="poetry-note"></div>

        </div>

    </section>


    <!-- SHORT STORIES -->
    <section class="box">

        <button class="box-title" onclick="toggleBox(this)">
            داستان کوتاه
            <span class="arrow">⌄</span>
        </button>

        <div class="content">

            <div class="empty">
                فعلاً داستانی در این بخش نیست.
            </div>

        </div>

    </section>


    <!-- SONGS -->
    <section class="box">

        <button class="box-title" onclick="toggleBox(this)">
            ترانه‌ها
            <span class="arrow">⌄</span>
        </button>

        <div class="content">

            <div class="song-name">
                ترانه اول
            </div>

        </div>

    </section>


    <footer>
        GHAREN
    </footer>

</main>


<script>

function toggleBox(button){

    const box = button.parentElement;

    document.querySelectorAll(".box").forEach(item => {

        if(item !== box){
            item.classList.remove("open");
        }

    });

    box.classList.toggle("open");
}


function openPoetry(type){

    const message = document.getElementById("poetry-message");

    if(type === "classic"){

        message.innerHTML =
        "شعرهای کلاسیک اینجا قرار می‌گیرند.";

    }

    if(type === "modern"){

        message.innerHTML =
        "شعرهای نو اینجا قرار می‌گیرند.";

    }

}

</script>

</body>
</html>
