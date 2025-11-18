
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Doll</title>

<style>
    body {
        margin: 0;
        padding: 0;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: #000000ff;
        overflow: hidden;
        font-family: "Poppins", sans-serif;
        color: white;
    }

    #bg {
        position: fixed;
        top: 0;
        left: 0;
        height: 100vh;
        width: 100vw;
        background-image: url('https://files.catbox.moe/c2njbn.jpg');
        background-size: cover;
        background-position: center;
        filter: blur(0.35px) brightness(0.8);
        opacity: 0;
        transition: opacity 1.8s ease-in-out;
        z-index: -1;
    }

    #openBtn {
        padding: 15px 30px;
        font-size: 20px;
        background: #e7e7e7cc;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        transition: 0.3s;
    }

    #openBtn:hover {
        background: white;
    }

    #messageBox {
        text-align: center;
        opacity: 0;
        transition: opacity 2s ease-in-out;
        display: none;
        margin-top: 130px;
        
    }

    .title {
        font-size: 58px;
        font-weight: 700;
        margin-bottom: 10px;
    }

    .subtitle {
        font-size: 34px;
        opacity: 0.9;
    }
</style>
</head>

<body>

<div id="bg"></div>

<button id="openBtn" onclick="reveal()">Click to Open</button>

<div id="messageBox">
    <div class="title">Happy Princess Day</div>
    <div class="subtitle">From Abhinav💌</div>
</div>

<audio id="bgMusic">
    <source src="https://files.catbox.moe/lwpmk7.mp3" type="audio/mp3">
</audio>

<script>
function reveal() {
    document.getElementById("openBtn").style.display = "none";
    document.getElementById("bg").style.opacity = "1";

    const msg = document.getElementById("messageBox");
    msg.style.display = "block";
    setTimeout(() => { msg.style.opacity = "1"; }, 50);

    const music = document.getElementById("bgMusic");
    music.volume = 0.25;
    music.play().catch(err => console.log("Autoplay blocked:", err));
}
</script>

</body>
</html>
