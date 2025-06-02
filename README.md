# Royal-
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Royal Canin - Породні корми</title>
    <meta name="description" content="Породні корми Royal Canin для собак - спеціально розроблені раціони">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ffffff 0%, #f8f8f8 100%);
            overflow: hidden;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        .presentation-container {
            width: 100vw;
            height: 100vh;
            position: relative;
        }

        .slide {
            width: 100%;
            height: 100%;
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            padding: 20px;
            background: linear-gradient(135deg, #ffffff 0%, #f8f8f8 100%);
            border-left: 8px solid #e31e24;
            will-change: transform, opacity;
        }

        .slide.active {
            display: flex;
            flex-direction: column;
            animation: slideIn 0.5s ease-out;
        }

        @keyframes slideIn {
            from { 
                opacity: 0; 
                transform: translateX(30px);
            }
            to { 
                opacity: 1; 
                transform: translateX(0);
            }
        }

        .slide-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 2px solid #e31e24;
            flex-shrink: 0;
        }

        .logo {
            font-size: clamp(1.5rem, 4vw, 2.5rem);
            font-weight: bold;
            color: #e31e24;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .slide-number {
            background: #e31e24;
            color: white;
            padding: 8px 16px;
            border-radius: 20px;
            font-weight: bold;
            font-size: clamp(0.8rem, 2vw, 1rem);
        }

        .slide-content {
            flex: 1;
            display: flex;
            align-items: center;
            gap: 30px;
            min-height: 0;
        }

        .breed-info {
            flex: 1;
            max-width: 50%;
            min-width: 0;
        }

        .breed-name {
            font-size: clamp(1.8rem, 4vw, 3rem);
            background: linear-gradient(135deg, #2c2c2c, #4a4a4a);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
            line-height: 1.2;
        }

        .breed-name::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 50px;
            height: 3px;
            background: linear-gradient(135deg, #e31e24, #ff4444);
            border-radius: 2px;
        }

        .product-info {
            background: linear-gradient(135deg, #ffffff 0%, #f8f8f8 100%);
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(227, 30, 36, 0.12);
            border: 2px solid #e31e24;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
        }

        .product-info::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #e31e24, #ff4444, #e31e24);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .product-name {
            font-size: clamp(1.1rem, 2.5vw, 1.8rem);
            background: linear-gradient(135deg, #e31e24, #c41e24);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 15px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
            line-height: 1.2;
        }

        .product-weight {
            font-size: clamp(0.9rem, 2vw, 1.3rem);
            color: #fff;
            background: linear-gradient(135deg, #e31e24, #c41e24);
            padding: 8px 16px;
            border-radius: 20px;
            display: inline-block;
            margin-bottom: 20px;
            font-weight: bold;
            box-shadow: 0 6px 15px rgba(227, 30, 36, 0.3);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .breed-features {
            list-style: none;
            display: grid;
            gap: 8px;
        }

        .breed-features li {
            background: linear-gradient(135deg, #fff 0%, #f9f9f9 100%);
            padding: 10px 12px;
            border-radius: 8px;
            font-size: clamp(0.8rem, 1.8vw, 1rem);
            color: #444;
            position: relative;
            padding-left: 35px;
            border-left: 3px solid #e31e24;
            box-shadow: 0 3px 10px rgba(227, 30, 36, 0.08);
            transition: all 0.3s ease;
            font-weight: 500;
            line-height: 1.3;
        }

        .breed-features li:hover {
            transform: translateY(-1px);
            box-shadow: 0 6px 20px rgba(227, 30, 36, 0.15);
        }

        .breed-features li:before {
            content: "✨";
            position: absolute;
            left: 12px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1rem;
        }

        .breed-image {
            flex: 1;
            max-width: 45%;
            text-align: center;
            min-width: 0;
        }

        .breed-photo {
            width: 100%;
            height: clamp(200px, 35vh, 400px);
            background: linear-gradient(135deg, #f8f8f8 0%, #ffffff 100%);
            border-radius: 15px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-size: clamp(1.5rem, 4vw, 3rem);
            border: 3px solid #e31e24;
            box-shadow: 0 15px 40px rgba(227, 30, 36, 0.25);
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .breed-photo:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 50px rgba(227, 30, 36, 0.35);
        }

        .breed-photo::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            right: -50%;
            bottom: -50%;
            background: conic-gradient(from 0deg, transparent, rgba(227, 30, 36, 0.1), transparent);
            animation: rotate 4s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .breed-photo small {
            font-size: clamp(0.7rem, 1.5vw, 1rem) !important;
            color: #e31e24;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 8px;
            background: rgba(255, 255, 255, 0.9);
            padding: 4px 8px;
            border-radius: 10px;
            position: relative;
            z-index: 2;
        }

        .navigation {
            position: fixed;
            bottom: 20px;
            right: 20px;
            display: flex;
            gap: 10px;
            z-index: 1000;
        }

        .nav-btn {
            background: #e31e24;
            color: white;
            border: none;
            padding: 10px 16px;
            border-radius: 25px;
            cursor: pointer;
            font-size: clamp(0.7rem, 1.5vw, 0.9rem);
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(227, 30, 36, 0.3);
            touch-action: manipulation;
        }

        .nav-btn:hover:not(:disabled) {
            background: #c41e24;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(227, 30, 36, 0.4);
        }

        .nav-btn:active {
            transform: translateY(0);
        }

        .nav-btn:disabled {
            background: #ccc;
            cursor: not-allowed;
            transform: none;
            box-shadow: 0 2px 6px rgba(0,0,0,0.1);
        }

        .title-slide {
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(135deg, #e31e24 0%, #c41e24 100%);
            color: white;
            border: none;
            padding: 40px;
        }

        .title-slide .main-title {
            font-size: clamp(2rem, 6vw, 3.5rem);
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            line-height: 1.2;
        }

        .title-slide .subtitle {
            font-size: clamp(1rem, 3vw, 1.5rem);
            margin-bottom: 25px;
            opacity: 0.9;
            line-height: 1.3;
        }

        .title-slide .description {
            font-size: clamp(0.8rem, 2.5vw, 1.1rem);
            max-width: 90%;
            line-height: 1.5;
            opacity: 0.8;
        }

        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            height: 4px;
            background: #e31e24;
            transition: width 0.3s ease;
            z-index: 1001;
        }

        .slide-indicator {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 6px;
            z-index: 1000;
        }

        .dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(227, 30, 36, 0.3);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .dot.active {
            background: #e31e24;
            transform: scale(1.2);
        }

        /* Mobile styles */
        @media (max-width: 768px) {
            .slide {
                padding: 15px;
                border-left: 4px solid #e31e24;
            }
            
            .slide-content {
                flex-direction: column;
                gap: 15px;
                text-align: center;
            }
            
            .breed-info, .breed-image {
                max-width: 100%;
                width: 100%;
            }
            
            .breed-photo {
                height: clamp(180px, 25vh, 300px);
            }
            
            .navigation {
                bottom: 15px;
                right: 15px;
                gap: 8px;
            }
            
            .nav-btn {
                padding: 8px 12px;
                font-size: 0.8rem;
            }
            
            .slide-indicator {
                bottom: 70px;
                gap: 4px;
            }
            
            .dot {
                width: 8px;
                height: 8px;
            }
            
            .breed-features {
                gap: 6px;
            }
            
            .breed-features li {
                padding: 8px 10px;
                padding-left: 30px;
            }
            
            .product-info {
                padding: 20px;
            }
        }

        @media (max-width: 480px) {
            .slide {
                padding: 10px;
            }
            
            .slide-header {
                margin-bottom: 15px;
                padding-bottom: 10px;
            }
            
            .breed-photo {
                height: clamp(150px, 20vh, 250px);
                font-size: 2rem;
            }
            
            .breed-photo small {
                font-size: 0.6rem !important;
                padding: 3px 6px;
            }
            
            .product-info {
                padding: 15px;
            }
            
            .breed-features li {
                font-size: 0.75rem;
                padding: 6px 8px;
                padding-left: 25px;
            }
            
            .breed-features li:before {
                left: 8px;
                font-size: 0.9rem;
            }
        }

        /* Large screens optimization */
        @media (min-width: 1200px) {
            .slide {
                padding: 40px;
            }
            
            .slide-content {
                gap: 40px;
            }
            
            .breed-photo {
                height: clamp(300px, 45vh, 500px);
            }
            
            .product-info {
                padding: 30px;
            }
        }

        @media (prefers-reduced-motion: reduce) {
            .slide.active {
                animation: none;
            }
            
            .breed-photo::before {
                animation: none;
            }
            
            .product-info::before {
                animation: none;
            }
        }
    </style>
</head>
<body>
    <div class="progress-bar" id="progressBar"></div>
    
    <div class="presentation-container">
        <!-- Титульний слайд -->
        <div class="slide active title-slide">
            <h1 class="main-title">Royal Canin</h1>
            <h2 class="subtitle">Породні корми для собак</h2>
            <p class="description">Спеціально розроблені раціони для конкретних порід, що враховують їх унікальні потреби в харчуванні</p>
        </div>

        <!-- Yorkshire Terrier Adult -->
        <div class="slide">
            <div class="slide-header">
                <div class="logo">Royal Canin</div>
                <div class="slide-number">1/6</div>
            </div>
            <div class="slide-content">
                <div class="breed-info">
                    <h2 class="breed-name">Yorkshire Terrier</h2>
                    <div class="product-info">
                        <div class="product-name">Yorkshire Terrier Adult</div>
                        <div class="product-weight">1.5 кг</div>
                        <ul class="breed-features">
                            <li>Підтримка здоров'я шкіри та блиску шерсті</li>
                            <li>Адаптований розмір гранул для маленької щелепи</li>
                            <li>Підтримка здоров'я зубів</li>
                            <li>Високоякісні білки для м'язової маси</li>
                        </ul>
                    </div>
                </div>
                <div class="breed-image">
                    <div class="breed-photo">🐕‍🦺<br><small>Yorkshire Terrier</small></div>
                </div>
            </div>
        </div>

        <!-- French Bulldog Adult -->
        <div class="slide">
            <div class="slide-header">
                <div class="logo">Royal Canin</div>
                <div class="slide-number">2/6</div>
            </div>
            <div class="slide-content">
                <div class="breed-info">
                    <h2 class="breed-name">French Bulldog</h2>
                    <div class="product-info">
                        <div class="product-name">French Bulldog Adult</div>
                        <div class="product-weight">3 кг</div>
                        <ul class="breed-features">
                            <li>Спеціальна форма гранул для брахіцефалів</li>
                            <li>Підтримка здоров'я травлення</li>
                            <li>Контроль ваги та м'язової маси</li>
                            <li>Підтримка здоров'я шкіри</li>
                        </ul>
                    </div>
                </div>
                <div class="breed-image">
                    <div class="breed-photo">🐕<br><small>French Bulldog</small></div>
                </div>
            </div>
        </div>

        <!-- Labrador Puppy -->
        <div class="slide">
            <div class="slide-header">
                <div class="logo">Royal Canin</div>
                <div class="slide-number">3/6</div>
            </div>
            <div class="slide-content">
                <div class="breed-info">
                    <h2 class="breed-name">Labrador Puppy</h2>
                    <div class="product-info">
                        <div class="product-name">Labrador Puppy</div>
                        <div class="product-weight">12 кг</div>
                        <ul class="breed-features">
                            <li>Підтримка здорового росту цуценят</li>
                            <li>Захист природного імунітету</li>
                            <li>Легкоперетравлювані білки</li>
                            <li>Збалансований вміст кальцію та фосфору</li>
                        </ul>
                    </div>
                </div>
                <div class="breed-image">
                    <div class="breed-photo">🐶<br><small>Labrador Puppy</small></div>
                </div>
            </div>
        </div>

        <!-- Labrador Adult -->
        <div class="slide">
            <div class="slide-header">
                <div class="logo">Royal Canin</div>
                <div class="slide-number">4/6</div>
            </div>
            <div class="slide-content">
                <div class="breed-info">
                    <h2 class="breed-name">Labrador Adult</h2>
                    <div class="product-info">
                        <div class="product-name">Labrador Adult</div>
                        <div class="product-weight">12 кг</div>
                        <ul class="breed-features">
                            <li>Контроль ваги та підтримка ідеальної форми</li>
                            <li>Підтримка здоров'я суглобів</li>
                            <li>Захист серцево-судинної системи</li>
                            <li>Підтримка здоров'я шкіри та шерсті</li>
                        </ul>
                    </div>
                </div>
                <div class="breed-image">
                    <div class="breed-photo">🦮<br><small>Labrador Adult</small></div>
                </div>
            </div>
        </div>

        <!-- German Shepherd Puppy -->
        <div class="slide">
            <div class="slide-header">
                <div class="logo">Royal Canin</div>
                <div class="slide-number">5/6</div>
            </div>
            <div class="slide-content">
                <div class="breed-info">
                    <h2 class="breed-name">German Shepherd Puppy</h2>
                    <div class="product-info">
                        <div class="product-name">German Shepherd Puppy</div>
                        <div class="product-weight">12 кг</div>
                        <ul class="breed-features">
                            <li>Підтримка здорового розвитку скелета</li>
                            <li>Зміцнення природного імунітету</li>
                            <li>Підтримка здоров'я травлення</li>
                            <li>Адаптований вміст енергії для росту</li>
                        </ul>
                    </div>
                </div>
                <div class="breed-image">
                    <div class="breed-photo">🐕‍🦺<br><small>German Shepherd Puppy</small></div>
                </div>
            </div>
        </div>

        <!-- Ger