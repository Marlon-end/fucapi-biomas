<!DOCTYPE html>
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
        .sidebar-toggle {
            position: fixed;
            top: 15px;
            left: 20px;
            font-size: 1.5rem;
            cursor: pointer;
            color: white;
            background-color: #4CAF50;
            padding: 5px 10px;
            border-radius: 5px;
            z-index: 3;
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
            margin-top: 60px; /* Espaço ajustado para o header fixo */
            transition: margin-left 0.3s;
        }
        .sidebar.active {
            transform: translateX(0);
        }
        .main-content.active {
            margin-left: 250px;
        }
        .video-container {
            position: relative;
            max-width: 1000px;
            height: 300px;
            margin: 2rem auto;
            overflow: hidden;
            border: 1px solid #ccc;
            border-radius: 8px;
        }
        .video-container video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        figcaption {
            font-size: 0.8rem;
            color: #555;
            text-align: center;
            margin-top: 0.5rem;
        }

        /* Estilos para a linha do tempo */
        .timeline {
            margin: 2rem auto;
            max-width: 600px;
            text-align: center;
        }
        .timeline input[type="range"] {
            width: 100%;
        }
        .timeline-display {
            font-size: 1.2rem;
            color: #333;
            margin-top: 1rem;
            min-height: 2em;
        }

        /* Estilos responsivos para dispositivos móveis */
        @media (max-width: 768px) {
            .video-container {
                height: 200px;
            }
            .sidebar {
                width: 200px;
                padding-top: 50px;
            }
            .main-content.active {
                margin-left: 200px;
            }
            figcaption {
                font-size: 0.7rem;
            }
        }
        
        @media (max-width: 480px) {
            .video-container {
                height: 150px;
            }
            .sidebar {
                width: 180px;
            }
            .main-content.active {
                margin-left: 180px;
            }
            header h1 {
                font-size: 1.2rem;
            }
            .sidebar-toggle {
                top: 10px; /* Ajuste de posição para dispositivos menores */
            }
        }
    </style>
</head>
<body>

<header>
    <h1>Início Biomas da Amazônia</h1>
</header>
<span class="sidebar-toggle" onclick="toggleSidebar()">☰ Menu</span>

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

    <!-- Seção de Linha do Tempo -->
    <div class="timeline">
        <h3>Linha do Tempo da Degradação Amazônica</h3>
        <input type="range" id="timelineSlider" min="2000" max="2024" value="2000" oninput="updateTimeline()">
        <div class="timeline-display" id="timelineDisplay">Ano: 2000 - Início da linha do tempo</div>
    </div>
</div>

<script>
    function toggleSidebar() {
        const sidebar = document.getElementById('sidebar');
        const mainContent = document.getElementById('main-content');
        sidebar.classList.toggle('active');
        mainContent.classList.toggle('active');
    }

    function updateTimeline() {
        const slider = document.getElementById('timelineSlider');
        const display = document.getElementById('timelineDisplay');
        const year = slider.value;

        // Mensagens baseadas no ano selecionado
        const messages = {
            "2000": "Ano: 2000 - Início da linha do tempo.",
            "2005": "Ano: 2005 - Aumento da área desmatada devido a expansão agropecuária.",
            "2010": "Ano: 2010 - Implementação de políticas para preservação, mas degradação continua.",
            "2015": "Ano: 2015 - Desmatamento ilegal ainda em alta.",
            "2020": "Ano: 2020 - Intensificação de queimadas e desmatamento.",
            "2024": "Ano: 2024 - Medidas de recuperação ambiental em andamento."
        };

        // Atualizar a exibição com base no valor do slider
        display.textContent = messages[year] || `Ano: ${year} - Dados não disponíveis para esse ano.`;
    }
</script>

</body>
</html>
