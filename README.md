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

        /* Responsividade */
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
            .video-container {
                width: 100%;
                padding-bottom: 56.25%; /* Aspect ratio 16:9 */
                position: relative;
                height: 0;
            }
            .video-container iframe {
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
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
    <span class="menu-toggle" onclick="toggleMenu()">☰ Menu</span>
    <div class="menu-bar" id="menu-bar">
        <a href="Biomas/projetos.html">Projetos</a>
        <a href="Biomas/dados.html">Dados da Poluição do Ar</a>
        <a href="Biomas/solucoes.html">Soluções</a>
        <a href="Biomas/ecomonitor.html">Ecomonitor</a> <!-- Novo link -->
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
    <a href="Biomas/ecomonitor.html" onclick="toggleSidebar()">Ecomonitor</a> <!-- Novo link -->
</div>

<div class="main-content" id="main-content">
    <section id="introducao">
        <h2>Bem-vindo ao site Biomas da Amazônia</h2>
        <p>Recentemente secas históricas acontecem com mais frequência, nos últimos anos, as principais hidrovias da amazônia secam muito além dos previsto, pesquisas apontam, o desmatamento, a agropecuária e a poluição do ar como principais causadores destes fenômenos climáticos, O reflorestamento surge como uma ação necessária para garantir a conservação da biodiversidade e equilibrar as mudanças climáticas. No entanto, ainda se faz necessários que outras atividades como o monitoramento, prevenção, incentivo e desenvolvimento de atividade que desenvolvam a bioeconomia, sejam criados e que principalmente trabalhem em conjunto, para recuperar uma área devastada, sem fazer com que se torne improdutiva, em casos como o da agropecuária.</p>
    </section>

    <!-- Vídeo Responsivo -->
    <figure class="video-container">
        <iframe src="https://www.youtube.com/embed/4MJvepYiBVk" 
                title="YouTube video player" frameborder="0" 
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
                allowfullscreen></iframe>
    </figure>
    <figcaption>Fig. 1 - Vídeo representando os temas de preservação e monitoramento dos biomas amazônicos.</figcaption>

    <!-- Linha do Tempo -->
    <div class="timeline">
        <h3>Linha do Tempo da Degradação Amazônica</h3>
        <div class="timeline-slider">
            <img src="imagens/fogo.png" alt="Fogo" id="fireIcon">
            <input type="range" id="timelineSlider" min="1" max="6" value="1" oninput="updateTimeline()">
            <div class="timeline-bar" id="timelineBar"></div>
        </div>
        <div id="timelineDisplay">Ano: 2000 - Início da linha do tempo</div>
    </div>

    <div class="image-display">
        <img src="imagens/evento1.jpg" alt="Imagem da Amazônia" id="timelineImage" onclick="showDetails()">
        <div class="image-details" id="imageDetails"></div>
    </div>
</div>

<script>
    function toggleMenu() {
        const menu = document.getElementById('menu-bar');
        menu.style.display = menu.style.display === 'flex' ? 'none' : 'flex';
    }
    function toggleSidebar() {
        document.getElementById("sidebar").classList.toggle("active");
        document.getElementById("main-content").classList.toggle("active");
    }

    function updateTimeline() {
        const sliderValue = document.getElementById("timelineSlider").value;
        const timelineDisplay = document.getElementById("timelineDisplay");
        const timelineImage = document.getElementById("timelineImage");

        const events = {
            "1": { year: "2000", image: "imagens/evento1.jpg" },
            "2": { year: "2005", image: "imagens/evento2.jpg" },
            "3": { year: "2010", image: "imagens/evento3.jpg" },
            "4": { year: "2015", image: "imagens/evento4.jpg" },
            "5": { year: "2020", image: "imagens/evento5.jpg" },
            "6": { year: "2024", image: "imagens/evento6.jpg" }
        };

        const currentEvent = events[sliderValue];
        timelineDisplay.innerText = Ano: ${currentEvent.year};
        timelineImage.src = currentEvent.image;
    }
    
</script>
</body>
</html>
