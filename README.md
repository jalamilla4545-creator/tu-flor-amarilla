# tu-flor-amarilla
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Una sorpresa 🌻</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    min-height: 100vh;
    overflow: hidden;
    font-family: Arial, sans-serif;
    background: linear-gradient(180deg, #fff8c9, #ffe680, #fff3a6);
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.contenedor {
    position: relative;
    z-index: 10;
    padding: 25px;
    width: 100%;
    max-width: 500px;
}

#sorpresa {
    display: none;
}

h1 {
    font-size: 42px;
    color: #d89b00;
    margin: 10px 0;
    animation: aparecer 1.5s ease;
}

h2 {
    font-size: 30px;
    color: #8a6200;
    margin: 15px 0;
}

.mensaje {
    font-size: 22px;
    color: #654d00;
    line-height: 1.5;
}

button {
    border: none;
    background: linear-gradient(135deg, #ffd21f, #f5a900);
    color: white;
    font-size: 22px;
    font-weight: bold;
    padding: 18px 30px;
    border-radius: 50px;
    box-shadow: 0 8px 20px rgba(0,0,0,.2);
    cursor: pointer;
}

button:active {
    transform: scale(.95);
}

.flor {
    position: fixed;
    top: -60px;
    font-size: 35px;
    z-index: 1;
    pointer-events: none;
    animation: caer linear forwards;
}

.corazon {
    font-size: 55px;
    animation: latir 1.2s infinite;
}

@keyframes caer {
    0% {
        transform: translateY(-60px) rotate(0deg);
        opacity: 1;
    }
    100% {
        transform: translateY(110vh) rotate(360deg);
        opacity: .9;
    }
}

@keyframes latir {
    0%,100% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.2);
    }
}

@keyframes aparecer {
    from {
        opacity: 0;
        transform: scale(.5);
    }
    to {
        opacity: 1;
        transform: scale(1);
    }
}

@media (max-width: 500px) {
    h1 {
        font-size: 34px;
    }

    h2 {
        font-size: 25px;
    }

    .mensaje {
        font-size: 19px;
    }
}
</style>
</head>

<body>

<div class="contenedor" id="inicio">
    <div class="corazon">💛</div>

    <h1>Una sorpresa para ti 🌻</h1>

    <p class="mensaje">
        Tengo algo especial que quiero regalarte...
    </p>

    <button onclick="abrirSorpresa()">
        Abrir sorpresa 💛
    </button>
</div>

<div class="contenedor" id="sorpresa">

    <div class="corazon">🌻</div>

    <h1>¡Feliz 21 de septiembre!</h1>

    <h2>🌻 Toma tu flor amarilla 🌻</h2>

    <p class="mensaje">
        Que esta flor amarilla te recuerde<br>
        lo especial que eres. 💛
        <br><br>
        ✨ Espero que tengas un día muy bonito ✨
    </p>

    <div style="font-size:55px;">
        🌻 💛 🌻 💛 🌻
    </div>

</div>

<script>

function abrirSorpresa() {

    document.getElementById("inicio").style.display = "none";
    document.getElementById("sorpresa").style.display = "block";

    // Crear muchas flores cayendo
    for (let i = 0; i < 35; i++) {
        crearFlor();
    }

    // Seguir creando flores
    setInterval(crearFlor, 700);
}

function crearFlor() {

    const flor = document.createElement("div");

    flor.className = "flor";

    const flores = ["🌻", "🌼", "💛", "🌻", "🌼"];

    flor.innerHTML = flores[Math.floor(Math.random() * flores.length)];

    flor.style.left = Math.random() * 100 + "vw";

    flor.style.fontSize = (25 + Math.random() * 25) + "px";

    flor.style.animationDuration = (4 + Math.random() * 5) + "s";

    document.body.appendChild(flor);

    setTimeout(() => {
        flor.remove();
    }, 10000);
}

</script>

</body>
</html>