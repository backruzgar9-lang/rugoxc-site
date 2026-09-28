# rugoxc-site
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>RUGOXC OFFICIAL</title>

    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap" rel="stylesheet">

    <style>

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: #000;
            color: white;
            font-family: Arial, sans-serif;
            overflow-x: hidden;
        }


        /* =========================
           VİDEO ARKA PLAN
        ========================= */

        .background-video {
            position: fixed;
            top: 0;
            left: 0;

            width: 100%;
            height: 100%;

            object-fit: cover;

            z-index: -5;
        }

        .video-overlay {
            position: fixed;
            inset: 0;

            background: rgba(0, 0, 0, 0.60);

            z-index: -4;

            pointer-events: none;
        }


        /* =========================
           HAREKETLİ GRID
        ========================= */

        .grid {
            position: fixed;
            inset: 0;

            z-index: -3;

            background-image:
                linear-gradient(
                    rgba(255,255,255,0.05) 1px,
                    transparent 1px
                ),
                linear-gradient(
                    90deg,
                    rgba(255,255,255,0.05) 1px,
                    transparent 1px
                );

            background-size: 60px 60px;

            animation: gridMove 12s linear infinite;

            pointer-events: none;
        }

        @keyframes gridMove {
            from {
                transform: translate(0, 0);
            }

            to {
                transform: translate(60px, 60px);
            }
        }


        /* =========================
           PARÇACIKLAR
        ========================= */

        .particles {
            position: fixed;
            inset: 0;

            pointer-events: none;

            z-index: -2;
        }

        .particle {
            position: absolute;

            width: 4px;
            height: 4px;

            background: white;

            box-shadow: 0 0 12px white;

            animation: particleMove 7s linear infinite;
        }

        .particle:nth-child(1) {
            left: 10%;
            bottom: -20px;
            animation-delay: 0s;
        }

        .particle:nth-child(2) {
            left: 30%;
            bottom: -20px;
            animation-delay: 2s;
        }

        .particle:nth-child(3) {
            left: 50%;
            bottom: -20px;
            animation-delay: 4s;
        }

        .particle:nth-child(4) {
            left: 70%;
            bottom: -20px;
            animation-delay: 1s;
        }

        .particle:nth-child(5) {
            left: 90%;
            bottom: -20px;
            animation-delay: 3s;
        }

        @keyframes particleMove {

            0% {
                transform: translateY(0) scale(0);
                opacity: 0;
            }

            20% {
                opacity: 1;
                transform: translateY(-20vh) scale(1);
            }

            100% {
                transform: translateY(-110vh) scale(0.5);
                opacity: 0;
            }
        }


        /* =========================
           ÜST MENÜ
        ========================= */

        header {
            height: 90px;

            padding: 0 7%;

            display: flex;

            align-items: center;

            justify-content: space-between;

            background: rgba(0,0,0,0.70);

            border-bottom: 1px solid rgba(255,255,255,0.25);

            backdrop-filter: blur(10px);

            position: relative;

            z-index: 10;
        }

        .logo {
            font-family: "Press Start 2P", monospace;

            font-size: 17px;

            color: white;

            text-shadow: 0 0 12px white;
        }

        nav {
            display: flex;
            gap: 30px;
        }

        nav a {
            color: white;

            text-decoration: none;

            font-family: "Press Start 2P", monospace;

            font-size: 10px;

            transition: 0.3s;
        }

        nav a:hover {
            color: #aaa;

            text-shadow:
                0 0 10px white;
        }


        /* =========================
           ANA SAYFA
        ========================= */

        .hero {
            min-height: calc(100vh - 90px);

            display: flex;

            flex-direction: column;

            align-items: center;

            justify-content: center;

            text-align: center;

            padding: 70px 20px;

            position: relative;

            z-index: 2;
        }


        /* =========================
           RUGOXC
        ========================= */

        .title {
            font-family: "Press Start 2P", monospace;

            font-size: clamp(35px, 8vw, 95px);

            /* SADECE SİYAH - BEYAZ */
            background: linear-gradient(
                120deg,
                #ffffff 0%,
                #ffffff 20%,
                #777777 35%,
                #000000 50%,
                #777777 65%,
                #ffffff 80%,
                #ffffff 100%
            );

            background-size: 300% 300%;

            -webkit-background-clip: text;
            background-clip: text;

            color: transparent;

            animation: blackWhite 4s ease-in-out infinite;

            filter:
                drop-shadow(0 0 8px white)
                drop-shadow(0 0 18px black);

            margin-bottom: 25px;
        }

        @keyframes blackWhite {

            0% {
                background-position: 0% 50%;
            }

            50% {
                background-position: 100% 50%;
            }

            100% {
                background-position: 0% 50%;
            }
        }


        /* =========================
           OFFICIAL
        ========================= */

        .official {
            font-family: "Press Start 2P", monospace;

            font-size: clamp(20px, 4vw, 45px);

            color: white;

            text-shadow:
                4px 4px 0 #333,
                0 0 10px white,
                0 0 30px white;

            animation: officialMove 2s ease-in-out infinite alternate;
        }

        @keyframes officialMove {

            from {
                transform: translateY(0);
            }

            to {
                transform: translateY(-8px);
            }
        }


        .subtitle {
            margin-top: 30px;

            font-size: 18px;

            color: #ddd;

            text-shadow: 0 3px 10px black;
        }


        /* =========================
           TIKTOK KUTUSU
        ========================= */

        .tiktok-card {
            width: min(650px, 92%);

            margin-top: 60px;

            padding: 45px 30px;

            background: rgba(0,0,0,0.82);

            border: 2px solid white;

            box-shadow:
                0 0 25px rgba(255,255,255,0.25),
                inset 0 0 30px rgba(255,255,255,0.05);

            transition: 0.4s;

            position: relative;

            overflow: hidden;
        }

        .tiktok-card::before {
            content: "";

            position: absolute;

            top: 0;
            left: -100%;

            width: 100%;
            height: 2px;

            background: white;

            animation: cardLine 3s linear infinite;
        }

        @keyframes cardLine {

            0% {
                left: -100%;
            }

            100% {
                left: 100%;
            }
        }

        .tiktok-card:hover {
            transform: translateY(-10px);

            box-shadow:
                0 0 45px rgba(255,255,255,0.45);
        }

        .tiktok-card h2 {
            font-family: "Press Start 2P", monospace;

            font-size: 16px;

            margin-bottom: 28px;
        }

        .username {
            font-family: "Press Start 2P", monospace;

            font-size: 25px;

            margin-bottom: 35px;

            text-shadow: 0 0 15px white;
        }


        /* =========================
           TIKTOK BUTONU
        ========================= */

        .tiktok-button {
            display: inline-block;

            padding: 18px 30px;

            background: white;

            color: black;

            text-decoration: none;

            font-family: "Press Start 2P", monospace;

            font-size: 11px;

            border: 2px solid white;

            transition: 0.3s;
        }

        .tiktok-button:hover {
            background: black;

            color: white;

            box-shadow: 0 0 25px white;

            transform: scale(1.05);
        }


        /* =========================
           FOOTER
        ========================= */

        footer {
            text-align: center;

            padding: 35px 20px;

            background: rgba(0,0,0,0.80);

            border-top: 1px solid rgba(255,255,255,0.25);

            color: #aaa;

            font-family: "Press Start 2P", monospace;

            font-size: 9px;

            position: relative;

            z-index: 5;
        }


        /* =========================
           TELEFON
        ========================= */

        @media (max-width: 700px) {

            header {
                height: auto;

                padding: 25px 20px;

                flex-direction: column;

                gap: 20px;
            }

            nav {
                gap: 15px;

                flex-wrap: wrap;

                justify-content: center;
            }

            nav a {
                font-size: 7px;
            }

            .tiktok-card {
                padding: 35px 15px;
            }

            .username {
                font-size: 16px;
            }

            .subtitle {
                font-size: 14px;
            }
        }

    </style>

