
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Task Post - توصيل المهمات من الباب للباب</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        /* متغيرات الألوان */
        :root {
            --burgundy: #800020;
            --dark-burgundy: #5c0018;
            --light-burgundy: #a8324d;
            --dark-gray: #2d2d2d;
            --medium-gray: #5a5a5a;
            --light-gray: #f5f5f5;
            --white: #ffffff;
            --shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        /* إعادة تعيين الأنماط الأساسية */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Tajawal', sans-serif;
        }

        body {
            background-color: var(--light-gray);
            color: var(--dark-gray);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* التصميم العام */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        section {
            padding: 80px 0;
        }

        h1, h2, h3, h4 {
            font-weight: 700;
            line-height: 1.3;
            margin-bottom: 20px;
        }

        h1 {
            font-size: 3.5rem;
        }

        h2 {
            font-size: 2.5rem;
            position: relative;
            padding-bottom: 15px;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 100px;
            height: 4px;
            background-color: var(--burgundy);
        }

        p {
            margin-bottom: 15px;
            font-size: 1.1rem;
        }

        .btn {
            display: inline-block;
            padding: 15px 35px;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            text-align: center;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            font-size: 1.1rem;
            box-shadow: var(--shadow);
        }

        .btn-primary {
            background-color: var(--burgundy);
            color: var(--white);
        }

        .btn-primary:hover {
            background-color: var(--dark-burgundy);
            transform: translateY(-3px);
        }

        .btn-secondary {
            background-color: var(--dark-gray);
            color: var(--white);
        }

        .btn-secondary:hover {
            background-color: #1a1a1a;
            transform: translateY(-3px);
        }

        /* الشريط العلوي */
        header {
            background-color: var(--white);
            box-shadow: var(--shadow);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 15px 0;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
        }

        .logo-text {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--burgundy);
            margin-right: 10px;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark-gray);
            font-weight: 600;
            transition: var(--transition);
            position: relative;
            padding: 5px 0;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 0;
            height: 2px;
            background-color: var(--burgundy);
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--burgundy);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--burgundy);
        }

        /* قسم البطل */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), 
                        url('https://images.unsplash.com/photo-1621972750746-2c6f5e5b1c9d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            height: 100vh;
            min-height: 700px;
            display: flex;
            align-items: center;
            color: var(--white);
            text-align: right;
            position: relative;
        }

        .hero-content {
            max-width: 700px;
            animation: fadeInUp 1s ease-out;
        }

        .hero h1 {
            margin-bottom: 20px;
            font-size: 3.5rem;
        }

        .hero h1 span {
            color: var(--burgundy);
            display: block;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 30px;
        }

        .hero-btns {
            display: flex;
            gap: 20px;
            margin-top: 30px;
        }

        .hero-features {
            display: flex;
            gap: 20px;
            margin-top: 40px;
            flex-wrap: wrap;
        }

        .feature-box {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 10px;
            padding: 20px;
            flex: 1;
            min-width: 200px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .feature-box i {
            font-size: 2rem;
            color: var(--burgundy);
            margin-bottom: 15px;
        }

        /* قسم كيفية العمل */
        .how-it-works {
            background-color: var(--white);
            text-align: center;
        }

        .how-it-works h2 {
            text-align: center;
            margin-bottom: 50px;
        }

        .how-it-works h2::after {
            right: 50%;
            transform: translateX(50%);
        }

        .steps-container {
            display: flex;
            justify-content: space-between;
            gap: 30px;
            flex-wrap: wrap;
        }

        .step {
            flex: 1;
            min-width: 250px;
            padding: 40px 20px;
            background: var(--light-gray);
            border-radius: 10px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .step:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow);
        }

        .step::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 5px;
            background-color: var(--burgundy);
            transform: scaleX(0);
            transform-origin: left;
            transition: var(--transition);
            z-index: -1;
        }

        .step:hover::before {
            transform: scaleX(1);
        }

        .step-icon {
            width: 80px;
            height: 80px;
            background-color: rgba(128, 0, 32, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 2rem;
            color: var(--burgundy);
        }

        .step-number {
            position: absolute;
            top: 15px;
            left: 15px;
            font-size: 1.5rem;
            font-weight: 700;
            color: rgba(128, 0, 32, 0.1);
        }

        /* قسم الميزات */
        .features {
            background: linear-gradient(to bottom, var(--light-gray) 50%, var(--white) 50%);
        }

        .features-container {
            display: flex;
            gap: 40px;
            flex-wrap: wrap;
        }

        .features-content {
            flex: 1;
            min-width: 300px;
        }

        .features-grid {
            flex: 1;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
            min-width: 300px;
        }

        .feature-card {
            background-color: var(--white);
            border-radius: 10px;
            padding: 30px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            text-align: center;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
        }

        .feature-card i {
            font-size: 2.5rem;
            color: var(--burgundy);
            margin-bottom: 20px;
        }

        /* قسم آراء العملاء */
        .testimonials {
            background-color: var(--burgundy);
            color: var(--white);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .testimonials h2 {
            color: var(--white);
        }

        .testimonials h2::after {
            background-color: var(--white);
            right: 50%;
            transform: translateX(50%);
        }

        .testimonials-container {
            max-width: 800px;
            margin: 50px auto;
            position: relative;
        }

        .testimonial {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 40px;
            margin: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .testimonial-content {
            font-style: italic;
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .client-info {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
        }

        .client-avatar {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background-color: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            color: var(--burgundy);
        }

        .client-name {
            font-weight: 700;
            font-size: 1.2rem;
        }

        .client-position {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        .rating {
            color: #FFD700;
            margin-top: 10px;
        }

        .testimonial-nav {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
        }

        .testimonial-nav button {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            color: var(--white);
            font-size: 1.2rem;
            cursor: pointer;
            transition: var(--transition);
        }

        .testimonial-nav button:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        /* قسم الاشتراك */
        .cta {
            background: linear-gradient(to right, var(--dark-gray), var(--medium-gray));
            color: var(--white);
            text-align: center;
            padding: 100px 0;
        }

        .cta h2 {
            color: var(--white);
            max-width: 700px;
            margin: 0 auto 30px;
        }

        .cta h2::after {
            display: none;
        }

        .cta-content {
            max-width: 600px;
            margin: 0 auto;
        }

        .cta-btns {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 40px;
            flex-wrap: wrap;
        }

        /* التذييل */
        footer {
            background-color: var(--dark-gray);
            color: var(--white);
            padding: 60px 0 30px;
        }

        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }

        .footer-col h3 {
            color: var(--burgundy);
            margin-bottom: 25px;
            font-size: 1.5rem;
            position: relative;
            padding-bottom: 10px;
        }

        .footer-col h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 50px;
            height: 3px;
            background-color: var(--burgundy);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 12px;
        }

        .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: var(--transition);
            display: block;
        }

        .footer-links a:hover {
            color: var(--white);
            transform: translateX(5px);
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--white);
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--burgundy);
            transform: translateY(-5px);
        }

        .copyright {
            text-align: center;
            padding-top: 40px;
            margin-top: 40px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #aaa;
            font-size: 0.9rem;
        }

        /* تأثيرات الحركة */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* تصميم متجاوب */
        @media (max-width: 992px) {
            h1 {
                font-size: 2.8rem;
            }
            
            h2 {
                font-size: 2rem;
            }
            
            .hero h1 {
                font-size: 3rem;
            }
            
            .feature-box {
                min-width: calc(50% - 10px);
            }
        }

        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }
            
            .nav-links {
                position: fixed;
                top: 80px;
                right: -100%;
                flex-direction: column;
                background-color: var(--white);
                width: 100%;
                height: calc(100vh - 80px);
                padding: 40px 20px;
                transition: var(--transition);
                box-shadow: var(--shadow);
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .nav-links li {
                margin: 15px 0;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .hero-btns {
                flex-direction: column;
            }
            
            .feature-box {
                min-width: 100%;
            }
            
            .steps-container {
                flex-direction: column;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 576px) {
            h1 {
                font-size: 2.2rem;
            }
            
            h2 {
                font-size: 1.8rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .cta-btns {
                flex-direction: column;
                align-items: center;
            }
        }
        
        /* أنماط إضافية لرقم الاتصال */
        .contact-number {
            display: block;
            background-color: var(--burgundy);
            color: white;
            padding: 15px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.3rem;
            margin: 25px auto;
            width: fit-content;
            box-shadow: 0 4px 15px rgba(128, 0, 32, 0.3);
            transition: all 0.3s ease;
            animation: pulse 2s infinite;
        }
        
        .contact-number:hover {
            background-color: var(--dark-burgundy);
            transform: scale(1.05);
        }
        
        .contact-number i {
            margin-left: 10px;
        }
        
        @keyframes pulse {
            0% {
                box-shadow: 0 0 0 0 rgba(128, 0, 32, 0.7);
            }
            70% {
                box-shadow: 0 0 0 15px rgba(128, 0, 32, 0);
            }
            100% {
                box-shadow: 0 0 0 0 rgba(128, 0, 32, 0);
            }
        }
        
        .contact-section {
            background-color: var(--light-gray);
            padding: 60px 0;
            text-align: center;
        }
        
        .contact-section h2 {
            color: var(--burgundy);
            margin-bottom: 30px;
        }
        
        .contact-info {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 30px;
            margin-top: 40px;
        }
        
        .contact-card {
            background-color: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: var(--shadow);
            width: 280px;
            transition: var(--transition);
        }
        
        .contact-card:hover {
            transform: translateY(-10px);
        }
        
        .contact-card i {
            font-size: 2.5rem;
            color: var(--burgundy);
            margin-bottom: 20px;
        }
        
        /* أنماط GitHub */
        .github-section {
            background-color: var(--dark-gray);
            color: white;
            padding: 60px 0;
            text-align: center;
        }
        
        .github-link {
            display: inline-flex;
            align-items: center;
            background-color: #333;
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.2rem;
            margin-top: 30px;
            transition: all 0.3s ease;
        }
        
        .github-link:hover {
            background-color: #444;
            transform: translateY(-3px);
        }
        
        .github-link i {
            margin-left: 10px;
        }
    </style>
</head>
<body>
    <!-- الشريط العلوي -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <div class="logo-text">TaskPost</div>
            </div>
            <ul class="nav-links">
                <li><a href="#home">الرئيسية</a></li>
                <li><a href="#how-it-works">كيف تعمل</a></li>
                <li><a href="#features">الميزات</a></li>
                <li><a href="#testimonials">آراء العملاء</a></li>
                <li><a href="#contact">تواصل معنا</a></li>
                <li><a href="#github">GitHub</a></li>
            </ul>
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- قسم البطل -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>مُهمّاتك تصل إليك<br><span>بسهولة. أينما كنت.</span></h1>
                <p>خدمة توصيل الطرود والمعاملات الجديدة من الباب للباب. ودّع عناء المشاوير!</p>
                
                <!-- زر الاتصال المباشر -->
                <a href="tel:+972504670703" class="contact-number">
                    <i class="fas fa-phone"></i> اتصل بنا الآن: +972 50-467-0703
                </a>
                
                <div class="hero-btns">
                    <!-- التعديل الأول: تغيير نص الزر إلى "بريد صورباهر أقرب وأسرع" -->
                    <a href="#how-it-works" class="btn btn-primary">بريد صورباهر أقرب وأسرع</a>
                    <a href="#features" class="btn btn-secondary">تعرف على الميزات</a>
                </div>
                <div class="hero-features">
                    <div class="feature-box">
                        <i class="fas fa-shipping-fast"></i>
                        <h3>توصيل سريع</h3>
                        <p>وصل مهماتك في وقت قياسي</p>
                    </div>
                    <div class="feature-box">
                        <i class="fas fa-shield-alt"></i>
                        <h3>آمن وموثوق</h3>
                        <p>ضمان وصول شحنتك بأمان</p>
                    </div>
                    <div class="feature-box">
                        <i class="fas fa-map-marker-alt"></i>
                        <h3>تتبع مباشر</h3>
                        <p>تابع بريدك خطوة بخطوة</p>
                    </div>
                    <div class="feature-box">
                        <i class="fas fa-headset"></i>
                        <h3>دعم فني 24/7</h3>
                        <p>فريق دعم جاهز لمساعدتك</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- قسم كيفية العمل -->
    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <h2>خطوات بسيطة... لراحة تامة</h2>
            <div class="steps-container">
                <div class="step">
                    <div class="step-number">1</div>
                    <div class="step-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3>اطلب بضغطة زر</h3>
                    <p>اطلب خدمتك بسهولة من موقعنا أو تطبيق الهاتف في دقائق معدودة</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <div class="step-icon">
                        <i class="fas fa-box-open"></i>
                    </div>
                    <h3>نحن نستلم</h3>
                    <p>سائقونا يصلون إليك لاستلام طردك أو معاملتك من مكانك</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <div class="step-icon">
                        <i class="fas fa-truck"></i>
                    </div>
                    <h3>نحن نُوصل</h3>
                    <p>يتم توصيل مهمتك بأمان وسرعة إلى الوجهة المحددة</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <div class="step-icon">
                        <i class="fas fa-check-circle"></i>
                    </div>
                    <h3>تأكيد الاستلام</h3>
                    <p>تتبع بريدك لحظة حتى تأكيد الاستلام</p>
                </div>
            </div>
        </div>
    </section>

    <!-- قسم الميزات -->
    <section class="features" id="features">
        <div class="container">
            <h2>اختر Task Post... اختر الراحة والموثوقية</h2>
            <div class="features-container">
                <div class="features-content">
                    <h3>لماذا نحن الخيار الأمثل لتوصيل مهماتك؟</h3>
                    <p>في Task Post، نقدم حلاً شاملاً لتوصيل المهمات اليومية بكل سهولة وأمان. نحن ندرك أهمية وقتك وثقتك، لذا نضمن لك تجربة توصيل سلسة ومضمونة.</p>
                    <p>من خلال شبكتنا الواسعة من السائقين المحترفين والتقنيات المتقدمة، نضمن وصول مهماتك في الوقت المحدد وبأعلى معايير الجودة والأمان.</p>
                    <div class="hero-btns" style="margin-top: 30px;">
                        <!-- التعديل الثالث: تصحيح الزر هنا -->
                        <a href="#" class="btn btn-primary">بريد صورباهر صار أسرع وأقرب</a>
                    </div>
                </div>
                <div class="features-grid">
                    <div class="feature-card">
                        <i class="fas fa-bolt"></i>
                        <h3>السرعة</h3>
                        <p>توصيل سريع وفعّال لضمان وصول مهماتك في أقصر وقت</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-lock"></i>
                        <h3>الأمان</h3>
                        <p>نضمن أمان وسلامة شحناتك من الاستلام حتى التسليم</p>
                    </div>
                    <div class="feature-card">
                        <i class="fas fa-couch"></i>
                        <h3>الراحة</h3>
                        <p>لا داعي لمغادرة منزلك أو مكتبك، نحن نأتيك!</p>
                    </div>
                    <!-- التعديل الثالث: حذف بطاقة التتبع المباشر -->
                    <!-- تم حذف بطاقة التتبع المباشر كما طلبت -->
                </div>
            </div>
        </div>
    </section>

    <!-- قسم آراء العملاء -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <h2>ماذا يقول عملاؤنا عن Task Post؟</h2>
            <div class="testimonials-container">
                <div class="testimonial">
                    <div class="testimonial-content">
                        "لقد غيرت Task Post طريقة إنجازي للمهام اليومية. الآن لا داعي للقلق بشأن الوقت الضائع في المشاوير. الخدمة سريعة وموثوقة!"
                    </div>
                    <div class="client-info">
                        <div class="client-avatar">
                            <i class="fas fa-user"></i>
                        </div>
                        <div>
                            <div class="client-name">سارة محمد</div>
                            <div class="client-position">مديرة تسويق</div>
                        </div>
                    </div>
                    <div class="rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                </div>
            </div>
            <div class="testimonial-nav">
                <button><i class="fas fa-chevron-right"></i></button>
                <button><i class="fas fa-chevron-left"></i></button>
            </div>
        </div>
    </section>

    <!-- قسم الاتصال -->
    <section class="contact-section" id="contact">
        <div class="container">
            <h2>تواصل معنا بكل سهولة</h2>
            <p>فريق دعمنا جاهز للإجابة على استفساراتك وتلبية احتياجاتك في أي وقت</p>
            
            <a href="tel:+972504670703" class="contact-number">
                <i class="fas fa-phone"></i> اتصل بنا الآن: +972 50-467-0703
            </a>
            
            <div class="contact-info">
                <div class="contact-card">
                    <i class="fas fa-headset"></i>
                    <h3>الدعم الفني</h3>
                    <p>متاح 24/7 للإجابة على استفساراتك وحل مشاكلك</p>
                </div>
                
                <div class="contact-card">
                    <i class="fas fa-envelope"></i>
                    <h3>البريد الإلكتروني</h3>
                    <p>info@taskpost.com</p>
                </div>
                
                <div class="contact-card">
                    <i class="fab fa-whatsapp"></i>
                    <h3>واتساب</h3>
                    <p>+972 50-467-0703</p>
                </div>
            </div>
        </div>
    </section>

    <!-- قسم GitHub -->
    <section class="github-section" id="github">
        <div class="container">
            <h2>مشروعنا على GitHub</h2>
            <p>يمكنك الاطلاع على الكود المصدري للمشروع وتطويراته المستقبلية</p>
            <a href="#" class="github-link">
                <i class="fab fa-github"></i> تصفح المشروع على GitHub
            </a>
        </div>
    </section>

    <!-- قسم الاشتراك -->
    <section class="cta">
        <div class="container">
            <div class="cta-content">
                <h2>مهماتك اليومية... أصبحت أسهل</h2>
                <p>جرب Task Post اليوم واكتشف الراحة التي تستحقها. سجل الآن واحصل على خصم 20% على أول طلب لك!</p>
                <div class="cta-btns">
                    <a href="#" class="btn btn-primary">ابدأ الآن</a>
                    <a href="tel:+972504670703" class="btn btn-secondary">اتصل بنا</a>
                </div>
            </div>
        </div>
    </section>

    <!-- التذييل -->
    <footer>
        <div class="container">
            <div class="footer-container">
                <div class="footer-col">
                    <h3>عن Task Post</h3>
                    <p>نحن نسعى لجعل حياتك أسهل من خلال خدمة توصيل المهمات اليومية من الباب للباب بأعلى معايير الجودة والأمان.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                <div class="footer-col">
                    <h3>روابط سريعة</h3>
                    <ul class="footer-links">
                        <li><a href="#home">الرئيسية</a></li>
                        <li><a href="#how-it-works">كيف نعمل</a></li>
                        <li><a href="#features">الميزات</a></li>
                        <li><a href="#testimonials">آراء العملاء</a></li>
                        <li><a href="#contact">تواصل معنا</a></li>
                        <li><a href="#github">GitHub</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>خدماتنا</h3>
                    <ul class="footer-links">
                        <li><a href="#">توصيل الطرود</a></li>
                        <li><a href="#">توصيل المعاملات</a></li>
                        <li><a href="#">توصيل المستندات</a></li>
                        <li><a href="#">خدمات الشركات</a></li>
                        <li><a href="#">خدمات التوصيل الفوري</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h3>اتصل بنا</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> القدس  صورباهر </li>
                        <li><i class="fas fa-phone"></i> +972 50-467-0703</li>
                        <li><i class="fas fa-envelope"></i> info@taskpost.com</li>
                        <li><i class="fas fa-clock"></i> الأحد - الخميس: 8 صباحاً - 10 مساءً</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 Task Post. جميع الحقوق محفوظة.</p>
            </div>
        </div>
    </footer>

    <script>
        // تنشيط القائمة المتنقلة
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const navLinks = document.querySelector('.nav-links');
        
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            
            // تغيير الأيقونة
            const icon = mobileMenuBtn.querySelector('i');
            if (icon.classList.contains('fa-bars')) {
                icon.classList.remove('fa-bars');
                icon.classList.add('fa-times');
            } else {
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            }
        });
        
        // إغلاق القائمة عند النقر على رابط
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                mobileMenuBtn.querySelector('i').classList.remove('fa-times');
                mobileMenuBtn.querySelector('i').classList.add('fa-bars');
            });
        });
        
        // التنقل السلس
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                window.scrollTo({
                    top: targetElement.offsetTop - 80,
                    behavior: 'smooth'
                });
            });
        });
        
        // تغيير لون الشريط العلوي عند التمرير
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.backgroundColor = 'var(--white)';
                header.style.boxShadow = '0 4px 20px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.backgroundColor = 'var(--white)';
                header.style.boxShadow = 'none';
            }
        });
        
        // تأثير تمرير شهادات العملاء
        const testimonials = document.querySelectorAll('.testimonial');
        const prevBtn = document.querySelector('.testimonial-nav button:first-child');
        const nextBtn = document.querySelector('.testimonial-nav button:last-child');
        let currentTestimonial = 0;
        
        function showTestimonial(index) {
            testimonials.forEach(testimonial => {
                testimonial.style.display = 'none';
            });
            testimonials[index].style.display = 'block';
        }
        
        prevBtn.addEventListener('click', () => {
            currentTestimonial = (currentTestimonial - 1 + testimonials.length) % testimonials.length;
            showTestimonial(currentTestimonial);
        });
        
        nextBtn.addEventListener('click', () => {
            currentTestimonial = (currentTestimonial + 1) % testimonials.length;
            showTestimonial(currentTestimonial);
        });
        
        // إظهار أول شهادة عند التحميل
        showTestimonial(currentTestimonial);
    </script>
</body>
</html>
```
ج


