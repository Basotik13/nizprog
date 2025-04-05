<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Прогулки по Нижегородской области</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" rel="stylesheet">
    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #f4f4f4, #e0e0e0);
            color: #333;
            padding-bottom: 60px;
        }
        header {
            background: linear-gradient(135deg, #6a11cb, #2575fc);
            color: white;
            padding: 40px 20px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }
        header h1 {
            font-size: 2.5rem;
            margin: 0;
            animation: fadeInDown 1s ease;
        }
        nav {
            display: flex;
            justify-content: center;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        nav a {
            margin: 10px;
            padding: 12px 24px;
            color: white;
            text-decoration: none;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 30px;
            transition: background 0.3s ease, transform 0.3s ease;
            font-weight: 500;
        }
        nav a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }
        section {
            padding: 30px;
            margin: 20px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            display: none;
            animation: fadeIn 0.5s ease;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        h2 {
            color: #6a11cb;
            margin-bottom: 20px;
            font-size: 2rem;
        }
        footer {
            text-align: center;
            padding: 20px;
            background: linear-gradient(135deg, #6a11cb, #2575fc);
            color: white;
            position: fixed;
            bottom: 0;
            width: 100%;
            box-shadow: 0 -4px 15px rgba(0, 0, 0, 0.2);
            z-index: 1000;
        }
        .tabs {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }
        .tab {
            margin: 10px;
            padding: 12px 24px;
            background: rgba(106, 17, 203, 0.1);
            border-radius: 30px;
            cursor: pointer;
            transition: background 0.3s ease, transform 0.3s ease;
            font-weight: 500;
        }
        .tab:hover {
            background: rgba(106, 17, 203, 0.2);
            transform: translateY(-3px);
        }
        .tab.active {
            background: #6a11cb;
            color: white;
        }
        .tab-content {
            padding: 30px;
            background: #f9f9f9;
            border-radius: 15px;
            margin-top: 20px;
            animation: fadeIn 0.5s ease;
        }
        .tab-content h3 {
            color: #6a11cb;
            margin-bottom: 20px;
            font-size: 1.8rem;
        }
        .tab-content p {
            line-height: 1.8;
            margin-bottom: 20px;
            color: #555;
        }
        .tab-content h4 {
            color: #333;
            margin-bottom: 15px;
            font-size: 1.4rem;
        }
        .tab-content a {
            color: #6a11cb;
            text-decoration: none;
            font-weight: 600;
        }
        .tab-content a:hover {
            text-decoration: underline;
        }
        .icon {
            margin-right: 10px;
        }
        #map-container {
            width: 100%;
            height: 400px;
            border-radius: 10px;
            margin-top: 15px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        @media (max-width: 768px) {
            nav a, .tab {
                width: 100%;
                text-align: center;
            }
            #map-container {
                height: 300px;
            }
        }
    </style>
</head>
<body>

<header>
    <h1>Прогулки по Нижегородской области</h1>
    <nav>
        <a href="#home" onclick="showSection('home')"><i class="fas fa-home icon"></i>Главная</a>
        <a href="#routes" onclick="showSection('routes')"><i class="fas fa-route icon"></i>Маршруты</a>
    </nav>
</header>

<section id="home">
    <h2>Добро пожаловать!</h2>
    <p>На нашем сайте вы найдете лучшие маршруты для прогулок по Нижегородской области. Мы предлагаем вам уникальные идеи для путешествий, включая интересные места, кафе и гостиницы.</p>
    <p>Исследуйте природу, культуру и искусство этого прекрасного региона. Начните свое путешествие прямо сейчас!</p>
</section>

<section id="routes">
    <h2>Маршруты</h2>
    <div class="tabs">
        <div class="tab active" onclick="showTab('overview')"><i class="fas fa-map-marked-alt icon"></i>Обзор</div>
        <div class="tab" onclick="showTab('homes')"><i class="fas fa-hotel icon"></i>Гостиницы</div>
        <div class="tab" onclick="showTab('day1')"><i class="fas fa-calendar-day icon"></i>День 1</div>
        <div class="tab" onclick="showTab('day2')"><i class="fas fa-calendar-day icon"></i>День 2</div>
        <div class="tab" onclick="showTab('day3')"><i class="fas fa-calendar-day icon"></i>День 3</div>
        <div class="tab" onclick="showTab('day4')"><i class="fas fa-calendar-day icon"></i>День 4</div>
        <div class="tab" onclick="showTab('expenses')"><i class="fas fa-coins icon"></i>Расходы</div>
        <div class="tab" onclick="showTab('map')"><i class="fas fa-map icon"></i>Карта</div>
    </div>

    <section id="overview" class="tab-content">
        <h3>Маршрут «На берегу Волги»</h3>
        <p>Этот маршрут предлагает вам насладиться живописными видами реки Волги, посещая различные интересные места вдоль берега.</p>
        <p>Включает посещение парков, кафе, исторических мест и многое другое.</p>
    </section>

    <section id="homes" class="tab-content" style="display:none;">
        <h3>Гостиницы</h3>
        <h4>Гостиница "Московская"</h4>
        <p><strong>Описание:</strong> Современные номера, ресторан, конференц-залы, бесплатный Wi-Fi и парковка.</p>
        <p><strong>Цены:</strong> От 3000 руб./ночь.</p>
        <p><strong>Адрес:</strong> ул. Чаадаева, 3Б.</p>
        <p><strong>Сайт:</strong> <a href="https://moscowhotel-nnov.ru" target="_blank">https://moscowhotel-nnov.ru</a></p>

        <h4>Гостиница «ЗОРИ»</h4>
        <p><strong>Описание:</strong> Бесплатный Wi-Fi, парковка, услуги по организации мероприятий.</p>
        <p><strong>Цены:</strong> От 2500 руб./ночь.</p>
        <p><strong>Адрес:</strong> улица Красных Зорь 24/5.</p>
        <p><strong>Сайт:</strong> <a href="https://www.zorinn.ru" target="_blank">https://www.zorinn.ru</a></p>
    </section>

    <section id="day1" class="tab-content" style="display:none;">
        <h3>День 1: Природа и история</h3>
        <h4>Утро: Сормовский парк</h4>
        <p><strong>09:00 - 10:30:</strong> Завтрак в кофейне «Coffee like»</p>
        <p><strong>Меню:</strong> Отличный кофе, как раз для начала прекрасного утра и можно подкрепиться</p>
        <p><strong>Адрес:</strong> Юбилейный бул., 34</p>
	<p><strong>Сайт:</strong> <a href="https://coffee-like.com/?ysclid=m94ohv4th9511241889" target="_blank">https://coffee-like.com</a></p>

        <h4>Полдень: Набережная реки Волги</h4>
        <p><strong>12:00 - 13:30:</strong> Обед в ресторане «Red Wall»</p>
        <p><strong>Меню:</strong> Уха — 350 руб., Пироги с мясом — 250 руб., Салат «Цезарь» — 400 руб. (600 руб.)</p>
        <p><strong>Адрес:</strong> Кожевенная ул., 2</p>
	<p><strong>Сайт:</strong> <a href="https://redwallrestaurant.ru" target="_blank">https://redwallrestaurant.ru</a></p>	

        <h4>Вечер: Парк Победы</h4>
        <p><strong>15:00 - 17:00:</strong> Посещение Парка Победы.</p>
        <p><strong>17:00 - 18:30:</strong> Ужин в ресторане <a href="https://vk.com/gustoloftnn" target="_blank">Gustu Loft</a></p>
        <p><strong>Меню:</strong> Стейк из говядины — 800 руб., Запеченные овощи — 300 руб., Десерт — 250 руб. (1350 руб.)</p>
        <p><strong>Адрес:</strong> Большая Печёрская ул., 65</p>
    </section>

    <section id="day2" class="tab-content" style="display:none;">
        <h3>День 2: Культура и искусство</h3>
        <h4>Утро: Нижегородский кремль</h4>
        <p><strong>09:00 - 10:00:</strong> Завтрак в кафе «Кремлевское»</p>
        <p><strong>Меню:</strong> Пирожки с начинкой — 150 руб., Каша — 200 руб., Чай — 100 руб. (450 руб.)</p>
        <p><strong>Адрес:</strong> Кремль, 1</p>

        <h4>Полдень: Чкаловская лестница</h4>
        <p><strong>12:00 - 12:30:</strong> Прогулка к Чкаловской лестнице.</p>

        <h4>Вечер: Площадь Минина и Пожарского</h4>
        <p><strong>13:30 - 14:00:</strong> Обед в ресторане <a href="https://steakhouse-nn.ru" target="_blank">Steak house</a></p>
        <p><strong>Меню:</strong> Стейк — 900 руб., Картофель фри — 200 руб., Салат — 300 руб. (1400 руб.)</p>
    </section>

    <section id="day3" class="tab-content" style="display:none;">
        <h3>День 3: Отдых и развлечения</h3>
        <h4>Утро: Канатная дорога на Гребном канале</h4>
        <p><strong>09:00 - 10:00:</strong> Завтрак в кафе «На высоте»</p>
        <p><strong>Меню:</strong> Сэндвичи — 250 руб., Кофе — 150 руб. (400 руб.)</p>

        <h4>Полдень: Гребной канал</h4>
        <p><strong>11:00 - 13:00:</strong> Прогулка вдоль Гребного канала.</p>

        <h4>Вечер: Парк «Швейцария»</h4>
        <p><strong>16:30 - 18:00:</strong> Ужин в кафе <a href="https://italiancann.ru" target="_blank">"Итальянка"</a></p>
        <p><strong>Средний чек:</strong> 1200 </p>
    </section>

    <section id="day4" class="tab-content" style="display:none;">
        <h3>День 4: Уникальные места и местные традиции</h3>
        <h4>Утро: Музей народного искусства</h4>
        <p><strong>09:00 - 10:00:</strong> Завтрак в кафе «Старый Нижний»</p>
        <p><strong>Меню:</strong> Блины — 150 руб., Чай — 100 руб. (250 руб.)</p>

        <h4>Полдень: Улица Рождественская</h4>
        <p><strong>13:30 - 15:00:</strong> Обед в ресторане «Гастроном»</p>
        <p><strong>Меню:</strong> Суп — 250 руб., Салат — 300 руб., Горячее — 500 руб. (1050 руб.)</p>
    </section>

    <section id="expenses" class="tab-content" style="display:none;">
        <h3>Примерные общие расходы</h3>
        <p><strong>День 1:</strong> 2550 руб.</p>
        <p><strong>День 2:</strong> 2850 руб.</p>
        <p><strong>День 3:</strong> 2550 руб.</p>
        <p><strong>День 4:</strong> 2200 руб.</p>
        <p><strong>Итого:</strong> 10150 руб. (без учета проживания)</p>
    </section>

    <section id="map" class="tab-content" style="display:none;">
        <h3>Интерактивная карта</h3>
        <p>Исследуйте точки маршрута на карте ниже:</p>
        <div id="map-container"></div>
    </section>
</section>

<footer>
    <p>© 2024-2025 Прогулки по Нижегородской области. Все права защищены.</p>
</footer>

<script>
    let map;
    let mapInitialized = false;

    function showSection(sectionId) {
        // Убираем # из ID если он есть
        const cleanId = sectionId.replace('#', '');
        
        document.querySelectorAll('section[id="home"], section[id="routes"]').forEach(section => {
            section.style.display = 'none';
        });
        
        const section = document.getElementById(cleanId);
        if (section) {
            section.style.display = 'block';
        }
    }

    function showTab(tabId) {
        // Убираем # из ID если он есть
        const cleanId = tabId.replace('#', '');
        
        document.querySelectorAll('.tab-content').forEach(tab => {
            tab.style.display = 'none';
        });
        
        const tab = document.getElementById(cleanId);
        if (tab) {
            tab.style.display = 'block';
        }

        document.querySelectorAll('.tab').forEach(tab => {
            tab.classList.remove('active');
        });
        
        const activeTab = document.querySelector(`.tab[onclick*="${tabId}"]`);
        if (activeTab) {
            activeTab.classList.add('active');
        }

        if (cleanId === 'map' && !mapInitialized) {
            initMap();
            mapInitialized = true;
        }
    }

    function initMap() {
        ymaps.ready(function() {
            map = new ymaps.Map('map-container', {
                center: [56.326887, 44.005986],
                zoom: 12
            });

            const places = [
                { coords: [56.326887, 44.005986], title: 'Нижний Новгород' },
                { coords: [56.3333, 43.8667], title: 'Сормовский парк' },
                { coords: [56.3287, 44.002], title: 'Чкаловская лестница' },
                { coords: [56.3206, 44.018], title: 'Парк Победы' }
            ];

            places.forEach(place => {
                const marker = new ymaps.Placemark(place.coords, {
                    hintContent: place.title
                });
                map.geoObjects.add(marker);
            });
        });
    }

    // Инициализация при загрузке
    document.addEventListener('DOMContentLoaded', function() {
        showSection('home');
        showTab('overview');
        
        // Обработка якорей в URL
        if (window.location.hash) {
            const hash = window.location.hash;
            if (hash === '#home' || hash === '#routes') {
                showSection(hash);
            } else {
                showSection('routes');
                setTimeout(() => showTab(hash), 100);
            }
        }
    });
</script>

<script src="https://api-maps.yandex.ru/2.1/?apikey=ваш_api_ключ&lang=ru_RU" type="text/javascript"></script>

</body>
</html>