</head>


<body>


    <!-- =========================
         ARKA PLAN VİDEOSU
    ========================= -->

    <video
        class="background-video"
        autoplay
        muted
        loop
        playsinline
    >

        <source
            src="background.mp4"
            type="video/mp4"
        >

    </video>


    <div class="video-overlay"></div>

    <div class="grid"></div>


    <!-- =========================
         PARÇACIKLAR
    ========================= -->

    <div class="particles">

        <div class="particle"></div>

        <div class="particle"></div>

        <div class="particle"></div>

        <div class="particle"></div>

        <div class="particle"></div>

    </div>


    <!-- =========================
         MENÜ
    ========================= -->

    <header>

        <div class="logo">
            RUGOXC
        </div>

        <nav>

            <a href="#anasayfa">
                ANA SAYFA
            </a>

            <a href="#tiktok">
                TIKTOK
            </a>

            <a href="#iletisim">
                İLETİŞİM
            </a>

        </nav>

    </header>


    <!-- =========================
         ANA ALAN
    ========================= -->

    <main
        class="hero"
        id="anasayfa"
    >

        <div class="title">
            RUGOXC
        </div>

        <div class="official">
            OFFICIAL
        </div>

        <p class="subtitle">
            Welcome to my official website.
        </p>


        <!-- =========================
             TIKTOK
        ========================= -->

        <div
            class="tiktok-card"
            id="tiktok"
        >

            <h2>
                TIKTOK HESABIM
            </h2>

            <div class="username">
                @rugoxc
            </div>

            <a
                class="tiktok-button"
                href="https://www.tiktok.com/@rugoxc"
                target="_blank"
            >
                TIKTOK'A GİT →
            </a>

        </div>

    </main>


    <!-- =========================
         ALT KISIM
    ========================= -->

    <footer id="iletisim">

        RUGOXC OFFICIAL

        <br>
        <br>

        © 2026 TÜM HAKLARI SAKLIDIR.

    </footer>


</body>

</html>
