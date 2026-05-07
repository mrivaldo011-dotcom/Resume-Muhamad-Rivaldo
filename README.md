<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resume - Muhamad Rivaldo</title>
    <style>
        /* ===== RESET & BASE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --primary-light: #dbeafe;
            --dark: #1e293b;
            --gray: #64748b;
            --light-gray: #f1f5f9;
            --white: #ffffff;
            --shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
            --shadow-lg: 0 10px 40px rgba(0, 0, 0, 0.12);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--dark);
            line-height: 1.7;
            background: var(--light-gray);
        }

        a {
            text-decoration: none;
            color: var(--primary);
        }

        /* ===== NAVBAR ===== */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 1px 10px rgba(0, 0, 0, 0.06);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .navbar .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 40px;
            max-width: 1100px;
            margin: auto;
        }

        .navbar .logo {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--dark);
        }

        .navbar .logo span {
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        .nav-links a {
            color: var(--gray);
            font-weight: 500;
            font-size: 0.95rem;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s;
        }

        .nav-links a:hover,
        .nav-links a.active {
            color: var(--primary);
        }

        .nav-links a:hover::after,
        .nav-links a.active::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
            gap: 5px;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: var(--dark);
            border-radius: 3px;
            transition: 0.3s;
        }

        /* ===== HERO ===== */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(135deg, #1e3a5f 0%, #2563eb 50%, #3b82f6 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 600px;
            height: 600px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -10%;
            width: 400px;
            height: 400px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.03);
        }

        .hero .container {
            max-width: 1100px;
            margin: auto;
            padding: 0 40px;
            display: flex;
            align-items: center;
            gap: 60px;
            position: relative;
            z-index: 1;
        }

        .hero-text {
            flex: 1;
        }

        .hero-text .greeting {
            font-size: 1.1rem;
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 10px;
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .hero-text h1 {
            font-size: 3.2rem;
            color: var(--white);
            margin-bottom: 8px;
            line-height: 1.2;
        }

        .hero-text .title {
            font-size: 1.4rem;
            color: rgba(255, 255, 255, 0.9);
            margin-bottom: 20px;
            font-weight: 300;
        }

        .hero-text p {
            color: rgba(255, 255, 255, 0.75);
            font-size: 1.05rem;
            margin-bottom: 30px;
            max-width: 500px;
        }

        .hero-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 0.95rem;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: var(--white);
            color: var(--primary);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
        }

        .btn-outline {
            background: transparent;
            color: var(--white);
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        .btn-outline:hover {
            border-color: var(--white);
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-2px);
        }

        .hero-image {
            flex-shrink: 0;
        }

        .hero-image .avatar {
            width: 280px;
            height: 280px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.15);
            border: 4px solid rgba(255, 255, 255, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 6rem;
            color: rgba(255, 255, 255, 0.6);
            position: relative;
        }

        .hero-image .avatar::before {
            content: '';
            position: absolute;
            inset: -10px;
            border-radius: 50%;
            border: 2px dashed rgba(255, 255, 255, 0.2);
            animation: spin 20s linear infinite;
        }

        @keyframes spin {
            100% { transform: rotate(360deg); }
        }

        /* ===== SECTIONS ===== */
        section {
            padding: 80px 40px;
        }

        .section-container {
            max-width: 1100px;
            margin: auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 2rem;
            color: var(--dark);
            margin-bottom: 10px;
        }

        .section-title .underline {
            width: 60px;
            height: 4px;
            background: var(--primary);
            margin: 0 auto;
            border-radius: 2px;
        }

        .section-title p {
            color: var(--gray);
            margin-top: 10px;
        }

        /* ===== ABOUT ===== */
        .about {
            background: var(--white);
        }

        .about-content {
            display: flex;
            gap: 50px;
            align-items: center;
        }

        .about-info {
            flex: 1;
        }

        .about-info h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--dark);
        }

        .about-info p {
            color: var(--gray);
            margin-bottom: 20px;
            font-size: 1.02rem;
        }

        .about-details {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin-bottom: 25px;
        }

        .about-details .detail {
            font-size: 0.95rem;
        }

        .about-details .detail strong {
            color: var(--dark);
            min-width: 100px;
            display: inline-block;
        }

        .about-details .detail span {
            color: var(--gray);
        }

        .about-stats {
            display: flex;
            gap: 40px;
            margin-top: 30px;
        }

        .stat {
            text-align: center;
        }

        .stat .number {
            font-size: 2.2rem;
            font-weight: 700;
            color: var(--primary);
        }

        .stat .label {
            font-size: 0.85rem;
            color: var(--gray);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* ===== EXPERIENCE ===== */
        .experience {
            background: var(--light-gray);
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 20px;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(to bottom, var(--primary), var(--primary-light));
            border-radius: 3px;
        }

        .timeline-item {
            padding-left: 60px;
            margin-bottom: 35px;
            position: relative;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: 12px;
            top: 8px;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--white);
            border: 3px solid var(--primary);
            z-index: 1;
        }

        .timeline-item:hover::before {
            background: var(--primary);
            transition: 0.3s;
        }

        .timeline-card {
            background: var(--white);
            padding: 25px 30px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .timeline-card:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        .timeline-card .date {
            display: inline-block;
            background: var(--primary-light);
            color: var(--primary);
            padding: 4px 14px;
            border-radius: 20px;
            font-size: 0.82rem;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .timeline-card h3 {
            font-size: 1.2rem;
            color: var(--dark);
            margin-bottom: 5px;
        }

        .timeline-card .company {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 10px;
            font-size: 0.95rem;
        }

        .timeline-card p {
            color: var(--gray);
            font-size: 0.95rem;
        }

        .timeline-card ul {
            list-style: none;
            margin-top: 10px;
        }

        .timeline-card ul li {
            color: var(--gray);
            font-size: 0.92rem;
            padding: 3px 0;
            position: relative;
            padding-left: 18px;
        }

        .timeline-card ul li::before {
            content: '▸';
            position: absolute;
            left: 0;
            color: var(--primary);
            font-weight: bold;
        }

        /* ===== EDUCATION ===== */
        .education {
            background: var(--white);
        }

        .edu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 25px;
            max-width: 800px;
            margin: auto;
        }

        .edu-card {
            background: var(--light-gray);
            padding: 30px;
            border-radius: 12px;
            border-left: 4px solid var(--primary);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .edu-card:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow);
        }

        .edu-card .year {
            color: var(--primary);
            font-weight: 700;
            font-size: 0.9rem;
            margin-bottom: 8px;
        }

        .edu-card h3 {
            font-size: 1.15rem;
            color: var(--dark);
            margin-bottom: 5px;
        }

        .edu-card .school {
            color: var(--gray);
            font-size: 0.95rem;
        }

        /* ===== SKILLS ===== */
        .skills {
            background: var(--light-gray);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .skill-category h3 {
            font-size: 1.1rem;
            color: var(--dark);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary-light);
        }

        .skill-item {
            margin-bottom: 18px;
        }

        .skill-item .skill-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 6px;
        }

        .skill-item .skill-name {
            font-weight: 600;
            font-size: 0.92rem;
            color: var(--dark);
        }

        .skill-item .skill-percent {
            font-size: 0.85rem;
            color: var(--primary);
            font-weight: 700;
        }

        .skill-bar {
            height: 8px;
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
        }

        .skill-bar .fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), #60a5fa);
            border-radius: 10px;
            width: 0;
            transition: width 1.5s ease;
        }

        .tags-container {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }

        .tag {
            background: var(--white);
            color: var(--dark);
            padding: 8px 18px;
            border-radius: 25px;
            font-size: 0.88rem;
            font-weight: 500;
            border: 1px solid #e2e8f0;
            transition: all 0.3s;
        }

        .tag:hover {
            background: var(--primary);
            color: var(--white);
            border-color: var(--primary);
            transform: translateY(-2px);
        }

        /* ===== PORTFOLIO ===== */
        .portfolio {
            background: var(--white);
        }

        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .portfolio-card {
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s, box-shadow 0.3s;
            background: var(--white);
        }

        .portfolio-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .portfolio-card .card-image {
            height: 200px;
            background: linear-gradient(135deg, var(--primary), #60a5fa);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: rgba(255, 255, 255, 0.5);
        }

        .portfolio-card .card-body {
            padding: 20px;
        }

        .portfolio-card h3 {
            font-size: 1.1rem;
            margin-bottom: 8px;
            color: var(--dark);
        }

        .portfolio-card p {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 15px;
        }

        .portfolio-card .tech-stack {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        .portfolio-card .tech-stack span {
            background: var(--primary-light);
            color: var(--primary);
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.78rem;
            font-weight: 600;
        }

        /* ===== CONTACT ===== */
        .contact {
            background: var(--dark);
            color: var(--white);
        }

        .contact .section-title h2 {
            color: var(--white);
        }

        .contact .section-title p {
            color: rgba(255, 255, 255, 0.6);
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            max-width: 900px;
            margin: auto;
        }

        .contact-info-list {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .contact-item .icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            background: rgba(37, 99, 235, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            flex-shrink: 0;
        }

        .contact-item h4 {
            font-size: 0.85rem;
            color: rgba(255, 255, 255, 0.5);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 3px;
        }

        .contact-item p {
            color: rgba(255, 255, 255, 0.9);
            font-size: 0.95rem;
        }

        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .contact-form input,
        .contact-form textarea {
            padding: 14px 18px;
            border-radius: 10px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            background: rgba(255, 255, 255, 0.05);
            color: var(--white);
            font-size: 0.95rem;
            font-family: inherit;
            transition: border-color 0.3s;
        }

        .contact-form input::placeholder,
        .contact-form textarea::placeholder {
            color: rgba(255, 255, 255, 0.3);
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: var(--primary);
        }

        .contact-form textarea {
            resize: vertical;
            min-height: 120px;
        }

        .contact-form .btn-submit {
            padding: 14px 32px;
            border-radius: 50px;
            background: var(--primary);
            color: var(--white);
            font-weight: 600;
            font-size: 0.95rem;
            border: none;
            cursor: pointer;
            transition: all 0.3s;
        }

        .contact-form .btn-submit:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
        }

        .social-links {
            display: flex;
            gap: 12px;
            margin-top: 25px;
        }

        .social-links a {
            width: 42px;
            height: 42px;
            border-radius: 10px;
            background: rgba(255, 255, 255, 0.08);
            display: flex;
            align-items: center;
            justify-content: center;
            color: rgba(255, 255, 255, 0.7);
            font-size: 1.1rem;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background: var(--primary);
            color: var(--white);
            transform: translateY(-3px);
        }

        /* ===== FOOTER ===== */
        footer {
            background: #0f172a;
            text-align: center;
            padding: 25px;
            color: rgba(255, 255, 255, 0.4);
            font-size: 0.88rem;
        }

        /* ===== SCROLL TO TOP ===== */
        .scroll-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--primary);
            color: var(--white);
            border: none;
            cursor: pointer;
            font-size: 1.2rem;
            display: none;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 15px rgba(37, 99, 235, 0.4);
            transition: all 0.3s;
            z-index: 999;
        }

        .scroll-top:hover {
            transform: translateY(-3px);
        }

        .scroll-top.show {
            display: flex;
        }

        /* ===== ANIMATIONS ===== */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            .navbar .container {
                padding: 15px 20px;
            }

            .hamburger {
                display: flex;
            }

            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 260px;
                height: 100vh;
                background: var(--white);
                flex-direction: column;
                padding: 80px 30px 30px;
                box-shadow: var(--shadow-lg);
                transition: right 0.3s;
            }

            .nav-links.open {
                right: 0;
            }

            .hero .container {
                flex-direction: column-reverse;
                text-align: center;
                padding-top: 120px;
            }

            .hero-text h1 {
                font-size: 2.2rem;
            }

            .hero-text p {
                margin: 0 auto 30px;
            }

            .hero-buttons {
                justify-content: center;
            }

            .hero-image .avatar {
                width: 200px;
                height: 200px;
                font-size: 4rem;
            }

            .about-content {
                flex-direction: column;
            }

            .about-details {
                grid-template-columns: 1fr;
            }

            .about-stats {
                justify-content: center;
            }

            .contact-content {
                grid-template-columns: 1fr;
            }

            section {
                padding: 60px 20px;
            }
        }

        @media (max-width: 480px) {
            .hero-text h1 {
                font-size: 1.8rem;
            }

            .hero-text .title {
                font-size: 1.1rem;
            }

            .portfolio-grid {
                grid-template-columns: 1fr;
            }

            .edu-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <nav class="navbar">
        <div class="container">
            <a href="#" class="logo">Rivaldo<span>.</span></a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#hero" class="active">Beranda</a></li>
                <li><a href="#about">Tentang</a></li>
                <li><a href="#experience">Pengalaman</a></li>
                <li><a href="#education">Pendidikan</a></li>
                <li><a href="#skills">Keahlian</a></li>
                <li><a href="#portfolio">Portfolio</a></li>
                <li><a href="#contact">Kontak</a></li>
            </ul>
            <div class="hamburger" id="hamburger" onclick="toggleMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- HERO -->
    <section class="hero" id="hero">
        <div class="container">
            <div class="hero-text">
                <p class="greeting">👋 Halo, saya</p>
                <h1>Muhamad Rivaldo</h1>
                <p class="title">Mahasiswa Broadcasting | Semester 2</p>
                <p>Mahasiswa aktif jurusan Broadcasting yang antusias di dunia media, produksi konten, dan komunikasi kreatif. Berpengalaman dalam PKL dan pengelolaan usaha mandiri.</p>
                <div class="hero-buttons">
                    <a href="#contact" class="btn btn-primary">📩 Hubungi Saya</a>
                    <a href="#portfolio" class="btn btn-outline">Lihat Karya →</a>
                </div>
            </div>
            <div class="hero-image">
                <div class="avatar">🎬</div>
            </div>
        </div>
    </section>

    <!-- ABOUT -->
    <section class="about" id="about">
        <div class="section-container">
            <div class="section-title">
                <h2>Tentang Saya</h2>
                <div class="underline"></div>
            </div>
            <div class="about-content fade-in">
                <div class="about-info">
                    <h3>Mahasiswa Kreatif & Berjiwa Wirausaha</h3>
                    <p>Saya adalah mahasiswa semester 2 jurusan Broadcasting yang berbasis di Jakarta, Indonesia. Saya memiliki ketertarikan besar terhadap dunia media, produksi video, dan komunikasi publik. Selain aktif berkuliah, saya juga memiliki pengalaman nyata dari PKL dan mengelola usaha sendiri.</p>
                    <div class="about-details">
                        <div class="detail">
                            <strong>Nama:</strong> <span>Muhamad Rivaldo</span>
                        </div>
                        <div class="detail">
                            <strong>Email:</strong> <span>rivaldo@email.com</span>
                        </div>
                        <div class="detail">
                            <strong>Lokasi:</strong> <span>Jakarta, Indonesia</span>
                        </div>
                        <div class="detail">
                            <strong>Status:</strong> <span>Mahasiswa Aktif Semester 2</span>
                        </div>
                    </div>
                    <a href="#" class="btn btn-primary" style="background: var(--primary); color: white;">📄 Download CV</a>
                </div>
                <div class="about-stats">
                    <div class="stat">
                        <div class="number" data-target="2">0</div>
                        <div class="label">Semester Aktif</div>
                    </div>
                    <div class="stat">
                        <div class="number" data-target="3">0</div>
                        <div class="label">Bulan PKL</div>
                    </div>
                    <div class="stat">
                        <div class="number" data-target="3">0</div>
                        <div class="label">Tahun Usaha</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- EXPERIENCE -->
    <section class="experience" id="experience">
        <div class="section-container">
            <div class="section-title">
                <h2>Pengalaman</h2>
                <div class="underline"></div>
                <p>Pengalaman kerja dan usaha saya</p>
            </div>
            <div class="timeline">
                <div class="timeline-item fade-in">
                    <div class="timeline-card">
                        <span class="date">Februari - Mei 2019</span>
                        <h3>Praktik Kerja Lapangan (PKL)</h3>
                        <p class="company">Program PKL — 3 Bulan</p>
                        <ul>
                            <li>Menjalani PKL selama 3 bulan di bidang broadcasting dan media</li>
                            <li>Mempelajari proses produksi konten secara langsung di lapangan</li>
                            <li>Berkolaborasi dengan tim profesional dalam dunia penyiaran</li>
                        </ul>
                    </div>
                </div>
                <div class="timeline-item fade-in">
                    <div class="timeline-card">
                        <span class="date">2020 - 2023</span>
                        <h3>Pemilik & Pengelola Usaha Madu</h3>
                        <p class="company">Usaha Mandiri — 3 Tahun</p>
                        <ul>
                            <li>Mengelola usaha penjualan madu secara mandiri selama 3 tahun</li>
                            <li>Menangani operasional, pemasaran, dan distribusi produk madu</li>
                            <li>Membangun relasi dengan pelanggan dan menjaga kualitas produk</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- EDUCATION -->
    <section class="education" id="education">
        <div class="section-container">
            <div class="section-title">
                <h2>Pendidikan</h2>
                <div class="underline"></div>
            </div>
            <div class="edu-grid">
                <div class="edu-card fade-in">
                    <div class="year">2024 - Sekarang</div>
                    <h3>Broadcasting (Semester 2)</h3>
                    <p class="school">Jurusan Ilmu Komunikasi — Penyiaran</p>
                </div>
                <div class="edu-card fade-in">
                    <div class="year">Feb - Mei 2019</div>
                    <h3>Praktik Kerja Lapangan (PKL)</h3>
                    <p class="school">Bidang Broadcasting & Media — 3 Bulan</p>
                </div>
            </div>
        </div>
    </section>

    <!-- SKILLS -->
    <section class="skills" id="skills">
        <div class="section-container">
            <div class="section-title">
                <h2>Keahlian</h2>
                <div class="underline"></div>
                <p>Teknologi dan tools yang saya kuasai</p>
            </div>
            <div class="skills-grid fade-in">
                <div class="skill-category">
                    <h3>🎬 Produksi & Broadcasting</h3>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Produksi Video</span>
                            <span class="skill-percent">80%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="80"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Editing Video</span>
                            <span class="skill-percent">75%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="75"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Fotografi</span>
                            <span class="skill-percent">70%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="70"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Penulisan Naskah</span>
                            <span class="skill-percent">78%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="78"></div></div>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>💼 Wirausaha & Pemasaran</h3>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Manajemen Usaha</span>
                            <span class="skill-percent">85%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="85"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Pemasaran Produk</span>
                            <span class="skill-percent">80%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="80"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Komunikasi Publik</span>
                            <span class="skill-percent">82%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="82"></div></div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span class="skill-name">Media Sosial</span>
                            <span class="skill-percent">88%</span>
                        </div>
                        <div class="skill-bar"><div class="fill" data-width="88"></div></div>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>🛠️ Tools & Lainnya</h3>
                    <div class="tags-container">
                        <span class="tag">Adobe Premiere</span>
                        <span class="tag">Adobe Photoshop</span>
                        <span class="tag">Canva</span>
                        <span class="tag">CapCut</span>
                        <span class="tag">OBS Studio</span>
                        <span class="tag">Microsoft Office</span>
                        <span class="tag">Instagram</span>
                        <span class="tag">YouTube</span>
                        <span class="tag">TikTok</span>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- PORTFOLIO -->
    <section class="portfolio" id="portfolio">
        <div class="section-container">
            <div class="section-title">
                <h2>Portfolio</h2>
                <div class="underline"></div>
                <p>Beberapa proyek yang telah saya kerjakan</p>
            </div>
            <div class="portfolio-grid">
                <div class="portfolio-card fade-in">
                    <div class="card-image">🎥</div>
                    <div class="card-body">
                        <h3>Konten Video Promosi Madu</h3>
                        <p>Membuat dan memproduksi video promosi produk madu untuk keperluan pemasaran di media sosial selama mengelola usaha.</p>
                        <div class="tech-stack">
                            <span>Produksi Video</span>
                            <span>Editing</span>
                            <span>Marketing</span>
                        </div>
                    </div>
                </div>
                <div class="portfolio-card fade-in">
                    <div class="card-image" style="background: linear-gradient(135deg, #7c3aed, #a78bfa);">📻</div>
                    <div class="card-body">
                        <h3>Laporan PKL Broadcasting</h3>
                        <p>Dokumentasi dan laporan pengalaman selama 3 bulan PKL di bidang broadcasting dan penyiaran media.</p>
                        <div class="tech-stack">
                            <span>Broadcasting</span>
                            <span>Penulisan</span>
                            <span>Dokumentasi</span>
                        </div>
                    </div>
                </div>
                <div class="portfolio-card fade-in">
                    <div class="card-image" style="background: linear-gradient(135deg, #059669, #34d399);">🍯</div>
                    <div class="card-body">
                        <h3>Usaha Madu Mandiri</h3>
                        <p>Mengelola usaha penjualan madu secara mandiri selama 3 tahun (2020–2023), termasuk pemasaran dan distribusi produk.</p>
                        <div class="tech-stack">
                            <span>Wirausaha</span>
                            <span>Manajemen</span>
                            <span>Pemasaran</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CONTACT -->
    <section class="contact" id="contact">
        <div class="section-container">
            <div class="section-title">
                <h2>Hubungi Saya</h2>
                <div class="underline"></div>
                <p>Tertarik untuk bekerja sama? Jangan ragu untuk menghubungi!</p>
            </div>
            <div class="contact-content fade-in">
                <div>
                    <div class="contact-info-list">
                        <div class="contact-item">
                            <div class="icon">📧</div>
                            <div>
                                <h4>Email</h4>
                                <p>rivaldo@email.com</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <div class="icon">📱</div>
                            <div>
                                <h4>Telepon</h4>
                                <p>+62 812 3456 7890</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <div class="icon">📍</div>
                            <div>
                                <h4>Lokasi</h4>
                                <p>Jakarta, Indonesia</p>
                            </div>
                        </div>
                    </div>
                    <div class="social-links">
                        <a href="#" title="LinkedIn">in</a>
                        <a href="#" title="GitHub">GH</a>
                        <a href="#" title="Twitter">𝕏</a>
                        <a href="#" title="Instagram">IG</a>
                    </div>
                </div>
                <form class="contact-form" onsubmit="handleSubmit(event)">
                    <input type="text" placeholder="Nama Anda" required>
                    <input type="email" placeholder="Email Anda" required>
                    <input type="text" placeholder="Subjek">
                    <textarea placeholder="Pesan Anda..." required></textarea>
                    <button type="submit" class="btn-submit">Kirim Pesan 🚀</button>
                </form>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <p>© 2026 Muhamad Rivaldo. Dibuat dengan ❤️ di Jakarta, Indonesia.</p>
    </footer>

    <!-- SCROLL TO TOP -->
    <button class="scroll-top" id="scrollTop" onclick="scrollToTop()">↑</button>

    <script>
        // ===== MOBILE MENU =====
        function toggleMenu() {
            document.getElementById('navLinks').classList.toggle('open');
        }

        // Close menu on link click
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                document.getElementById('navLinks').classList.remove('open');
            });
        });

        // ===== ACTIVE NAV LINK ON SCROLL =====
        const sections = document.querySelectorAll('section');
        const navLinks = document.querySelectorAll('.nav-links a');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop - 100;
                if (pageYOffset >= sectionTop) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === '#' + current) {
                    link.classList.add('active');
                }
            });

            // Scroll to top button
            const scrollBtn = document.getElementById('scrollTop');
            if (window.scrollY > 500) {
                scrollBtn.classList.add('show');
            } else {
                scrollBtn.classList.remove('show');
            }
        });

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // ===== SCROLL ANIMATIONS =====
        const fadeElements = document.querySelectorAll('.fade-in');
        const skillBars = document.querySelectorAll('.skill-bar .fill');

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');

                    // Animate skill bars
                    if (entry.target.querySelector('.skill-bar .fill')) {
                        entry.target.querySelectorAll('.skill-bar .fill').forEach(bar => {
                            bar.style.width = bar.dataset.width + '%';
                        });
                    }
                }
            });
        }, { threshold: 0.15 });

        fadeElements.forEach(el => observer.observe(el));

        // ===== COUNTER ANIMATION =====
        const counters = document.querySelectorAll('.stat .number');
        const counterObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const target = +entry.target.dataset.target;
                    let count = 0;
                    const increment = target / 50;
                    const timer = setInterval(() => {
                        count += increment;
                        if (count >= target) {
                            entry.target.textContent = target + '+';
                            clearInterval(timer);
                        } else {
                            entry.target.textContent = Math.ceil(count) + '+';
                        }
                    }, 30);
                    counterObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });

        counters.forEach(counter => counterObserver.observe(counter));

        // ===== FORM SUBMIT =====
        function handleSubmit(e) {
            e.preventDefault();
            alert('Terima kasih! Pesan Anda telah terkirim. 🎉');
            e.target.reset();
        }

        // ===== NAVBAR SHADOW ON SCROLL =====
        window.addEventListener('scroll', () => {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.style.boxShadow = '0 2px 20px rgba(0,0,0,0.1)';
            } else {
                navbar.style.boxShadow = '0 1px 10px rgba(0,0,0,0.06)';
            }
        });
    </script>

</body>
</html>
