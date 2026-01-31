<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>V. L MEDIA Group | Premium Digital Solutions</title>
    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            --primary: #0f172a; /* Dark Blue */
            --secondary: #1e293b; /* Lighter Dark */
            --accent: #3b82f6; /* Professional Blue */
            --gold: #fbbf24; /* Premium feel */
            --text: #f8fafc;
            --text-muted: #94a3b8;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        
        body { background-color: var(--primary); color: var(--text); line-height: 1.6; }
        
        a { text-decoration: none; color: inherit; transition: 0.3s; }
        ul { list-style: none; }

        /* --- HEADER --- */
        header {
            background: rgba(15, 23, 42, 0.95);
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid #334155;
            backdrop-filter: blur(10px);
        }

        .logo { font-size: 1.8rem; font-weight: bold; color: var(--text); letter-spacing: 1px; }
        .logo span { color: var(--accent); }

        nav ul { display: flex; gap: 30px; }
        nav a:hover { color: var(--accent); }

        .btn-quote {
            background: var(--accent);
            color: white;
            padding: 10px 25px;
            border-radius: 5px;
            font-weight: 600;
            border: none;
            cursor: pointer;
        }
        .btn-quote:hover { background: #2563eb; transform: translateY(-2px); }

        /* --- HERO SECTION --- */
        .hero {
            height: 80vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(15, 23, 42, 0.8), rgba(15, 23, 42, 0.8)), url('https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            padding: 0 20px;
        }

        .hero h1 { font-size: 3.5rem; margin-bottom: 20px; }
        .hero p { font-size: 1.2rem; color: var(--text-muted); max-width: 600px; margin-bottom: 30px; }

        /* --- SERVICES SECTION --- */
        .services { padding: 80px 10%; }
        .section-title { text-align: center; margin-bottom: 60px; font-size: 2.5rem; }
        
        .category-title { 
            color: var(--accent); 
            margin: 40px 0 20px; 
            font-size: 1.8rem; 
            border-bottom: 2px solid #334155; 
            padding-bottom: 10px; 
            display: inline-block;
        }

        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .card {
            background: var(--secondary);
            padding: 30px;
            border-radius: 10px;
            border: 1px solid #334155;
            transition: 0.3s;
        }
        .card:hover { border-color: var(--accent); transform: translateY(-5px); }
        .card h3 { margin-bottom: 15px; font-size: 1.4rem; }
        .price { color: var(--gold); font-size: 1.2rem; font-weight: bold; margin-bottom: 10px; display: block;}
        .desc { color: var(--text-muted); font-size: 0.9rem; }

        /* --- MODAL / POPUP FORM --- */
        .modal {
            display: none; 
            position: fixed; 
            z-index: 2000; 
            left: 0;
            top: 0;
            width: 100%; 
            height: 100%; 
            background-color: rgba(0,0,0,0.8);
            overflow: auto;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background-color: var(--secondary);
            margin: 5% auto;
            padding: 40px;
            border: 1px solid var(--accent);
            width: 90%;
            max-width: 600px;
            border-radius: 10px;
            position: relative;
            animation: fadeIn 0.4s;
        }

        @keyframes fadeIn {
            from {opacity: 0; transform: translateY(-20px);}
            to {opacity: 1; transform: translateY(0);}
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            position: absolute;
            right: 20px;
            top: 15px;
        }
        .close:hover { color: white; }

        .form-group { margin-bottom: 20px; }
        .form-group label { display: block; margin-bottom: 8px; color: var(--accent); font-weight: 500;}
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 12px;
            background: #0f172a;
            border: 1px solid #334155;
            color: white;
            border-radius: 5px;
        }
        .form-group input:focus, .form-group textarea:focus { outline: 2px solid var(--accent); }

        .btn-submit {
            width: 100%;
            padding: 15px;
            background: var(--accent);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
        }
        .btn-submit:hover { background: #2563eb; }

        /* Success Message Styling */
        #success-message {
            display: none;
            text-align: center;
            color: white;
        }
        #success-message h2 { color: var(--gold); margin-bottom: 15px; }
        #success-message p { margin-bottom: 10px; color: #cbd5e1; }
        .owner-email {
            color: var(--accent);
            font-weight: bold;
            margin-top: 10px;
            display: block;
        }

        /* --- FOOTER --- */
        footer {
            background: #020617;
            padding: 40px 10%;
            text-align: center;
            border-top: 1px solid #334155;
            margin-top: 50px;
        }
        footer p { color: var(--text-muted); }
        .footer-email { color: var(--accent); font-weight: bold; margin-top: 10px; display: inline-block; }

        /* Mobile Responsive */
        @media(max-width: 768px) {
            .hero h1 { font-size: 2.5rem; }
            nav { display: none; } /* Simplified for mobile demo */
            .modal-content { margin: 20% auto; width: 95%; }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">V. L <span>MEDIA</span> Group</div>
        <nav>
            <ul>
                <li><a href="#services">Services</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
        <button class="btn-quote" onclick="openModal()">Get Quotation</button>
    </header>

    <section class="hero">
        <h1>Transforming Ideas into Digital Reality</h1>
        <p>Premium Video Editing, Web Development, and Digital Strategy for Global Brands.</p>
        <button class="btn-quote" onclick="openModal()">Start Your Project</button>
    </section>

    <section id="services" class="services">
        <h2 class="section-title">Our Services & Pricing</h2>

        <h3 class="category-title">Video Editing</h3>
        <div class="pricing-grid">
            <div class="card">
                <h3>Instagram Reels / TikTok</h3>
                <span class="price">$70 / video</span>
                <p class="desc">High retention editing, captions, and effects.</p>
            </div>
            <div class="card">
                <h3>Long Form Content</h3>
                <span class="price">$50 / min</span>
                <p class="desc">YouTube videos, Documentaries, Corporate videos.</p>
            </div>
        </div>

        <h3 class="category-title">Graphic Design</h3>
        <div class="pricing-grid">
            <div class="card">
                <h3>Logo Design</h3>
                <span class="price">$300 – $2,500+</span>
                <p class="desc">Unique, memorable, and scalable vector logos.</p>
            </div>
            <div class="card">
                <h3>Brand Identity Package</h3>
                <span class="price">$1,000 – $10,000+</span>
                <p class="desc">Full visual system, typography, and brand guidelines.</p>
            </div>
            <div class="card">
                <h3>Brochure Design</h3>
                <span class="price">$300 – $1,600</span>
                <p class="desc">4-page to 8-page professional layout design.</p>
            </div>
            <div class="card">
                <h3>Packaging Design</h3>
                <span class="price">$500 – $1,000+</span>
                <p class="desc">Retail-ready packaging solutions.</p>
            </div>
        </div>

        <h3 class="category-title">Website Development</h3>
        <div class="pricing-grid">
            <div class="card">
                <h3>Landing Page</h3>
                <span class="price">$100 – $1,000</span>
                <p class="desc">High-converting single page sites.</p>
            </div>
            <div class="card">
                <h3>Small Business Website</h3>
                <span class="price">$2,000 – $10,000</span>
                <p class="desc">5-10 pages, SEO optimized, Mobile responsive.</p>
            </div>
            <div class="card">
                <h3>eCommerce Website</h3>
                <span class="price">$5,000 – $100,000+</span>
                <p class="desc">Online stores (Shopify/WooCommerce/Custom).</p>
            </div>
            <div class="card">
                <h3>Custom Web Application</h3>
                <span class="price">$20,000 – $150,000+</span>
                <p class="desc">SaaS platforms and complex functionality.</p>
            </div>
        </div>

        <h3 class="category-title">Social Media Management</h3>
        <div class="pricing-grid">
            <div class="card">
                <h3>Small / Short-Term</h3>
                <span class="price">$500 – $2,500</span>
                <p class="desc">Initial strategy, profile setup, or small ad campaign.</p>
            </div>
            <div class="card">
                <h3>Mid-Level Campaign</h3>
                <span class="price">$2,500 – $10,000</span>
                <p class="desc">Content creation, influencer management (3-month strategy).</p>
            </div>
            <div class="card">
                <h3>Large Scale Project</h3>
                <span class="price">$10,000 – $50,000+</span>
                <p class="desc">Full brand launches & multi-platform strategies.</p>
            </div>
        </div>
