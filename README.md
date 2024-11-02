
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
            top: 20px;
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
            margin-top: 70px; /* Espaço para o header fixo */
            transition: margin-left 0.3s;
        }
        .sidebar.active {
            transform: translateX(0);
        }
        .main-content.active {
            margin-left: 250px;
        }
        .carousel {
            position: relative;
            max-width: 500px;
            height: 300px;
            margin: 2rem auto;
            overflow: hidden;
            border: 1px solid #ccc;
            border-radius: 8px;
        }
        .carousel-images {
            display: flex;
            transition: transform 0.5s ease-in-out;
            width: 500%;
        }
        .carousel-image {
            min-width: 100%;
            height: 150px;
        }
        .carousel-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .carousel-button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
            font-size: 1.5rem;
        }
        .carousel-button.prev {
            left: 10px;
        }
        .carousel-button.next {
            right: 10px;
        }
        .carousel-button:hover {
            background-color: rgba(0, 0, 0, 0.7);
        }
        .carousel-indicators {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 5px;
        }
        .carousel-indicator {
            width: 10px;
            height: 10px;
            background-color: rgba(255, 255, 255, 0.7);
            border-radius: 50%;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .carousel-indicator.active {
            background-color: #4CAF50;
        }
        figcaption {
            font-size: 0.8rem;
            color: #555;
            text-align: center;
            margin-top: 0.5rem;
        }

        /* Estilos responsivos para dispositivos móveis */
        @media (max-width: 768px) {
            .carousel {
                height: 200px;
            }
            .carousel-image {
                height: 200px;
            }
            .sidebar {
                width: 200px;
                padding-top: 50px;
            }
            .main-content.active {
                margin-left: 200px;
            }
            .carousel-button {
                font-size: 1rem;
                padding: 0.25rem 0.75rem;
            }
            figcaption {
                font-size: 0.7rem;
            }
        }
        
        @media (max-width: 480px) {
            .carousel {
                height: 150px;
            }
            .carousel-image {
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

    <figure class="carousel">
        <div class="carousel-images" id="carousel-images">
            <div class="carousel-image">
                <img src="imagens/imagem1.jpg" alt="Imagem 1 - Floresta Amazônica">
            </div>
            <div class="carousel-image">
                <img src="imagens/imagem2.jpg" alt="Imagem 2 - Monitoramento Ambiental">
            </div>
            <!-- Adicione mais imagens se necessário -->
        </div>
        <button class="carousel-button prev" onclick="prevSlide()">❮</button>
        <button class="carousel-button next" onclick="nextSlide()">❯</button>
        <div class="carousel-indicators" id="carousel-indicators">
            <span class="carousel-indicator" onclick="showSlide(0)"></span>
            <span class="carousel-indicator" onclick="showSlide(1)"></span>
        </div>
    </figure>
    <figcaption>Fig. 1 - Carrossel de imagens representando os temas de preservação e monitoramento dos biomas amazônicos.</figcaption>
</div>

<script>
    function toggleSidebar() {
        const sidebar = document.getElementById('sidebar');
        const mainContent = document.getElementById('main-content');
        sidebar.classList.toggle('active');
        mainContent.classList.toggle('active');
    }

    let currentIndex = 0;

    function showSlide(index) {
        const slides = document.getElementById('carousel-images');
        const indicators = document.getElementById('carousel-indicators').children;
        const totalSlides = slides.children.length;
        if (index >= totalSlides) {
            currentIndex = 0;
        } else if (index < 0) {
            currentIndex = totalSlides - 1;
        } else {
            currentIndex = index;
        }
        slides.style.transform = `translateX(-${currentIndex * 100}%)`;
        Array.from(indicators).forEach((indicator, i) => {
            indicator.classList.toggle('active', i === currentIndex);
        });
    }

    function nextSlide() {
        showSlide(currentIndex + 1);
    }

    function prevSlide() {
        showSlide(currentIndex - 1);
    }

    // Automatic slide change every 5 seconds
    setInterval(nextSlide, 5000);
</script>

</body>
</html>
