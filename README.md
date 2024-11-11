
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Início Biomas da Amazônia</title>
    <style>
        /* Estilos básicos */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f3f3f3;
            scroll-behavior: smooth;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 1rem;
            text-align: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 2;
        }

        /* Barra de menu centralizada */
        .menu-bar {
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: absolute;
            top: 60px;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            background-color: #4CAF50;
        }

        .menu-bar a {
            color: white;
            padding: 10px 20px;
            text-decoration: none;
            font-size: 1rem;
            display: block;
            width: 100%;
            text-align: center;
        }

        .menu-bar a:hover {
            background-color: #575757;
        }

        /* Título com imagem de fundo */
        .title-section {
            position: relative;
            text-align: center;
            background-image: url('imagens/feira.jpg'); /* Caminho da imagem */
            background-size: cover;
            background-position: center;
            padding: 200px 0;
            color: rgb(255, 255, 255);
        }

        /* Sobreposição de cor para ofuscar a imagem */
        .title-section::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1;
        }

        .title-section h2, .title-section p, .title-section .subtitle {
            position: relative;
            z-index: 2;
        }

        /* Estilos da linha do tempo */
        .timeline {
            padding: 2rem;
            text-align: center;
        }

        .timeline h3 {
            margin-bottom: 1rem;
        }

        .timeline-slider {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .timeline-slider input[type="range"] {
            width: 70%;
            cursor: pointer;
        }

        .timeline-bar {
            height: 5px;
            background: linear-gradient(to right, #ff7f50, #ff4500);
            border-radius: 10px;
            transition: width 0.5s ease-in-out;
        }

        /* Área de detalhes da imagem */
        .image-display {
            margin-top: 1rem;
            text-align: center;
        }

        .image-display img {
            width: 100%;
            max-width: 500px;
            border-radius: 10px;
            transition: opacity 0.3s;
            cursor: pointer;
        }

        .sidebar {
            height: 100%;
            width: 250px;
            position: fixed;
            top: 0;
            left: 0;
            background-color: #333;
            overflow-x: hidden;
            transition: transform 0.3s;
            padding-top: 60px;
            transform: translateX(-250px);
            z-index: 2;
        }

        .sidebar a {
            padding: 15px 25px;
            text-decoration: none;
            font-size: 1rem;
            color: white;
            display: block;
            transition: 0.3s;
        }

        .sidebar a:hover {
            background-color: #575757;
        }

        .main-content {
            padding: 2rem 1.5rem;
            margin-top: 60px;
            transition: margin-left 0.3s;
        }

        .sidebar.active {
            transform: translateX(0);
        }

        .main-content.active {
            margin-left: 250px;
        }

        /* Estilos responsivos */
        @media (max-width: 768px) {
            .menu-bar {
                width: 100%;
                position: absolute;
                top: 60px;
                left: 50%;
                transform: translateX(-50%);
                padding: 0;
            }
            .sidebar {
                width: 200px;
                padding-top: 50px;
            }
            .main-content.active {
                margin-left: 200px;
            }
        }

        /* Diminui o tamanho do ícone de fogo */
        #fireIcon {
            width: 30px;
            height: auto;
        }
    </style>
</head>
<body>

<header>
    <!-- Botão para abrir o menu -->
    <span class="menu-toggle" onclick="toggleMenu()">☰ Menu</span>
    <div class="menu-bar" id="menu-bar">
        <a href="Biomas/projetos.html">Projetos</a>
        <a href="Biomas/dados.html">Dados da Poluição do Ar</a>
        <a href="Biomas/solucoes.html">Soluções</a>
    </div>
</header>

<section class="title-section">
    <h2>Feira Tecnológica - FUCAPI</h2>
    <p>Manaus, Brasil</p>
    <p class="subtitle">Ecomonitor - NBE1</p>
</section>

<div class="sidebar" id="sidebar">
    <a href="Biomas/projetos.html" onclick="toggleSidebar()">Projetos</a>
    <a href="Biomas/dados.html" onclick="toggleSidebar()">Dados da Poluição do Ar</a>
    <a href="Biomas/solucoes.html" onclick="toggleSidebar()">Soluções</a>
</div>

<div class="main-content" id="main-content">
    <section id="introducao">
        <h2>Bem-vindo ao site Biomas da Amazônia</h2>
        <p>Aqui você encontrará informações sobre os projetos de monitoramento de poluição do ar e as soluções para combater o impacto ambiental.</p>
    </section>

    <figure class="video-container">
        <video controls>
            <source src="videos/seu_video.mp4" type="video/mp4">
        </video>
    </figure>
    <figcaption>Fig. 1 - Vídeo representando os temas de preservação e monitoramento dos biomas amazônicos.</figcaption>

    <!-- Linha do Tempo -->
    <div class="timeline">
        <h3>Linha do Tempo da Degradação Amazônica</h3>
        <div class="timeline-slider">
            <img src="imagens/fogo.png" alt="Fogo" id="fireIcon">
            <input type="range" id="timelineSlider" min="2000" max="2024" value="2000" oninput="updateTimeline()">
            <div class="timeline-bar" id="timelineBar"></div>
        </div>
        <div id="timelineDisplay">Ano: 2000 - Início da linha do tempo</div>
    </div>

    <div class="image-display">
        <img src="imagens/imagem2000.jpg" alt="Imagem da Amazônia" id="timelineImage" onclick="showDetails()">
        <div class="image-details" id="imageDetails"></div>
    </div>
</div>

<script>
    const images = {
        "2000": { src: "imagens/evento1.jpg", details: "Ano 2000 - Início do desmatamento intensivo." },
        "2005": { src: "imagens/evento2.jpg", details: "Ano 2005 - Expansão agropecuária aumenta a área desmatada." },
        "2010": { src: "imagens/evento3.jpg", details: "Ano 2010 - Políticas de preservação são implementadas, mas o desmatamento persiste." },
        "2015": { src: "imagens/evento4.jpg", details: "Ano 2015 - Queimadas e desmatamento ilegal continuam." },
        "2020": { src: "imagens/evento5.jpg", details: "Ano 2020 - Queimadas intensificadas devido à falta de fiscalização." },
        "2024": { src: "imagens/evento6.jpg", details: "Ano 2024 - Medidas de controle são introduzidas, mas o impacto é lento." }
    };

    function updateTimeline() {
        const slider = document.getElementById('timelineSlider');
        const year = slider.value;
        document.getElementById('timelineDisplay').textContent = `Ano: ${year} - ${images[year].details}`;
        document.getElementById('timelineImage').src = images[year].src;

        // Atualiza a largura da barra da linha do tempo
        const percentage = ((year - 2000) / (2024 - 2000)) * 100;
        document.getElementById('timelineBar').style.width = percentage + '%';
    }

    function toggleSidebar() {
        document.getElementById('sidebar').classList.toggle('active');
        document.getElementById('main-content').classList.toggle('active');
    }

    function toggleMenu() {
        const menuBar = document.getElementById('menu-bar');
        menuBar.style.display = menuBar.style.display === 'flex' ? 'none' : 'flex';
    }
</script>
</body>
</html>
