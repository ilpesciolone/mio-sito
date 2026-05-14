<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <title>Capolavoro</title>
    <style>
    body {
        margin: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background-color: #333; /* Colore di sfondo scuro per far risaltare il libro */
        overflow-x: hidden;
    }

    .book {
        position: relative;
        width: 90vw; 
        max-width: 400px; 
        height: 70vh; 
        max-height: 550px; 
        perspective: 1500px;
        transform-style: preserve-3d;
    }

    .page {
        position: absolute;
        width: 100%;
        height: 100%;
        transform-origin: left;
        transform-style: preserve-3d;
        transition: transform 0.8s cubic-bezier(0.645, 0.045, 0.355, 1);
        cursor: pointer;
    }

    .front, .back {
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
        overflow: hidden;
        box-shadow: inset 3px 0 10px rgba(0,0,0,0.1); /* Effetto ombra piega */
    }

    .front img, .back img {
        width: 100%;
        height: 100%;
        display: block;
        object-fit: cover; /* Evita che le immagini si schiaccino */
    }

    .unita-img {
        width: 200% !important; 
        max-width: none;
        position: absolute;
        height: 100%;
    }

    .back {
        transform: rotateY(180deg);
        background-color: #d2bc91; 
    }

    .flipped {
        transform: rotateY(-180deg);
    }
</style>
</head>
<body>

<div class="book">
    <div class="page-base">
        <img src="https://i.postimg.cc/CMtk43cW/paggina-unitefinale.jpg" class="unita-img" style="right: 0;">
    </div>

    <div class="page" id="p10" style="z-index: 1;" onclick="flip(this, 10)">
        <div class="front">
            <img src="https://i.postimg.cc/kgWQGTvq/paggina-unite08.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/CMtk43cW/paggina-unitefinale.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p9" style="z-index: 2;" onclick="flip(this, 9)">
        <div class="front">
            <img src="https://i.postimg.cc/pV0qMcqf/paggina-unite07.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/kgWQGTvq/paggina-unite08.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p8" style="z-index: 3;" onclick="flip(this, 8)">
        <div class="front">
            <img src="https://i.postimg.cc/1z6j90fp/paggina-unite06.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/pV0qMcqf/paggina-unite07.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p7" style="z-index: 4;" onclick="flip(this, 7)">
        <div class="front">
            <img src="https://i.postimg.cc/ZKHX1qp2/paggina-unite05.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/1z6j90fp/paggina-unite06.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p6" style="z-index: 5;" onclick="flip(this, 6)">
        <div class="front">
            <img src="https://i.postimg.cc/C16gTLWj/paggina-unite04.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/ZKHX1qp2/paggina-unite05.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p5" style="z-index: 6;" onclick="flip(this, 5)">
        <div class="front">
            <img src="https://i.postimg.cc/CKsht0hN/paggina-unite03.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/C16gTLWj/paggina-unite04.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p4" style="z-index: 7;" onclick="flip(this, 4)">
        <div class="front">
            <img src="https://i.postimg.cc/qqMzQR8r/paggina-unite02.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/CKsht0hN/paggina-unite03.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p3" style="z-index: 8;" onclick="flip(this, 3)">
        <div class="front">
            <img src="https://i.postimg.cc/3rSMdRf9/paggina-unite01.jpg" class="unita-img" style="right: 0;">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/qqMzQR8r/paggina-unite02.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p2" style="z-index: 9;" onclick="flip(this, 2)">
        <div class="front">
            <img src="https://i.postimg.cc/GhL0pDjq/paggina-seguente.jpg">
        </div>
        <div class="back">
            <img src="https://i.postimg.cc/3rSMdRf9/paggina-unite01.jpg" class="unita-img" style="left: 0;">
        </div>
    </div>

    <div class="page" id="p1" style="z-index: 10;" onclick="flip(this, 1)">
        <div class="front">
            <img src="https://i.postimg.cc/PrpGgHfH/copertina.jpg">
        </div>
        <div class="back"></div>
    </div>
</div>

<script>
    function flip(element, index) {
        element.classList.toggle('flipped');
        
        if (element.classList.contains('flipped')) {
            setTimeout(() => { 
                element.style.zIndex = index; 
            }, 400);
        } else {
            setTimeout(() => { 
                // Aggiornato per 10 pagine mobili: base 11
                element.style.zIndex = (11 - index); 
            }, 400);
        }
    }
</script>

</body>
</html>
