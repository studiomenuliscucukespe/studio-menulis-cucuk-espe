# studio-menulis-cucuk-espe
Web resmi Studio Menulis Cucuk Espe

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Studio Menulis Cucuk Espe - Menemukan Suara, Menulis dengan Nyawa. Kelas menulis premium eksklusif via Zoom.">
    <meta name="author" content="Cucuk Espe">
    <title>Studio Menulis Cucuk Espe | Menemukan Suara, Menulis dengan Nyawa</title>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,500;0,700;1,400&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* ==========================================================================
           1. CORE STYLES & CSS VARIABLES
           ========================================================================== */
        :root {
            --bg-main: #0f0f0f;
            --bg-card: #181818;
            --gold: #c8a24d;
            --gold-hover: #e5be65;
            --white: #ffffff;
            --gray-light: #eaeaea;
            --gray-muted: #a0a0a0;
            --font-heading: 'Playfair Display', serif;
            --font-body: 'Poppins', sans-serif;
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            --glass-bg: rgba(24, 24, 24, 0.7);
            --glass-border: rgba(200, 162, 77, 0.15);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-main);
            color: var(--gray-light);
            font-family: var(--font-body);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: var(--font-heading);
            color: var(--white);
            font-weight: 700;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: var(--transition);
        }

        ul {
            list-style: none;
        }

        img {
            max-width: 100%;
            height: auto;
            display: block;
        }

        /* Utility Classes */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        .section-padding {
            padding: 100px 0;
        }

        .text-gold {
            color: var(--gold);
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }

        .section-header h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 2px;
            background-color: var(--gold);
        }

        .section-header p {
            color: var(--gray-muted);
            font-size: 1rem;
        }

        /* Buttons */
        .btn {
            display: inline-block;
            padding: 14px 32px;
            border-radius: 4px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9rem;
            cursor: pointer;
            border: 2px solid transparent;
            transition: var(--transition);
        }

        .btn-gold {
            background-color: var(--gold);
            color: var(--bg-main);
        }

        .btn-gold:hover {
            background-color: var(--gold-hover);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(200, 162, 77, 0.2);
        }

        .btn-outline {
            border-color: var(--gold);
            color: var(--gold);
            background: transparent;
        }

        .btn-outline:hover {
            background-color: var(--gold);
            color: var(--bg-main);
            transform: translateY(-3px);
        }

        /* Glassmorphism Card */
        .glass-card {
            background: var(--glass-bg);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border);
            border-radius: 8px;
            padding: 30px;
        }

        /* ==========================================================================
           2. NAVIGATION
           ========================================================================== */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            padding: 20px 0;
            transition: var(--transition);
        }

        .navbar.scrolled {
            background: rgba(15, 15, 15, 0.95);
            backdrop-filter: blur(10px);
            padding: 15px 0;
            border-bottom: 1px solid rgba(200, 162, 77, 0.1);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: var(--font-heading);
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--white);
            letter-spacing: 1px;
        }

        .logo span {
            color: var(--gold);
        }

        .nav-menu {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-link {
            font-size: 0.9rem;
            font-weight: 400;
            color: var(--gray-light);
        }

        .nav-link:hover {
            color: var(--gold);
        }

        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
            color: var(--white);
        }

        /* ==========================================================================
           3. HERO SECTION
           ========================================================================== */
        .hero {
            min-height: 100vh;
            position: relative;
            background: linear-gradient(rgba(15, 15, 15, 0.85), rgba(15, 15, 15, 0.95)), url('https://images.unsplash.com/photo-1455390582262-044cdead277a?auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            display: flex;
            align-items: center;
            padding-top: 100px;
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 50px;
            align-items: center;
        }

        .hero-badge {
            display: inline-block;
            padding: 6px 16px;
            border: 1px solid var(--gold);
            color: var(--gold);
            font-size: 0.8rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 20px;
            border-radius: 50px;
        }

        .hero-title {
            font-size: 3.5rem;
            line-height: 1.15;
            margin-bottom: 15px;
        }

        .hero-tagline {
            font-size: 1.5rem;
            font-family: var(--font-heading);
            font-style: italic;
            color: var(--gold);
            margin-bottom: 20px;
        }

        .hero-desc {
            font-size: 1rem;
            color: var(--gray-muted);
            margin-bottom: 30px;
            max-width: 600px;
        }

        .hero-info-box {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            margin-bottom: 30px;
        }

        .info-item h4 {
            font-size: 1rem;
            color: var(--gold);
            margin-bottom: 5px;
        }

        .info-item p {
            font-size: 0.85rem;
            color: var(--gray-light);
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
        }

        .hero-img-wrapper {
            position: relative;
            text-align: center;
        }

        .hero-img-wrapper img {
            border-radius: 12px;
            border: 2px solid var(--gold);
            box-shadow: 0 20px 40px rgba(0,0,0,0.8);
            filter: grayscale(20%);
            transition: var(--transition);
        }

        .hero-img-wrapper:hover img {
            filter: grayscale(0%);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            color: var(--gray-muted);
            font-size: 0.8rem;
            letter-spacing: 1px;
        }

        .scroll-indicator i {
            animation: bounce 2s infinite;
            color: var(--gold);
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        /* ==========================================================================
           4. TENTANG SECTION
           ========================================================================== */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 40px;
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
        }

        .about-content p {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 30px;
            color: var(--gray-light);
        }

        .about-quote {
            padding: 30px;
            border-left: 3px solid var(--gold);
            border-right: 3px solid var(--gold);
            background: rgba(200, 162, 77, 0.03);
            margin-top: 20px;
        }

        .about-quote blockquote {
            font-family: var(--font-heading);
            font-size: 1.4rem;
            font-style: italic;
            color: var(--gold);
        }

        /* ==========================================================================
           5. KEUNGGULAN SECTION
           ========================================================================== */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .feature-card {
            text-align: center;
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: var(--gold);
        }

        .feature-icon {
            width: 70px;
            height: 70px;
            background: rgba(200, 162, 77, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 1.8rem;
            color: var(--gold);
        }

        .feature-card h3 {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }

        /* ==========================================================================
           6. SILABUS SECTION
           ========================================================================== */
        .syllabus-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 25px;
        }

        .syllabus-card {
            position: relative;
            overflow: hidden;
            border-top: 3px solid var(--gold);
        }

        .syllabus-step {
            font-size: 0.8rem;
            color: var(--gold);
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .syllabus-card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            line-height: 1.4;
        }

        /* ==========================================================================
           7. FASILITAS SECTION
           ========================================================================== */
        .facilities-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .facility-item {
            display: flex;
            align-items: center;
            gap: 20px;
            padding: 20px;
            background: var(--bg-card);
            border-radius: 8px;
            border: 1px solid rgba(255,255,255,0.05);
        }

        .facility-item i {
            font-size: 1.5rem;
            color: var(--gold);
        }

        .facility-item span {
            font-weight: 500;
        }

        /* ==========================================================================
           8. INVESTASI & PENDAFTARAN SECTION
           ========================================================================== */
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 40px;
            align-items: stretch;
        }

        .pricing-card {
            text-align: center;
            border: 2px solid var(--gold);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .price-badge {
            background: var(--gold);
            color: var(--bg-main);
            padding: 4px 12px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            border-radius: 4px;
            display: inline-block;
            margin-bottom: 20px;
        }

        .price-amount {
            font-size: 3rem;
            font-family: var(--font-heading);
            color: var(--white);
            margin-bottom: 20px;
        }

        .bank-info {
            background: rgba(255,255,255,0.03);
            padding: 20px;
            border-radius: 6px;
            margin: 20px 0;
        }

        .bank-name {
            color: var(--gold);
            font-weight: 600;
            font-size: 1.1rem;
        }

        .account-number {
            font-size: 1.3rem;
            letter-spacing: 1px;
            margin: 5px 0;
            font-weight: 600;
            color: var(--white);
        }

        .registration-card {
            display: flex;
            flex-direction: column;
            justify-content: center;
            text-align: center;
        }

        /* ==========================================================================
           9. GALLERY SECTION
           ========================================================================== */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .gallery-item {
            position: relative;
            border-radius: 8px;
            overflow: hidden;
            height: 220px;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .gallery-item:hover img {
            transform: scale(1.08);
        }

        /* ==========================================================================
           10. TESTIMONIALS SECTION
           ========================================================================== */
        .testimonial-slider {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
        }

        .testimonial-wrapper {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }

        .testimonial-slide {
            min-width: 100%;
            box-sizing: border-box;
            text-align: center;
            padding: 20px;
        }

        .testimonial-text {
            font-size: 1.1rem;
            font-style: italic;
            margin-bottom: 20px;
            color: var(--gray-light);
        }

        .testimonial-author {
            font-family: var(--font-heading);
            color: var(--gold);
            font-size: 1.1rem;
        }

        .slider-dots {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 20px;
        }

        .dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(255,255,255,0.2);
            cursor: pointer;
            transition: var(--transition);
        }

        .dot.active {
            background: var(--gold);
            width: 25px;
            border-radius: 5px;
        }

        /* ==========================================================================
           11. FAQ SECTION
           ========================================================================== */
        .faq-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .faq-item {
            margin-bottom: 15px;
            border: 1px solid rgba(255,255,255,0.05);
            border-radius: 6px;
            overflow: hidden;
            background: var(--bg-card);
        }

        .faq-question {
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            font-weight: 500;
        }

        .faq-question i {
            color: var(--gold);
            transition: var(--transition);
        }

        .faq-answer {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease;
            background: rgba(0,0,0,0.2);
        }

        .faq-answer p {
            padding: 20px;
            color: var(--gray-muted);
            font-size: 0.95rem;
        }

        .faq-item.active .faq-question i {
            transform: rotate(180deg);
        }

        /* ==========================================================================
           12. CTA SECTION
           ========================================================================== */
        .cta-section {
            background: linear-gradient(135deg, #c8a24d 0%, #e5be65 100%);
            color: var(--bg-main);
            text-align: center;
            padding: 80px 0;
        }

        .cta-section h2 {
            color: var(--bg-main);
            font-size: 2.5rem;
            margin-bottom: 30px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .btn-dark {
            background-color: var(--bg-main);
            color: var(--gold);
        }

        .btn-dark:hover {
            background-color: #000;
            color: var(--white);
            transform: translateY(-3px);
        }

        /* ==========================================================================
           13. FOOTER
           ========================================================================== */
        footer {
            background: #080808;
            padding: 50px 0 20px;
            border-top: 1px solid rgba(255,255,255,0.05);
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-logo {
            font-family: var(--font-heading);
            font-size: 1.3rem;
            color: var(--white);
            margin-bottom: 15px;
        }

        .footer-logo span { color: var(--gold); }

        .footer-desc {
            color: var(--gray-muted);
            font-size: 0.9rem;
            max-width: 400px;
        }

        .footer-links h4 {
            color: var(--gold);
            font-size: 1rem;
            margin-bottom: 20px;
        }

        .footer-links ul li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: var(--gray-muted);
            font-size: 0.9rem;
        }

        .footer-links a:hover {
            color: var(--white);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.05);
            color: var(--gray-muted);
            font-size: 0.85rem;
        }

        /* ==========================================================================
           14. RESPONSIVE DESIGN (MOBILE FIRST OVERRIDES)
           ========================================================================== */
        @media (max-width: 992px) {
            .hero-grid {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-title { font-size: 2.8rem; }
            
            .hero-desc { margin: 0 auto 30px; }

            .hero-info-box {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-buttons {
                justify-content: center;
            }

            .hero-img-wrapper img {
                max-width: 300px;
                margin: 0 auto;
            }

            .footer-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .hamburger { display: block; }

            .nav-menu {
                position: fixed;
                top: 0;
                right: -100%;
                width: 80%;
                height: 100vh;
                background: var(--bg-main);
                flex-direction: column;
                justify-content: center;
                transition: 0.4s ease;
                border-left: 1px solid var(--glass-border);
            }

            .nav-menu.active {
                right: 0;
            }

            .hero-buttons {
                flex-direction: column;
            }

            .section-header h2 { font-size: 2rem; }
            .cta-section h2 { font-size: 1.8rem; }
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <nav class="navbar" id="navbar">
        <div class="container nav-container">
            <a href="#" class="logo">STUDIO MENULIS <span>CUCUK ESPE</span></a>
            <div class="hamburger" id="hamburger">
                <i class="fas fa-bars"></i>
            </div>
            <ul class="nav-menu" id="navMenu">
                <li><a href="#beranda" class="nav-link">Beranda</a></li>
                <li><a href="#tentang" class="nav-link">Tentang</a></li>
                <li><a href="#program" class="nav-link">Program</a></li>
                <li><a href="#silabus" class="nav-link">Silabus</a></li>
                <li><a href="#fasilitas" class="nav-link">Fasilitas</a></li>
                <li><a href="#pendaftaran" class="nav-link">Pendaftaran</a></li>
                <li><a href="#faq" class="nav-link">FAQ</a></li>
                <li><a href="#kontak" class="nav-link">Kontak</a></li>
            </ul>
        </div>
    </nav>

    <!-- HERO SECTION -->
    <section class="hero" id="beranda">
        <div class="container hero-grid">
            <div class="hero-content">
                <span class="hero-badge">Kelas Premium Via Zoom</span>
                <h1 class="hero-title">STUDIO MENULIS CUCUK ESPE</h1>
                <div class="hero-tagline">"Menemukan Suara, Menulis dengan Nyawa."</div>
                <p class="hero-desc">Belajar menulis langsung bersama penulis dan mentor berpengalaman melalui kelas interaktif premium.</p>
                
                <div class="hero-info-box">
                    <div class="info-item">
                        <h4>Program</h4>
                        <p>ANGKATAN AKSARA</p>
                    </div>
                    <div class="info-item">
                        <h4>Jadwal</h4>
                        <p>September 2026<br>Minggu, 19.00–21.00 WIB</p>
                    </div>
                    <div class="info-item">
                        <h4>Eksklusivitas</h4>
                        <p>Kuota Terbatas<br>Hanya 20 Peserta</p>
                    </div>
                </div>

                <div class="hero-buttons">
                    <a href="#pendaftaran" class="btn btn-gold">Daftar Sekarang</a>
                    <a href="#silabus" class="btn btn-outline">Lihat Silabus</a>
                </div>
            </div>

            <div class="hero-img-wrapper">
                <!-- Placeholder Mentor Image -->
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=600&q=80" alt="Cucuk Espe - Mentor Menulis">
            </div>
        </div>

        <div class="scroll-indicator">
            <span>GULIR KE BAWAH</span>
            <i class="fas fa-chevron-down"></i>
        </div>
    </section>

    <!-- SECTION TENTANG -->
    <section class="section-padding" id="tentang">
        <div class="container">
            <div class="section-header">
                <h2>Tentang Cucuk Espe</h2>
                <p>Mengenal lebih dekat ruang kreatif dan pengampu kelas</p>
            </div>
            
            <div class="about-grid">
                <div class="about-content">
                    <p>Cucuk Espe adalah penulis, penyair, cerpenis, esais, dramawan, sekaligus mentor menulis yang telah berkarya selama bertahun-tahun. Studio Menulis Cucuk Espe lahir sebagai ruang belajar bagi siapa pun yang ingin menemukan suara kepenulisannya sendiri melalui proses kreatif yang jujur, terarah, dan membumi.</p>
                    
                    <div class="about-quote">
                        <blockquote>"Tulisan yang baik tidak lahir dari kepandaian semata, tetapi dari keberanian menyelami kehidupan."</blockquote>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION KEUNGGULAN (PROGRAM) -->
    <section class="section-padding" id="program" style="background: #121212;">
        <div class="container">
            <div class="section-header">
                <h2>Keunggulan Program</h2>
                <p>Metode pembelajaran dirancang untuk hasil nyata</p>
            </div>

            <div class="features-grid">
                <div class="glass-card feature-card">
                    <div class="feature-icon"><i class="fas fa-user-graduate"></i></div>
                    <h3>Mentor Berpengalaman</h3>
                    <p style="color: var(--gray-muted); font-size: 0.85rem;">Bimbingan intensif langsung dari praktisi sastra berpengalaman.</p>
                </div>
                <div class="glass-card feature-card">
                    <div class="feature-icon"><i class="fas fa-video"></i></div>
                    <h3>Kelas Interaktif</h3>
                    <p style="color: var(--gray-muted); font-size: 0.85rem;">Diskusi dua arah via Zoom Meeting secara langsung.</p>
                </div>
                <div class="glass-card feature-card">
                    <div class="feature-icon"><i class="fas fa-feather-alt"></i></div>
                    <h3>Bedah Karya</h3>
                    <p style="color: var(--gray-muted); font-size: 0.85rem;">Ulasan dan masukan konstruktif mendalam untuk draf tulisan Anda.</p>
                </div>
                <div class="glass-card feature-card">
                    <div class="feature-icon"><i class="fas fa-users"></i></div>
                    <h3>Komunitas Penulis</h3>
                    <p style="color: var(--gray-muted); font-size: 0.85rem;">Ruang bertukar ide bersama rekan sefrekuensi.</p>
                </div>
                <div class="glass-card feature-card">
                    <div class="feature-icon"><i class="fas fa-play-circle"></i></div>
                    <h3>Rekaman Zoom</h3>
                    <p style="color: var(--gray-muted); font-size: 0.85rem;">Akses rekaman kelas bagi yang ingin mengulang materi.</p>
                </div>
                <div class="glass-card feature-card">
                    <div class="feature-icon"><i class="fas fa-certificate"></i></div>
                    <h3>Sertifikat Digital</h3>
                    <p style="color: var(--gray-muted); font-size: 0.85rem;">Apresiasi kelulusan dan bukti keikutsertaan resmi.</p>
                </div>
                <div class="glass-card feature-card">
                    <div class="feature-icon"><i class="fas fa-file-pdf"></i></div>
                    <h3>Modul PDF</h3>
                    <p style="color: var(--gray-muted); font-size: 0.85rem;">Materi panduan eksklusif yang dapat disimpan selamanya.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION SILABUS -->
    <section class="section-padding" id="silabus">
        <div class="container">
            <div class="section-header">
                <h2>Silabus Kurikulum</h2>
                <p>4 Pertemuan terstruktur menuju penulisan berpijak nyawa</p>
            </div>

            <div class="syllabus-grid">
                <div class="glass-card syllabus-card">
                    <div class="syllabus-step">Pertemuan 1</div>
                    <h3>Menemukan Ide yang Layak Ditulis</h3>
                    <p style="color: var(--gray-muted); font-size: 0.9rem;">Bagaimana menggali gagasan dari pengalaman hidup dan mengubahnya menjadi bahan tulisan yang memikat.</p>
                </div>

                <div class="glass-card syllabus-card">
                    <div class="syllabus-step">Pertemuan 2</div>
                    <h3>Menghidupkan Tulisan</h3>
                    <p style="color: var(--gray-muted); font-size: 0.9rem;">Menggunakan rasa, narasi, dan dinamika deskripsi agar tulisan terasa bernyawa dan emosional.</p>
                </div>

                <div class="glass-card syllabus-card">
                    <div class="syllabus-step">Pertemuan 3</div>
                    <h3>Editing dan Penyempurnaan</h3>
                    <p style="color: var(--gray-muted); font-size: 0.9rem;">Teknik memeriksa kembali struktur, pilihan kata, dan ritme kalimat tanpa mengorbankan keaslian suara.</p>
                </div>

                <div class="glass-card syllabus-card">
                    <div class="syllabus-step">Pertemuan 4</div>
                    <h3>Publikasi dan Konsistensi Berkarya</h3>
                    <p style="color: var(--gray-muted); font-size: 0.9rem;">Langkah mendistribusikan karya serta strategi merawat konsistensi menulis dalam jangka panjang.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION FASILITAS -->
    <section class="section-padding" id="fasilitas" style="background: #121212;">
        <div class="container">
            <div class="section-header">
                <h2>Fasilitas Peserta</h2>
                <p>Semua yang Anda dapatkan selama dan setelah program</p>
            </div>

            <div class="facilities-grid">
                <div class="facility-item">
                    <i class="fas fa-desktop"></i>
                    <span>Empat kali Zoom Meeting</span>
                </div>
                <div class="facility-item">
                    <i class="fas fa-book-open"></i>
                    <span>Modul PDF Eksklusif</span>
                </div>
                <div class="facility-item">
                    <i class="fab fa-whatsapp"></i>
                    <span>Grup WhatsApp Eksklusif</span>
                </div>
                <div class="facility-item">
                    <i class="fas fa-film"></i>
                    <span>Akses Rekaman Kelas</span>
                </div>
                <div class="facility-item">
                    <i class="fas fa-edit"></i>
                    <span>Sesi Bedah Karya Langsung</span>
                </div>
                <div class="facility-item">
                    <i class="fas fa-award"></i>
                    <span>Sertifikat Digital Kelulusan</span>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION INVESTASI & PENDAFTARAN -->
    <section class="section-padding" id="pendaftaran">
        <div class="container">
            <div class="section-header">
                <h2>Investasi & Pendaftaran</h2>
                <p>Amankan kursi Anda sekarang, kuota terbatas untuk 20 peserta</p>
            </div>

            <div class="pricing-grid">
                <!-- Box Investasi -->
                <div class="glass-card pricing-card">
                    <div>
                        <span class="price-badge">Investasi Belajar</span>
                        <div class="price-amount">Rp150.000</div>
                        <p style="color: var(--gray-muted); font-size: 0.9rem;">Transfer Pembayaran ke:</p>
                        
                        <div class="bank-info">
                            <div class="bank-name">SeaBank</div>
                            <div class="account-number">901954878338</div>
                            <div style="font-size: 0.85rem; color: var(--gray-muted);">a.n. Cucuk Suparno</div>
                        </div>
                    </div>
                </div>

                <!-- Box Formulir -->
                <div class="glass-card registration-card">
                    <h3 style="margin-bottom: 15px; font-size: 1.5rem;">Langkah Selanjutnya</h3>
                    <p style="color: var(--gray-muted); margin-bottom: 25px; font-size: 0.95rem;">
                        Setelah melakukan pembayaran transfer, silakan klik tombol di bawah ini untuk mengisi formulir pendaftaran serta mengunggah bukti transfer Anda.
                    </p>
                    <div>
                        <!-- Ganti '#' dengan Link Google Form Anda -->
                        <a href="https://forms.google.com" target="_blank" rel="noopener noreferrer" class="btn btn-gold" style="width: 100%;">
                            DAFTAR SEKARANG <i class="fas fa-external-link-alt" style="margin-left: 8px; font-size: 0.8rem;"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION TESTIMONI -->
    <section class="section-padding" style="background: #121212;">
        <div class="container">
            <div class="section-header">
                <h2>Kata Alumni</h2>
                <p>Pengalaman mereka yang telah menemukan suara kepenulisannya</p>
            </div>

            <div class="testimonial-slider">
                <div class="testimonial-wrapper" id="testimonialWrapper">
                    <div class="testimonial-slide">
                        <p class="testimonial-text">"Mengikuti kelas Mas Cucuk Espe membuka pandangan baru. Saya tidak lagi sekadar merangkai kata, tapi belajar bagaimana menuangkan nyawa ke dalam tiap paragraf."</p>
                        <div class="testimonial-author">- Rian A., Alumni Angkatan 1</div>
                    </div>
                    <div class="testimonial-slide">
                        <p class="testimonial-text">"Sesi bedah karyanya jujur dan sangat berharga. Saya menemukan karakter tulisan saya sendiri yang selama ini tersembunyi."</p>
                        <div class="testimonial-author">- Sarah M., Alumni Angkatan 2</div>
                    </div>
                    <div class="testimonial-slide">
                        <p class="testimonial-text">"Suasana kelas sangat hangat dan kondusif. Materi PDF dan rekaman kelas sangat membantu untuk belajar ulang kapan saja."</p>
                        <div class="testimonial-author">- Budi S., Alumni Angkatan 2</div>
                    </div>
                </div>
                <div class="slider-dots" id="sliderDots"></div>
            </div>
        </div>
    </section>

    <!-- SECTION GALLERY -->
    <section class="section-padding">
        <div class="container">
            <div class="section-header">
                <h2>Galeri Kegiatan</h2>
                <p>Dokumentasi perjalanan kelas dan ruang diskusi</p>
            </div>

            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1515378791036-0648a3ef77b2?auto=format&fit=crop&w=500&q=80" alt="Galeri 1">
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?auto=format&fit=crop&w=500&q=80" alt="Galeri 2">
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1457369804613-52c61a468e7d?auto=format&fit=crop&w=500&q=80" alt="Galeri 3">
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1434030216411-0b793f4b4173?auto=format&fit=crop&w=500&q=80" alt="Galeri 4">
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION FAQ -->
    <section class="section-padding" id="faq" style="background: #121212;">
        <div class="container">
            <div class="section-header">
                <h2>Pertanyaan Umum</h2>
                <p>Hal yang sering ditanyakan seputar kelas</p>
            </div>

            <div class="faq-container">
                <div class="faq-item">
                    <div class="faq-question">
                        Apakah pemula boleh ikut?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>Sangat boleh. Kelas ini dirancang terbuka untuk siapa saja, baik pemula yang baru ingin memulai maupun penulis yang ingin mengasah kembali kedalaman karya mereka.</p>
                    </div>
                </div>

                <div class="faq-item">
                    <div class="faq-question">
                        Apakah kelas direkam?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>Ya, setiap sesi live Zoom akan direkam. Rekaman akan dibagikan kepada peserta untuk dapat dipelajari kembali kapan saja.</p>
                    </div>
                </div>

                <div class="faq-item">
                    <div class="faq-question">
                        Apakah mendapat sertifikat?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>Ya, seluruh peserta yang menyelesaikan rangkaian kelas akan mendapatkan Sertifikat Digital resmi dari Studio Menulis Cucuk Espe.</p>
                    </div>
                </div>

                <div class="faq-item">
                    <div class="faq-question">
                        Bagaimana jika berhalangan hadir saat kelas live?
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="faq-answer">
                        <p>Anda tidak perlu khawatir. Anda tetap dapat menyimak materi melalui rekaman Zoom yang disediakan dan mengajukan pertanyaan di grup WhatsApp eksklusif.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECTION CTA -->
    <section class="cta-section">
        <div class="container">
            <h2>Mari Menjadi Bagian dari Studio Menulis Cucuk Espe.</h2>
            <a href="#pendaftaran" class="btn btn-dark">DAFTAR SEKARANG</a>
        </div>
    </section>

    <!-- FOOTER & KONTAK -->
    <footer id="kontak">
        <div class="container">
            <div class="footer-grid">
                <div>
                    <div class="footer-logo">STUDIO MENULIS <span>CUCUK ESPE</span></div>
                    <p class="footer-desc">Ruang belajar kreatif untuk menemukan suara kepenulisan yang jujur, terarah, dan bernyawa.</p>
                </div>
                <div class="footer-links">
                    <h4>Navigasi</h4>
                    <ul>
                        <li><a href="#beranda">Beranda</a></li>
                        <li><a href="#tentang">Tentang</a></li>
                        <li><a href="#silabus">Silabus</a></li>
                        <li><a href="#pendaftaran">Pendaftaran</a></li>
                    </ul>
                </div>
                <div class="footer-links">
                    <h4>Kontak & Info</h4>
                    <ul>
                        <li><a href="#"><i class="fab fa-whatsapp" style="margin-right: 8px;"></i> WhatsApp Admin</a></li>
                        <li><a href="#"><i class="fab fa-instagram" style="margin-right: 8px;"></i> @cucukespe</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2026 Studio Menulis Cucuk Espe. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <!-- ==========================================================================
       JAVASCRIPT
       ========================================================================== -->
    <script>
        // 1. Navbar Sticky & Scroll Effect
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // 2. Mobile Menu Toggle
        const hamburger = document.getElementById('hamburger');
        const navMenu = document.getElementById('navMenu');

        hamburger.addEventListener('click', () => {
            navMenu.classList.toggle('active');
            hamburger.querySelector('i').classList.toggle('fa-bars');
            hamburger.querySelector('i').classList.toggle('fa-times');
        });

        // Close menu when clicking a link
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('active');
                hamburger.querySelector('i').classList.add('fa-bars');
                hamburger.querySelector('i').classList.remove('fa-times');
            });
        });

        // 3. FAQ Accordion Logic
        const faqItems = document.querySelectorAll('.faq-item');

        faqItems.forEach(item => {
            const question = item.querySelector('.faq-question');
            const answer = item.querySelector('.faq-answer');

            question.addEventListener('click', () => {
                const isOpen = item.classList.contains('active');
                
                // Close all FAQ items
                faqItems.forEach(otherItem => {
                    otherItem.classList.remove('active');
                    otherItem.querySelector('.faq-answer').style.maxHeight = null;
                });

                // Toggle current item
                if (!isOpen) {
                    item.classList.add('active');
                    answer.style.maxHeight = answer.scrollHeight + "px";
                }
            });
        });

        // 4. Testimonial Slider Logic
        const wrapper = document.getElementById('testimonialWrapper');
        const slides = document.querySelectorAll('.testimonial-slide');
        const dotsContainer = document.getElementById('sliderDots');
        let currentSlide = 0;

        // Create Dots
        slides.forEach((_, index) => {
            const dot = document.createElement('div');
            dot.classList.add('dot');
            if (index === 0) dot.classList.add('active');
            dot.addEventListener('click', () => goToSlide(index));
            dotsContainer.appendChild(dot);
        });

        const dots = document.querySelectorAll('.dot');

        function goToSlide(index) {
            currentSlide = index;
            wrapper.style.transform = `translateX(-${index * 100}%)`;
            dots.forEach(dot => dot.classList.remove('active'));
            dots[index].classList.add('active');
        }

        // Auto slide every 5 seconds
        setInterval(() => {
            currentSlide = (currentSlide + 1) % slides.length;
            goToSlide(currentSlide);
        }, 5000);
    </script>
</body>
</html>
