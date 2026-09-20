<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Portofolio Profesional Mohammad Ryan Saputra - Sarjana Teknik Konstruksi Perkapalan. Spesialisasi dalam desain struktur, stabilitas kapal, dan manajemen proyek galangan.">
    <meta name="keywords" content="Teknik Perkapalan, Naval Architect, Mohammad Ryan Saputra, Gresik, Shipbuilding, Marine Engineer">
    <meta name="author" content="Mohammad Ryan Saputra">
    
    <title>Mohammad Ryan Saputra | Teknik Konstruksi Perkapalan</title>
    
    <!-- Font Modern: Orbitron (Industrial/Tech) & Inter (Clean/Readable) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Orbitron:wght@400;600;700&display=swap" rel="stylesheet">
    
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        :root {
            --primary-color: #0b1120; /* Deep Navy */
            --secondary-color: #1e293b; /* Steel Blue/Grey */
            --accent-color: #f59e0b; /* Safety Orange */
            --accent-glow: rgba(245, 158, 11, 0.4);
            --text-light: #f8fafc;
            --text-dim: #94a3b8;
            --glass-bg: rgba(30, 41, 59, 0.6);
            --glass-border: rgba(255, 255, 255, 0.08);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--primary-color);
            color: var(--text-light);
            overflow-x: hidden;
            line-height: 1.7;
        }

        /* --- Canvas Animation Background --- */
        #canvas-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at 50% 0%, #1e293b 0%, #0b1120 70%);
        }

        /* --- Typography & Utilities --- */
        h1, h2, h3 {
            font-family: 'Orbitron', sans-serif;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        .section-title {
            font-size: 2rem;
            text-align: center;
            margin-bottom: 3.5rem;
            color: var(--text-light);
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--accent-color), transparent);
            margin: 12px auto 0;
            border-radius: 2px;
        }

        .gradient-text {
            background: linear-gradient(135deg, #fff 0%, var(--accent-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* --- Navigation --- */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(11, 17, 32, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            z-index: 1000;
            border-bottom: 1px solid var(--glass-border);
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            font-size: 1.3rem;
            color: var(--accent-color);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--text-dim);
            text-decoration: none;
            font-weight: 500;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-color);
            transition: width 0.3s ease;
        }

        .nav-links a:hover, .nav-links a.active {
            color: var(--text-light);
        }

        .nav-links a:hover::after, .nav-links a.active::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text-light);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* --- Hero Section --- */
        header {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding-top: 80px;
            position: relative;
        }

        .hero-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            animation: fadeInUp 1s ease-out;
        }

        .profile-wrapper {
            position: relative;
            width: 220px;
            height: 220px;
            margin-bottom: 2rem;
        }

        .profile-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            border: 3px solid var(--accent-color);
            box-shadow: 0 0 40px var(--accent-glow);
            position: relative;
            z-index: 2;
            background-color: var(--secondary-color);
        }

        .tech-ring {
            position: absolute;
            top: -15px;
            left: -15px;
            right: -15px;
            bottom: -15px;
            border: 2px dashed rgba(245, 158, 11, 0.3);
            border-radius: 50%;
            animation: spin 25s linear infinite;
            z-index: 1;
        }

        .tech-ring::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 140%;
            height: 140%;
            border: 1px solid rgba(56, 189, 248, 0.1);
            border-radius: 50%;
            animation: spin-reverse 35s linear infinite;
        }

        .hero-name {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            line-height: 1.2;
        }

        .hero-degree {
            font-size: 1.25rem;
            color: var(--accent-color);
            margin-bottom: 1rem;
            font-weight: 500;
            letter-spacing: 1px;
        }

        .hero-location {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--text-dim);
            font-size: 1rem;
            margin-bottom: 2.5rem;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            justify-content: center;
        }

        .btn {
            padding: 14px 32px;
            text-decoration: none;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            clip-path: polygon(8% 0, 100% 0, 100% 75%, 92% 100%, 0 100%, 0 25%);
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: var(--accent-color);
            color: var(--primary-color);
            border: 2px solid var(--accent-color);
        }

        .btn-primary:hover {
            background: transparent;
            color: var(--accent-color);
            box-shadow: 0 0 25px var(--accent-glow);
        }

        .btn-secondary {
            background: transparent;
            color: var(--text-light);
            border: 2px solid rgba(255,255,255,0.2);
        }

        .btn-secondary:hover {
            border-color: var(--text-light);
            background: rgba(255,255,255,0.05);
        }

        /* --- Sections General --- */
        section {
            padding: 6rem 0;
        }

        /* --- Glass Cards --- */
        .glass-card {
            background: var(--glass-bg);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            padding: 2rem;
            border: 1px solid var(--glass-border);
            border-left: 3px solid var(--accent-color);
            border-radius: 8px;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .glass-card:hover {
            transform: translateY(-8px);
            background: rgba(30, 41, 59, 0.8);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            border-left-width: 5px;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
        }

        .card-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .card-icon {
            width: 50px;
            height: 50px;
            background: rgba(245, 158, 11, 0.1);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent-color);
            font-size: 1.3rem;
        }

        .info-list {
            list-style: none;
        }

        .info-list li {
            margin-bottom: 1rem;
            display: flex;
            align-items: flex-start;
            gap: 12px;
            color: var(--text-dim);
            font-size: 0.95rem;
        }

        .info-list i {
            margin-top: 4px;
            color: var(--accent-color);
            min-width: 20px;
        }

        /* --- Experience Timeline --- */
        .experience-timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
            padding-left: 30px;
        }

        .experience-timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 10px;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, var(--accent-color), transparent);
        }

        .timeline-item {
            position: relative;
            background: var(--glass-bg);
            padding: 2rem;
            margin-bottom: 2rem;
            border-radius: 8px;
            border: 1px solid var(--glass-border);
            transition: transform 0.3s ease;
        }

        .timeline-item:hover {
            transform: translateX(10px);
            border-color: rgba(245, 158, 11, 0.3);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -36px;
            top: 2rem;
            width: 14px;
            height: 14px;
            background: var(--primary-color);
            border: 3px solid var(--accent-color);
            border-radius: 50%;
            box-shadow: 0 0 10px var(--accent-glow);
        }

        .job-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .job-title {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--text-light);
            font-family: 'Orbitron', sans-serif;
        }

        .job-company {
            font-size: 0.95rem;
            color: var(--accent-color);
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .job-desc {
            color: var(--text-dim);
            font-size: 0.95rem;
        }
        
        .job-desc ul {
            list-style: none;
            margin-top: 12px;
        }

        .job-desc ul li {
            position: relative;
            padding-left: 20px;
            margin-bottom: 8px;
        }

        .job-desc ul li::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: var(--accent-color);
        }

        /* --- Skills --- */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            max-width: 900px;
            margin: 0 auto;
        }

        .skill-tag {
            background: rgba(255,255,255,0.03);
            padding: 0.8rem 1.5rem;
            border-radius: 6px;
            border: 1px solid rgba(255,255,255,0.1);
            font-family: 'Inter', sans-serif;
            font-weight: 500;
            font-size: 0.9rem;
            color: var(--text-dim);
            transition: all 0.3s ease;
            cursor: default;
        }

        .skill-tag:hover {
            background: rgba(245, 158, 11, 0.1);
            border-color: var(--accent-color);
            color: var(--accent-color);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(245, 158, 11, 0.15);
        }

        /* --- Contact --- */
        .contact-box {
            text-align: center;
            background: linear-gradient(145deg, rgba(30, 41, 59, 0.8), rgba(11, 17, 32, 0.9));
            padding: 4rem 2rem;
            border-radius: 16px;
            border: 1px solid var(--glass-border);
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
        }

        .contact-box::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--accent-color), transparent);
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--text-light);
            text-decoration: none;
            font-size: 1rem;
            font-weight: 500;
            padding: 14px 28px;
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 8px;
            transition: all 0.3s ease;
            background: rgba(255,255,255,0.02);
        }

        .contact-link:hover {
            background: rgba(255,255,255,0.08);
            border-color: var(--accent-color);
            color: var(--accent-color);
            transform: translateY(-4px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 2.5rem;
            background: #070b14;
            color: var(--text-dim);
            font-size: 0.9rem;
            border-top: 1px solid var(--glass-border);
        }

        /* --- Animations --- */
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes spin-reverse {
            0% { transform: translate(-50%, -50%) rotate(360deg); }
            100% { transform: translate(-50%, -50%) rotate(0deg); }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in-section {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
            will-change: opacity, visibility;
        }

        .fade-in-section.is-visible {
            opacity: 1;
            transform: none;
        }

        /* --- Responsiveness --- */
        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }

            .nav-links {
                position: fixed;
                top: 70px;
                right: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background: rgba(11, 17, 32, 0.98);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                gap: 2.5rem;
                transition: right 0.4s ease;
                border-top: 1px solid var(--glass-border);
            }

            .nav-links.active {
                right: 0;
            }

            .nav-links a {
                font-size: 1.2rem;
            }

            .hero-name {
                font-size: 2.2rem;
            }
            
            .hero-degree {
                font-size: 1.1rem;
            }

            .profile-wrapper {
                width: 180px;
                height: 180px;
            }

            .experience-timeline {
                padding-left: 20px;
            }

            .timeline-item::before {
                left: -26px;
                width: 12px;
                height: 12px;
            }

            .job-header {
                flex-direction: column;
                gap: 0.5rem;
            }
            
            .contact-links {
                flex-direction: column;
                align-items: center;
                gap: 1rem;
            }
            
            .contact-link {
                width: 100%;
                max-width: 320px;
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <!-- Canvas untuk Efek Partikel Industrial -->
    <div id="canvas-container">
        <canvas id="fallingBars"></canvas>
    </div>

    <!-- Navigasi -->
    <nav id="navbar">
        <div class="container nav-content">
            <a href="#home" class="logo">
                <i class="fas fa-anchor"></i> M.R.SAPUTRA
            </a>
            <button class="mobile-menu-btn" aria-label="Toggle Menu" onclick="toggleMenu()">
                <i class="fas fa-bars"></i>
            </button>
            <div class="nav-links" id="navLinks">
                <a href="#home" onclick="closeMenu()">Beranda</a>
                <a href="#about" onclick="closeMenu()">Tentang</a>
                <a href="#skills" onclick="closeMenu()">Keahlian</a>
                <a href="#experience" onclick="closeMenu()">Pengalaman</a>
                <a href="#contact" onclick="closeMenu()">Kontak</a>
            </div>
        </div>
    </nav>

    <!-- Header / Hero Section -->
    <header id="home">
        <div class="container hero-content">
            <div class="profile-wrapper">
                <!-- Ganti URL ini dengan foto profil asli Anda jika link sebelumnya kedaluwarsa -->
                <img src="https://z-cdn-media.chatglm.cn/files/bdd7cca4-135d-4d96-a52a-d54d0ad25207.jpeg?auth_key=1870118750-42e82049a15945aeb68a20f9b39cd0d9-0-6d56ac3351c5189365b2be42375746e6" 
                     alt="Mohammad Ryan Saputra" class="profile-img" onerror="this.src='https://via.placeholder.com/250x250/1e293b/f59e0b?text=MRS'">
                <div class="tech-ring"></div>
            </div>
            
            <h1 class="hero-name">Mohammad Ryan <span class="gradient-text">Saputra</span></h1>
            <p class="hero-degree">S1 Teknik Konstruksi Perkapalan</p>
            
            <div class="hero-location">
                <i class="fas fa-map-marker-alt"></i>
                <span>Desa Jetis, Petyintunggal, Gresik, Jawa Timur</span>
            </div>
            
            <div class="hero-buttons">
                <a href="#contact" class="btn btn-primary">
                    <i class="fas fa-paper-plane"></i> Hubungi Saya
                </a>
                <a href="#" class="btn btn-secondary" onclick="alert('Fitur Unduh CV akan segera tersedia!')">
                    <i class="fas fa-download"></i> Unduh CV
                </a>
            </div>
        </div>
    </header>

    <!-- Tentang Saya -->
    <section id="about" class="fade-in-section">
        <div class="container">
            <h2 class="section-title">Profil Profesional</h2>
            <div class="about-grid">
                <div class="glass-card">
                    <div class="card-header">
                        <div class="card-icon"><i class="fas fa-user-graduate"></i></div>
                        <h3>Pendidikan</h3>
                    </div>
                    <ul class="info-list">
                        <li>
                            <i class="fas fa-university"></i>
                            <div>
                                <strong style="color: var(--text-light);">Sarjana Teknik (S1)</strong><br>
                                Teknik Konstruksi Perkapalan<br>
                                <span style="font-size:0.85rem; margin-top: 4px; display: block;">Fokus pada desain struktur, stabilitas kapal, dan manajemen proyek galangan.</span>
                            </div>
                        </li>
                    </ul>
                </div>
                
                <div class="glass-card">
                    <div class="card-header">
                        <div class="card-icon"><i class="fas fa-id-card"></i></div>
                        <h3>Informasi Dasar</h3>
                    </div>
                    <ul class="info-list">
                        <li><i class="fas fa-user"></i> <span><strong style="color: var(--text-light);">Nama:</strong> Mohammad Ryan Saputra</span></li>
                        <li><i class="fas fa-home"></i> <span><strong style="color: var(--text-light);">Domisili:</strong> Gresik, Jawa Timur</span></li>
                        <li><i class="fas fa-map-pin"></i> <span><strong style="color: var(--text-light);">Desa:</strong> Jetis, Petyintunggal</span></li>
                        <li><i class="fas fa-briefcase"></i> <span><strong style="color: var(--text-light);">Status:</strong> Siap Bekerja / Full-time</span></li>
                    </ul>
                </div>

                <div class="glass-card">
                    <div class="card-header">
                        <div class="card-icon"><i class="fas fa-bullseye"></i></div>
                        <h3>Objektif Karir</h3>
                    </div>
                    <p style="color: var(--text-dim); font-size: 0.95rem; line-height: 1.8;">
                        Berkontribusi dalam industri maritim dan konstruksi kapal dengan mengaplikasikan pengetahuan teknis tentang struktur kapal, perencanaan, dan manajemen proyek untuk menciptakan solusi maritim yang efisien, aman, dan berkualitas tinggi sesuai standar klasifikasi internasional.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Keahlian Teknis -->
    <section id="skills" class="fade-in-section">
        <div class="container">
            <h2 class="section-title">Keahlian Teknis</h2>
            <div class="skills-container">
                <span class="skill-tag"><i class="fas fa-ship" style="margin-right: 8px;"></i> Naval Architecture</span>
                <span class="skill-tag">Ship Structural Design</span>
                <span class="skill-tag"><i class="fas fa-drafting-compass" style="margin-right: 8px;"></i> AutoCAD 2D/3D</span>
                <span class="skill-tag">Maxsurf Stability</span>
                <span class="skill-tag">ANSYS (FEA)</span>
                <span class="skill-tag">Manajemen Proyek Galangan</span>
                <span class="skill-tag">Perhitungan Stabilitas Kapal</span>
                <span class="skill-tag">Material Baja Konstruksi</span>
                <span class="skill-tag"><i class="fas fa-hard-hat" style="margin-right: 8px;"></i> K3 Perkapalan</span>
                <span class="skill-tag">Welding Inspection (NDT)</span>
            </div>
        </div>
    </section>

    <!-- Detail Pekerjaan -->
    <section id="experience" class="fade-in-section">
        <div class="container">
            <h2 class="section-title">Pengalaman & Proyek</h2>
            <div class="experience-timeline">
                
                <div class="timeline-item">
                    <div class="job-header">
                        <div class="job-title">Junior Naval Architect / Engineer</div>
                        <div class="job-company"><i class="fas fa-building"></i> Shipyard & Marine Industry (Gresik)</div>
                    </div>
                    <div class="job-desc">
                        <p>Bertanggung jawab atas perencanaan awal dan pengawasan konstruksi lambung kapal.</p>
                        <ul>
                            <li>Melakukan perhitungan stabilitas dan garis air kapal menggunakan perangkat lunak spesialis (Maxsurf).</li>
                            <li>Membuat gambar teknis detail (detail drawing) untuk konstruksi lambung dan superstruktur sesuai standar BKI.</li>
                            <li>Supervisi lapangan (scheduling blok, welding inspection) untuk memastikan kualitas hasil las dan struktur.</li>
                            <li>Berkolaborasi dengan tim produksi untuk menyelesaikan masalah teknis selama proses fabrikasi.</li>
                        </ul>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="job-header">
                        <div class="job-title">Site Supervisor / QC Officer</div>
                        <div class="job-company"><i class="fas fa-tools"></i> Proyek Perbaikan & Maintenance Kapal</div>
                    </div>
                    <div class="job-desc">
                        <p>Fokus pada pengawasan kualitas dan keselamatan kerja di lingkungan galangan kapal yang dinamis.</p>
                        <ul>
                            <li>Memeriksa kualitas material plat baja dan profil yang digunakan untuk konstruksi sesuai spesifikasi.</li>
                            <li>Memastikan prosedur K3 diterapkan ketat, terutama pada pekerjaan ketinggian dan confined space.</li>
                            <li>Menyusun laporan progres harian pekerjaan docking dan perbaikan kapal untuk Project Manager.</li>
                        </ul>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="job-header">
                        <div class="job-title">Draftsperson (Engineering Cadet)</div>
                        <div class="job-company"><i class="fas fa-pencil-ruler"></i> Engineering Consultant</div>
                    </div>
                    <div class="job-desc">
                        <p>Mendukung tim insinyur senior dalam dokumentasi teknis dan perencanaan awal.</p>
                        <ul>
                            <li>Mengkonversi sketsa teknis menjadi gambar digital 2D dan 3D yang presisi menggunakan AutoCAD.</li>
                            <li>Menyusun Bill of Materials (BOM) untuk akurasi kebutuhan material proyek.</li>
                        </ul>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Kontak -->
    <section id="contact" class="fade-in-section">
        <div class="container">
            <div class="contact-box">
                <h2 style="margin-bottom: 1rem; font-size: 2rem;">Siap Berkolaborasi</h2>
                <p style="color: var(--text-dim); margin-bottom: 2rem; max-width: 600px; margin-left: auto; margin-right: auto;">
                    Tertarik untuk bekerja sama dalam proyek konstruksi kapal, survei, atau engineering lainnya? Jangan ragu untuk menghubungi saya melalui saluran di bawah ini.
                </p>
                
                <!-- KONTAK YANG SUDAH DIUPDATE -->
                <div class="contact-links">
                    <a href="https://wa.me/6285707517675" target="_blank" class="contact-link">
                        <i class="fab fa-whatsapp" style="color: #25D366; font-size: 1.2rem;"></i> 
                        <span>0857-0751-7675</span>
                    </a>
                    
                    <a href="https://www.linkedin.com/in/ryan-saputra-426935370/" target="_blank" class="contact-link">
                        <i class="fab fa-linkedin" style="color: #0A66C2; font-size: 1.2rem;"></i> 
                        <span>LinkedIn Profil</span>
                    </a>
                    
                    <a href="mailto:ryansaputra03182002@gmail.com" class="contact-link">
                        <i class="fas fa-envelope" style="color: var(--accent-color); font-size: 1.2rem;"></i> 
                        <span>ryansaputra03182002@gmail.com</span>
                    </a>
                </div>
                <!-- AKHIR DARI KONTAK YANG DIUPDATE -->

            </div>
        </div>
    </section>

    <footer>
        <p>&copy; <span id="current-year"></span> Mohammad Ryan Saputra. Teknik Konstruksi Perkapalan. All Rights Reserved.</p>
    </footer>

    <!-- Script Javascript -->
    <script>
        // --- 1. Dynamic Year ---
        document.getElementById('current-year').textContent = new Date().getFullYear();

        // --- 2. Mobile Menu Toggle ---
        function toggleMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
        }

        function closeMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.remove('active');
        }

        // --- 3. Scroll Spy (Active Navigation) ---
        const sections = document.querySelectorAll('section, header');
        const navLinks = document.querySelectorAll('.nav-links a');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (pageYOffset >= (sectionTop - 150)) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').includes(current)) {
                    link.classList.add('active');
                }
            });
            
            // Navbar background on scroll
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.style.background = 'rgba(11, 17, 32, 0.95)';
                navbar.style.boxShadow = '0 4px 20px rgba(0,0,0,0.3)';
            } else {
                navbar.style.background = 'rgba(11, 17, 32, 0.85)';
                navbar.style.boxShadow = 'none';
            }
        });

        // --- 4. Intersection Observer for Fade-in Animations ---
        const observerOptions = {
            threshold: 0.15,
            rootMargin: "0px 0px -50px 0px"
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible');
                    observer.unobserve(entry.target); // Hanya animasi sekali
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in-section').forEach(el => {
            observer.observe(el);
        });

        // --- 5. Optimized Canvas Animation (Glowing Industrial Bars/Sparks) ---
        const canvas = document.getElementById('fallingBars');
        const ctx = canvas.getContext('2d');

        let width, height;
        let bars = [];
        let animationId;

        function resize() {
            width = window.innerWidth;
            height = window.innerHeight;
            const dpr = window.devicePixelRatio || 1;
            canvas.width = width * dpr;
            canvas.height = height * dpr;
            ctx.scale(dpr, dpr);
            canvas.style.width = `${width}px`;
            canvas.style.height = `${height}px`;
        }

        window.addEventListener('resize', () => {
            resize();
            initBars();
        });
        resize();

        class Bar {
            constructor() {
                this.init();
            }

            init() {
                this.x = Math.random() * width;
                this.y = Math.random() * -height;
                this.speed = 1.5 + Math.random() * 3;
                this.length = 15 + Math.random() * 80;
                this.width = 1.5 + Math.random() * 3;
                this.opacity = 0.1 + Math.random() * 0.3;
                
                const colors = ['255, 255, 255', '56, 189, 248', '245, 158, 11'];
                this.color = colors[Math.floor(Math.random() * colors.length)];
            }

            update() {
                this.y += this.speed;
                if (this.y > height) {
                    this.init();
                    this.y = -this.length;
                }
            }

            draw() {
                ctx.beginPath();
                ctx.fillStyle = `rgba(${this.color}, ${this.opacity})`;
                ctx.shadowBlur = 8;
                ctx.shadowColor = `rgba(${this.color}, 0.6)`;
                ctx.fillRect(this.x, this.y, this.width, this.length);
                ctx.shadowBlur = 0;
                ctx.closePath();
            }
        }

        function initBars() {
            bars = [];
            const numberOfBars = Math.floor(width / 15); 
            for (let i = 0; i < numberOfBars; i++) {
                bars.push(new Bar());
            }
        }

        initBars();

        function animate() {
            ctx.clearRect(0, 0, width, height);
            bars.forEach(bar => {
                bar.update();
                bar.draw();
            });
            animationId = requestAnimationFrame(animate);
        }

        animate();

        document.addEventListener('visibilitychange', () => {
            if (document.hidden) {
                cancelAnimationFrame(animationId);
            } else {
                animate();
            }
        });
    </script>
</body>
</html>
