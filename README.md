<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>NovaMed - Modern Medical Clinic</title>
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet" />
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: #f7f9fc;
            color: #1a2332;
            line-height: 1.7;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
            cursor: pointer;
        }

        .container {
            max-width: 1240px;
            margin: 0 auto;
            padding: 0 28px;
        }

        /* Buttons */
        .btn-primary {
            background: linear-gradient(135deg, #0d9488, #0f766e);
            color: #fff;
            padding: 14px 38px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 15px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 28px rgba(13, 148, 136, 0.30);
            display: inline-block;
            letter-spacing: 0.3px;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 14px 36px rgba(13, 148, 136, 0.40);
        }

        .btn-outline {
            background: transparent;
            color: #1a2332;
            padding: 12px 34px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 15px;
            border: 2px solid #dce3ed;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-block;
        }

        .btn-outline:hover {
            border-color: #0d9488;
            color: #0d9488;
            transform: translateY(-2px);
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            padding: 18px 0;
            transition: all 0.3s ease;
            background: rgba(255, 255, 255, 0.72);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border-bottom: 1px solid rgba(0, 0, 0, 0.04);
        }

        header.scrolled {
            background: rgba(255, 255, 255, 0.92);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.06);
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 28px;
            font-weight: 800;
            letter-spacing: -0.5px;
            background: linear-gradient(135deg, #0d9488, #0f766e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .logo i {
            -webkit-text-fill-color: #0d9488;
            margin-right: 6px;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 34px;
            list-style: none;
        }

        .nav-links a {
            font-weight: 500;
            font-size: 15px;
            color: #1a2332;
            transition: 0.25s ease;
            position: relative;
            cursor: pointer;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2.5px;
            background: #0d9488;
            border-radius: 4px;
            transition: 0.3s ease;
        }

        .nav-links a:hover {
            color: #0d9488;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-cta {
            background: linear-gradient(135deg, #0d9488, #0f766e);
            color: #fff !important;
            padding: 10px 28px;
            border-radius: 50px;
            font-weight: 600;
            transition: 0.3s ease;
            box-shadow: 0 6px 20px rgba(13, 148, 136, 0.25);
        }

        .nav-cta::after {
            display: none !important;
        }

        .nav-cta:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 28px rgba(13, 148, 136, 0.35);
            color: #fff !important;
        }

        .hamburger {
            display: none;
            font-size: 26px;
            cursor: pointer;
            color: #1a2332;
            background: none;
            border: none;
        }

        /* Hero */
        .hero {
            padding: 140px 0 80px;
            display: flex;
            align-items: center;
            gap: 50px;
            min-height: 100vh;
        }

        .hero-content {
            flex: 1.1;
        }

        .hero-badge {
            display: inline-block;
            background: #e0f2f1;
            color: #0d9488;
            font-weight: 600;
            font-size: 13px;
            padding: 6px 20px;
            border-radius: 50px;
            letter-spacing: 0.5px;
            margin-bottom: 24px;
        }

        .hero-content h1 {
            font-size: 56px;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 20px;
            letter-spacing: -1px;
        }

        .hero-content h1 span {
            background: linear-gradient(135deg, #0d9488, #0f766e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-content p {
            font-size: 18px;
            color: #4a5a6e;
            max-width: 500px;
            margin-bottom: 34px;
        }

        .hero-buttons {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
        }

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .hero-image img {
            max-width: 100%;
            border-radius: 32px;
            box-shadow: 0 40px 80px rgba(0, 0, 0, 0.06);
        }

        .hero-stats {
            display: flex;
            gap: 48px;
            margin-top: 48px;
            padding-top: 32px;
            border-top: 1px solid #e8edf4;
        }

        .hero-stats .stat h3 {
            font-size: 32px;
            font-weight: 800;
            color: #0d9488;
        }

        .hero-stats .stat p {
            font-size: 14px;
            color: #5a6a7e;
            margin: 0;
        }

        /* Section Titles */
        .section-title {
            text-align: center;
            max-width: 600px;
            margin: 0 auto 60px;
        }

        .section-title h2 {
            font-size: 42px;
            font-weight: 800;
            letter-spacing: -0.5px;
        }

        .section-title h2 span {
            background: linear-gradient(135deg, #0d9488, #0f766e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .section-title p {
            color: #5a6a7e;
            font-size: 17px;
            margin-top: 8px;
        }

        /* Services */
        .services {
            padding: 90px 0;
            background: #fff;
            scroll-margin-top: 80px;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
            gap: 30px;
        }

        .service-card {
            padding: 36px 28px;
            border-radius: 24px;
            background: #f7f9fc;
            transition: 0.35s ease;
            border: 1px solid transparent;
            text-align: center;
        }

        .service-card:hover {
            background: #fff;
            border-color: #e0edec;
            transform: translateY(-8px);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.04);
        }

        .service-card .icon {
            width: 68px;
            height: 68px;
            background: linear-gradient(135deg, #e0f2f1, #ccf0ee);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 18px;
            font-size: 30px;
            color: #0d9488;
        }

        .service-card h4 {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 8px;
        }

        .service-card p {
            color: #5a6a7e;
            font-size: 15px;
        }

        /* Doctors */
        .doctors {
            padding: 90px 0;
            background: #f7f9fc;
            scroll-margin-top: 80px;
        }

        .doctors-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 34px;
        }

        .doctor-card {
            background: #fff;
            border-radius: 28px;
            padding: 28px 20px 32px;
            text-align: center;
            transition: 0.3s ease;
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.02);
        }

        .doctor-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 20px 48px rgba(0, 0, 0, 0.05);
        }

        .doctor-card img {
            width: 130px;
            height: 130px;
            border-radius: 50%;
            object-fit: cover;
            background: #d4e8e6;
            margin-bottom: 16px;
        }

        .doctor-card h4 {
            font-size: 19px;
            font-weight: 700;
        }

        .doctor-card .specialty {
            color: #0d9488;
            font-weight: 500;
            font-size: 14px;
        }

        .doctor-card .social-icons {
            margin-top: 14px;
            display: flex;
            justify-content: center;
            gap: 18px;
            color: #6a7a8e;
            font-size: 18px;
        }

        .doctor-card .social-icons i {
            transition: 0.2s;
            cursor: pointer;
        }

        .doctor-card .social-icons i:hover {
            color: #0d9488;
        }

        /* Testimonials */
        .testimonials {
            padding: 90px 0;
            background: #fff;
            scroll-margin-top: 80px;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background: #f7f9fc;
            padding: 30px 28px;
            border-radius: 24px;
            transition: 0.3s;
        }

        .testimonial-card:hover {
            background: #fff;
            box-shadow: 0 12px 36px rgba(0, 0, 0, 0.03);
        }

        .testimonial-card .stars {
            color: #f59e0b;
            margin-bottom: 10px;
            font-size: 16px;
        }

        .testimonial-card p {
            font-size: 16px;
            color: #2a3a4a;
        }

        .testimonial-card .author {
            margin-top: 16px;
            font-weight: 700;
        }

        .testimonial-card .author span {
            font-weight: 400;
            color: #6a7a8e;
            font-size: 14px;
        }

        /* Appointment */
        .appointment {
            padding: 90px 0;
            background: linear-gradient(135deg, #e8f5f4, #d4edeb);
            scroll-margin-top: 80px;
        }

        .appointment-wrapper {
            display: flex;
            gap: 50px;
            align-items: center;
        }

        .appointment-info {
            flex: 1;
        }

        .appointment-info h2 {
            font-size: 38px;
            font-weight: 800;
            line-height: 1.2;
        }

        .appointment-info h2 span {
            background: linear-gradient(135deg, #0d9488, #0f766e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .appointment-info p {
            color: #3a4a5e;
            margin: 16px 0 28px;
            font-size: 17px;
        }

        .appointment-form {
            flex: 1;
            background: #fff;
            padding: 40px 42px;
            border-radius: 32px;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.06);
        }

        .appointment-form h4 {
            font-size: 22px;
            margin-bottom: 6px;
        }

        .appointment-form .sub {
            color: #5a6a7e;
            margin-bottom: 24px;
            font-size: 14px;
        }

        .form-group {
            margin-bottom: 18px;
        }

        .form-group label {
            font-weight: 600;
            font-size: 13px;
            display: block;
            margin-bottom: 4px;
            color: #1a2332;
        }

        .form-group input,
        .form-group select {
            width: 100%;
            padding: 14px 18px;
            border-radius: 16px;
            border: 1.5px solid #e4ebf2;
            font-size: 15px;
            background: #fafbfc;
            transition: 0.25s;
            outline: none;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group select:focus {
            border-color: #0d9488;
            background: #fff;
            box-shadow: 0 0 0 4px rgba(13, 148, 136, 0.08);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
        }

        .btn-submit {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, #0d9488, #0f766e);
            color: #fff;
            border: none;
            border-radius: 50px;
            font-weight: 700;
            font-size: 17px;
            cursor: pointer;
            transition: 0.3s;
            margin-top: 6px;
            box-shadow: 0 10px 30px rgba(13, 148, 136, 0.25);
        }

        .btn-submit:hover {
            transform: translateY(-3px);
            box-shadow: 0 16px 40px rgba(13, 148, 136, 0.35);
        }

        /* Footer */
        footer {
            background: #0f1a24;
            color: #b0c4d4;
            padding: 60px 0 32px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-brand h3 {
            color: #fff;
            font-size: 24px;
            font-weight: 800;
        }

        .footer-brand h3 i {
            color: #0d9488;
            margin-right: 6px;
        }

        .footer-brand p {
            margin-top: 10px;
            max-width: 300px;
            font-size: 14px;
        }

        .footer-col h5 {
            color: #fff;
            font-size: 17px;
            margin-bottom: 18px;
        }

        .footer-col a {
            display: block;
            margin-bottom: 10px;
            font-size: 14px;
            transition: 0.2s;
            cursor: pointer;
        }

        .footer-col a:hover {
            color: #fff;
        }

        .footer-bottom {
            border-top: 1px solid #1e2e3a;
            padding-top: 28px;
            text-align: center;
            font-size: 14px;
        }

        /* Responsive */
        @media (max-width: 992px) {
            .hero {
                flex-direction: column;
                text-align: center;
                padding-top: 120px;
            }

            .hero-content p {
                margin-left: auto;
                margin-right: auto;
            }

            .hero-buttons {
                justify-content: center;
            }

            .hero-stats {
                justify-content: center;
            }

            .appointment-wrapper {
                flex-direction: column;
            }

            .footer-grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                gap: 16px;
                background: rgba(255, 255, 255, 0.96);
                backdrop-filter: blur(12px);
                padding: 30px 24px;
                border-radius: 24px;
                position: absolute;
                top: 74px;
                left: 20px;
                right: 20px;
                box-shadow: 0 20px 50px rgba(0, 0, 0, 0.08);
                border: 1px solid rgba(0, 0, 0, 0.03);
            }

            .nav-links.open {
                display: flex;
            }

            .hamburger {
                display: block;
            }

            .hero-content h1 {
                font-size: 38px;
            }

            .section-title h2 {
                font-size: 32px;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .appointment-form {
                padding: 28px 20px;
            }

            .footer-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }
        }

        @media (max-width: 480px) {
            .hero-content h1 {
                font-size: 30px;
            }

            .hero-stats {
                flex-wrap: wrap;
                gap: 24px;
            }

            .btn-primary,
            .btn-outline {
                width: 100%;
                text-align: center;
            }
        }
    </style>
</head>
<body>

    <!-- ===== HEADER ===== -->
    <header id="header">
        <div class="container navbar">
            <div class="logo">
                <i class="fas fa-heart-pulse"></i> NovaMed
            </div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home" onclick="closeMenu()">Home</a></li>
                <li><a href="#services" onclick="closeMenu()">Services</a></li>
                <li><a href="#doctors" onclick="closeMenu()">Doctors</a></li>
                <li><a href="#testimonials" onclick="closeMenu()">Testimonials</a></li>
                <li><a href="#appointment" class="nav-cta" onclick="closeMenu()">Book Now</a></li>
            </ul>
            <button class="hamburger" id="hamburger" aria-label="Toggle menu">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- ===== HERO ===== -->
    <section class="hero container" id="home">
        <div class="hero-content">
            <span class="hero-badge"><i class="fas fa-shield-alt"></i> &nbsp;Trusted Healthcare</span>
            <h1>
                Modern <br />
                <span>Medical Care</span> for You
            </h1>
            <p>
                Experience world-class medical services with cutting-edge technology
                and a team of dedicated specialists who prioritize your well-being.
            </p>
            <div class="hero-buttons">
                <a href="#appointment" class="btn-primary">Book Appointment</a>
                <a href="#services" class="btn-outline">Explore Services</a>
            </div>
            <div class="hero-stats">
                <div class="stat">
                    <h3>15+</h3>
                    <p>Years Experience</p>
                </div>
                <div class="stat">
                    <h3>24/7</h3>
                    <p>Emergency Support</p>
                </div>
                <div class="stat">
                    <h3>2K+</h3>
                    <p>Happy Patients</p>
                </div>
            </div>
        </div>
        <div class="hero-image">
            <img src="https://images.unsplash.com/photo-1576091160550-2173dba999ef?w=600&h=450&fit=crop&crop=center" alt="Medical team" />
        </div>
    </section>

    <!-- ===== SERVICES ===== -->
    <section class="services" id="services">
        <div class="container">
            <div class="section-title">
                <h2>Our <span>Services</span></h2>
                <p>Comprehensive medical services designed for your health and comfort.</p>
            </div>
            <div class="services-grid">
                <div class="service-card">
                    <div class="icon"><i class="fas fa-stethoscope"></i></div>
                    <h4>General Checkup</h4>
                    <p>Full health assessment with state-of-the-art diagnostic tools.</p>
                </div>
                <div class="service-card">
                    <div class="icon"><i class="fas fa-tooth"></i></div>
                    <h4>Dentistry</h4>
                    <p>Advanced dental care for a healthy and confident smile.</p>
                </div>
                <div class="service-card">
                    <div class="icon"><i class="fas fa-brain"></i></div>
                    <h4>Psychology</h4>
                    <p>Professional mental health support and therapy sessions.</p>
                </div>
                <div class="service-card">
                    <div class="icon"><i class="fas fa-baby"></i></div>
                    <h4>Pediatrics</h4>
                    <p>Specialized care for children from birth to adolescence.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== DOCTORS ===== -->
    <section class="doctors" id="doctors">
        <div class="container">
            <div class="section-title">
                <h2>Our <span>Specialists</span></h2>
                <p>Meet our experienced and compassionate medical team.</p>
            </div>
            <div class="doctors-grid">
                <div class="doctor-card">
                    <img src="https://images.unsplash.com/photo-1612349317150-e413f6a5b16d?w=200&h=200&fit=crop&crop=center" alt="Doctor" />
                    <h4>Dr. James Carter</h4>
                    <p class="specialty">Cardiologist</p>
                    <div class="social-icons">
                        <i class="fab fa-linkedin-in"></i>
                        <i class="fab fa-twitter"></i>
                        <i class="fab fa-instagram"></i>
                    </div>
                </div>
                <div class="doctor-card">
                    <img src="https://images.unsplash.com/photo-1559839734-2b71ea197ec2?w=200&h=200&fit=crop&crop=center" alt="Doctor" />
                    <h4>Dr. Emily Watson</h4>
                    <p class="specialty">Pediatrician</p>
                    <div class="social-icons">
                        <i class="fab fa-linkedin-in"></i>
                        <i class="fab fa-twitter"></i>
                        <i class="fab fa-instagram"></i>
                    </div>
                </div>
                <div class="doctor-card">
                    <img src="https://images.unsplash.com/photo-1622253692010-333f2da6031d?w=200&h=200&fit=crop&crop=center" alt="Doctor" />
                    <h4>Dr. Robert Chen</h4>
                    <p class="specialty">Orthopedic Surgeon</p>
                    <div class="social-icons">
                        <i class="fab fa-linkedin-in"></i>
                        <i class="fab fa-twitter"></i>
                        <i class="fab fa-instagram"></i>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== TESTIMONIALS ===== -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>Patient <span>Testimonials</span></h2>
                <p>Real stories from people who trusted us with their health.</p>
            </div>
            <div class="testimonials-grid">
                <div class="testimonial-card">
                    <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p>“The care I received was outstanding. The doctors truly listen and the facility is top-notch.”</p>
                    <div class="author">Sarah Mitchell <span>– Patient</span></div>
                </div>
                <div class="testimonial-card">
                    <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p>“Booking online was so easy, and I was seen right on time. Highly recommend NovaMed.”</p>
                    <div class="author">David Park <span>– Patient</span></div>
                </div>
                <div class="testimonial-card">
                    <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p>“The team made me feel safe and comfortable throughout my treatment. Truly exceptional.”</p>
                    <div class="author">Maria Gonzalez <span>– Patient</span></div>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== APPOINTMENT ===== -->
    <section class="appointment" id="appointment">
        <div class="container appointment-wrapper">
            <div class="appointment-info">
                <h2>Book Your <span>Appointment</span></h2>
                <p>Fill in the form and our team will get back to you within 24 hours.</p>
                <div style="display: flex; gap: 18px; flex-wrap: wrap; margin-top: 12px;">
                    <span style="display: flex; align-items: center; gap: 8px; background: rgba(255,255,255,0.6); padding: 8px 18px; border-radius: 50px; font-size: 14px;">
                        <i class="fas fa-phone" style="color: #0d9488;"></i> +1 (555) 123-4567
                    </span>
                    <span style="display: flex; align-items: center; gap: 8px; background: rgba(255,255,255,0.6); padding: 8px 18px; border-radius: 50px; font-size: 14px;">
                        <i class="fas fa-envelope" style="color: #0d9488;"></i> info@novamed.com
                    </span>
                </div>
            </div>
            <div class="appointment-form">
                <h4>Request a Visit</h4>
                <p class="sub">We'll confirm your appointment shortly.</p>
                <form id="appointmentForm">
                    <div class="form-row">
                        <div class="form-group">
                            <label>Full Name</label>
                            <input type="text" placeholder="Your full name" required />
                        </div>
                        <div class="form-group">
                            <label>Phone Number</label>
                            <input type="tel" placeholder="+1 (555) 000-0000" required />
                        </div>
                    </div>
                    <div class="form-group">
                        <label>Specialty</label>
                        <select>
                            <option>Cardiology</option>
                            <option>Pediatrics</option>
                            <option>Orthopedics</option>
                            <option>Psychology</option>
                            <option>Dentistry</option>
                            <option>General Checkup</option>
                        </select>
                    </div>
                    <button type="submit" class="btn-submit">Send Request</button>
                </form>
            </div>
        </div>
    </section>

    <!-- ===== FOOTER ===== -->
    <footer>
        <div class="container footer-grid">
            <div class="footer-brand">
                <h3><i class="fas fa-heart-pulse"></i> NovaMed</h3>
                <p>Delivering modern, compassionate healthcare with a focus on innovation and patient well-being.</p>
            </div>
            <div class="footer-col">
                <h5>Quick Links</h5>
                <a href="#home">Home</a>
                <a href="#services">Services</a>
                <a href="#doctors">Doctors</a>
                <a href="#testimonials">Testimonials</a>
            </div>
            <div class="footer-col">
                <h5>Support</h5>
                <a href="#">FAQ</a>
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Use</a>
                <a href="#">Contact</a>
            </div>
            <div class="footer-col">
                <h5>Connect</h5>
                <a href="#"><i class="fab fa-instagram"></i> Instagram</a>
                <a href="#"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
                <a href="#"><i class="fab fa-youtube"></i> YouTube</a>
                <a href="#"><i class="fab fa-twitter"></i> Twitter</a>
            </div>
        </div>
        <div class="container footer-bottom">
            &copy; 2025 NovaMed – All rights reserved.
        </div>
    </footer>

    <!-- ===== SCRIPTS ===== -->
    <script>
        // Close menu function
        function closeMenu() {
            const navLinks = document.getElementById('navLinks');
            const hamburger = document.getElementById('hamburger');
            navLinks.classList.remove('open');
            const icon = hamburger.querySelector('i');
            if (icon) {
                icon.className = 'fas fa-bars';
            }
        }

        // Hamburger Menu Toggle
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');

        hamburger.addEventListener('click', function() {
            navLinks.classList.toggle('open');
            const icon = this.querySelector('i');
            if (navLinks.classList.contains('open')) {
                icon.className = 'fas fa-times';
            } else {
                icon.className = 'fas fa-bars';
            }
        });

        // Header shadow on scroll
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 30) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Smooth form submission
        document.getElementById('appointmentForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('✅ Your appointment request has been sent!\nWe will contact you within 24 hours.');
            this.reset();
        });

        // Close menu when clicking outside (optional but nice)
        document.addEventListener('click', function(event) {
            const nav = document.getElementById('navLinks');
            const hamburger = document.getElementById('hamburger');
            if (!nav.contains(event.target) && !hamburger.contains(event.target)) {
                nav.classList.remove('open');
                const icon = hamburger.querySelector('i');
                if (icon) {
                    icon.className = 'fas fa-bars';
                }
            }
        });
    </script>

</body>
</html>
