<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>red.kamel</title>
    <link href="https://fonts.googleapis.com/css2?family=Concert+One&display=swap" rel="stylesheet">
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            color: #fff;
            background-color: #f8fcf7;
        }

        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 0;
            z-index: 1000;
            transition: background 0.3s, padding 0.3s;
        }

        header.scrolled {
            background: rgba(0, 0, 0, 0.9);
            padding: 10px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
        }

        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }

        nav ul li {
            margin-left: 20px;
        }

        nav ul li a {
            text-decoration: none;
            color: #fff;
            padding: 5px 10px;
            transition: background 0.3s;
        }

        nav ul li a:hover {
            background: #444;
            border-radius: 5px;
        }

        .buy-tickets {
            background: #ff4b2b;
            border-radius: 5px;
            padding: 5px 15px;
        }

        .main-content {
            background: url('3.jpg') no-repeat center center/cover;
            background-attachment: scroll;
        }

        .hero {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
        }

        .hero .overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
        }

        .hero .content {
            position: relative;
            z-index: 1;
            animation: fadeIn 2s ease-in-out;
        }

        .hero .content h1,
        .hero .content p {
            color: rgb(23, 76, 23);
        }

        .hero h1 {
            font-size: 64px;
            margin: 0;
            font-family: 'Concert One', cursive;
            animation: slideInFromLeft 1s ease-in-out;
        }

        .hero p {
            font-size: 24px;
            margin: 10px 0;
            animation: slideInFromRight 1s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
        }

        @keyframes slideInFromLeft {
            from {
                transform: translateX(-100%);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes slideInFromRight {
            from {
                transform: translateX(100%);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .ticket-info {
            padding: 50px 0;
            background: rgba(226, 188, 19, 0.195);
        }

        .ticket-info .container {
            background-color: rgb(80, 138, 46);
            border-radius: 5px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
            padding: 20px;
        }

        .concert-image {
            width: 100%;
            height: auto;
            border-radius: 5px;
            margin-bottom: 20px;
            opacity: 0;
            transform: translateY(50px);
            animation: fadeInUp 1s forwards;
        }

        .prices {
            opacity: 0;
            transform: translateY(50px);
            animation: fadeInUp 1s forwards 0.5s;
        }

        .pass {
            background-color: #fff;
            border: 1px solid rgb(250, 244, 65);
            border-radius: 5px;
            padding: 20px;
            margin-bottom: 20px;
            opacity: 0;
            transform: translateY(50px);
            animation: fadeInUp 1s forwards;
        }

        .pass:nth-child(2) {
            animation-delay: 1s;
        }

        .pass:nth-child(3) {
            animation-delay: 1.5s;
        }

        .pass:nth-child(4) {
            animation-delay: 2s;
        }

        .pass h2 {
            color: rgb(17, 17, 17);
            font-size: 24px;
            margin-top: 0;
            margin-bottom: 10px;
        }

        .pass p {
            color: rgb(139, 0, 0);
            font-size: 16px;
            margin-top: 0;
        }

        footer {
            background: #333;
            color: #fff;
            text-align: center;
            padding: 20px 0;
            position: relative;
            bottom: 0;
            width: 100%;
        }

        footer a {
            color: #ff4b2b;
            text-decoration: none;
        }

        footer a:hover {
            text-decoration: underline;
        }

        footer .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        footer .container div {
            margin: 10px 0;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 48px;
            }

            .hero p {
                font-size: 20px;
            }

            .ticket-info .container {
                padding: 10px;
            }

            .pass {
                padding: 10px;
            }
        }

        @media (max-width: 576px) {
            .hero h1 {
                font-size: 36px;
            }

            .hero p {
                font-size: 18px;
            }

            nav ul {
                flex-direction: column;
                align-items: flex-start;
            }

            nav ul li {
                margin-left: 0;
                margin-top: 10px;
            }

            nav ul li a {
                padding: 10px 15px;
            }

            .ticket-info .container {
                padding: 5px;
            }

            .pass {
                padding: 10px;
            }
        }
    </style>
</head>

<body>
    <header>
        <nav class="navbar navbar-expand-lg navbar-dark">
            <div class="container">
                <a class="navbar-brand logo" href="#">red.kamel</a>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav"
                    aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav ml-auto">
                        <li class="nav-item"><a class="nav-link" href="#">Home</a></li>
                        <li class="nav-item"><a class="nav-link" href="#">Contact</a></li>
                        <li class="nav-item"><a class="nav-link buy-tickets"
                                href="https://www.instagram.com/red.kamel">Buy Tickets</a></li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>

    <div class="main-content">
        <section class="hero">
            <div class="overlay"></div>
            <div class="content text-center">
                <h1>Pool partie!!!!</h1>
                <p>08, juin 2024</p>
                <p>PALAIS ATLAS MARRAKECH</p>
            </div>
        </section>
    </div>

    <section class="ticket-info py-5">
        <div class="container py-5">
            <div class="row">
                <div class="col-md-6">
                    <img src="5.jpg" alt="Concert Image" class="concert-image img-fluid mb-4">
                </div>
                <div class="col-md-6">
                    <h2>Tarifs pour l'événement :</h2>
                    <div class="pass">
                        <h2>Normal pass</h2>
                        <p>300DH</p>
                    </div>
                    <div class="pass">
                        <h2>VIP pass pour deux personnes</h2>
                        <p>
                            Lit extérieur près de la piscine<br>
                            Soda illimité<br>
                            Bouteille de whisky ou de vodka
                        </p>
                        <p>600DH + 2 shots de vodka ou 2 sodas</p>
                    </div>
                    <div class="pass">
                        <h2>Pack spécial pour les filles</h2>
                        <p>700DH + 3 boissons gratuites</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div>&copy; 2024 red.kamel. Tous droits réservés.</div>
            <div>
                <a href="https://www.instagram.com/red.kamel" target="_blank">Instagram</a>
            </div>
        </div>
    </footer>

    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    <script>
        window.addEventListener('scroll', function () {
            var header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
    </script>
</body>

</html>
