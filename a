<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AzIoT.com - Custom Electronic Device Creation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: #ffffff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: #ffffff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #4a5568;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
            align-items: center;
        }

        .nav-links > li {
            position: relative;
        }

        .nav-links a {
            color: #4a5568;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 6px;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .nav-links a:hover {
            color: #2d3748;
            background: rgba(74, 85, 104, 0.1);
        }

        /* Dropdown Menus */
        .dropdown {
            position: relative;
        }

        .dropdown-content {
            display: none;
            position: absolute;
            top: 100%;
            left: 0;
            background: #ffffff;
            min-width: 280px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
            border-radius: 8px;
            padding: 1rem 0;
            margin-top: 0.5rem;
            border: 1px solid #e2e8f0;
            z-index: 1001;
        }

        .dropdown:hover .dropdown-content {
            display: block;
            animation: fadeInDown 0.3s ease-out;
        }

        .dropdown-content a {
            color: #4a5568;
            padding: 0.7rem 1.5rem;
            text-decoration: none;
            display: block;
            font-weight: 400;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            border-radius: 0;
        }

        .dropdown-content a:hover {
            background: #f7fafc;
            color: #2d3748;
            padding-left: 2rem;
        }

        .dropdown-icon {
            font-size: 0.8rem;
            transition: transform 0.3s ease;
        }

        .dropdown:hover .dropdown-icon {
            transform: rotate(180deg);
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            position: relative;
            color: #2d3748;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(255, 255, 255, 0.1);
            z-index: 1;
        }

        .hero-content {
            max-width: 800px;
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease-out;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            color: #2d3748;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 0.2s both;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
            color: #4a5568;
        }

        .cta-button {
            display: inline-block;
            background: #4a5568;
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease-out 0.4s both;
            box-shadow: 0 8px 25px rgba(74, 85, 104, 0.3);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .cta-button:hover {
            background: #2d3748;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 12px 35px rgba(74, 85, 104, 0.4);
        }

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

        /* Learn More Section */
        .learn-more {
            padding: 5rem 0;
            background: #ffffff;
            color: #2d3748;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #2d3748;
        }

        .highlight-badge {
            display: inline-block;
            background: #28a745;
            color: white;
            padding: 0.5rem 1.5rem;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 3rem;
        }

        .highlight-products {
            display: none;
            margin-top: 2rem;
        }

        .highlight-products.active {
            display: block;
            animation: fadeIn 0.5s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .product-item {
            background: #ffffff;
            padding: 0;
            border-radius: 12px;
            text-align: left;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid #e2e8f0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            overflow: hidden;
        }

        .product-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(40, 167, 69, 0.15);
            border-color: #28a745;
        }

        .product-icon {
            background: #28a745;
            color: white;
            padding: 3rem 2rem;
            text-align: center;
            font-size: 3rem;
            margin-bottom: 0;
        }

        .product-content {
            padding: 2rem;
        }

        .product-item h3 {
            margin-bottom: 1rem;
            font-size: 1.4rem;
            color: #2d3748;
            font-weight: 600;
        }

        .product-item p {
            color: #4a5568;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            font-size: 0.95rem;
        }

        .see-detail-btn {
            color: #28a745;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            border-bottom: 2px solid transparent;
            transition: all 0.3s ease;
        }

        .see-detail-btn:hover {
            border-bottom-color: #28a745;
        }

        .product-description {
            display: none;
            margin-top: 1rem;
            padding: 1.5rem;
            background: #f8f9fa;
            color: #333;
            border-radius: 8px;
            border-left: 4px solid #28a745;
        }

        .product-description.active {
            display: block;
            animation: slideDown 0.3s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* PAMS Section */
        .pams-section {
            background: rgba(74, 85, 104, 0.1);
            backdrop-filter: blur(10px);
            padding: 3rem;
            border-radius: 20px;
            margin-top: 3rem;
            text-align: center;
            border: 2px solid rgba(74, 85, 104, 0.2);
        }

        .pams-section h2 {
            margin-bottom: 1rem;
            font-size: 2rem;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
            color: #2d3748;
        }

        .pams-section p {
            margin-bottom: 2rem;
            font-size: 1.1rem;
            color: #4a5568;
        }

        .explore-button {
            background: #4a5568;
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .explore-button:hover {
            background: #2d3748;
            transform: translateY(-2px) scale(1.05);
        }

        .pams-description {
            display: none;
            margin-top: 2rem;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            border-radius: 12px;
            text-align: left;
            border: 1px solid rgba(74, 85, 104, 0.3);
        }

        .pams-description.active {
            display: block;
            animation: fadeIn 0.5s ease-in-out;
        }

        /* Technology Section */
        .technology-section {
            padding: 5rem 0;
            background: #f8f9fa;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .tech-card {
            background: #ffffff;
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            border: 1px solid #e2e8f0;
        }

        .tech-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.12);
        }

        .tech-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-align: center;
        }

        .tech-card h3 {
            color: #2d3748;
            margin-bottom: 1rem;
            font-size: 1.3rem;
            text-align: center;
        }

        .tech-card p {
            color: #4a5568;
            margin-bottom: 1.5rem;
            text-align: center;
        }

        .tech-features {
            list-style: none;
            padding: 0;
        }

        .tech-features li {
            color: #4a5568;
            padding: 0.5rem 0;
            padding-left: 1.5rem;
            position: relative;
        }

        .tech-features li:before {
            content: "✓";
            color: #28a745;
            font-weight: bold;
            position: absolute;
            left: 0;
        }

        /* Solutions Section */
        .solutions-section {
            padding: 5rem 0;
            background: #ffffff;
        }

        .solutions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }

        .solution-card {
            background: #ffffff;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            border: 1px solid #e2e8f0;
        }

        .solution-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.15);
        }

        .solution-header {
            background: linear-gradient(135deg, #4a5568 0%, #2d3748 100%);
            color: white;
            padding: 2rem;
            text-align: center;
        }

        .solution-icon {
            font-size: 3.5rem;
            margin-bottom: 1rem;
        }

        .solution-header h3 {
            font-size: 1.5rem;
            margin: 0;
        }

        .solution-content {
            padding: 2rem;
        }

        .solution-content p {
            color: #4a5568;
            margin-bottom: 2rem;
            font-size: 1.1rem;
        }

        .solution-features {
            display: grid;
            gap: 1.5rem;
        }

        .feature-item {
            padding: 1rem;
            background: #f8f9fa;
            border-radius: 8px;
            border-left: 4px solid #28a745;
        }

        .feature-item h4 {
            color: #2d3748;
            margin-bottom: 0.5rem;
            font-size: 1.1rem;
        }

        .feature-item p {
            color: #4a5568;
            margin: 0;
            font-size: 0.95rem;
        }

        /* Products Section */
        .products-section {
            padding: 5rem 0;
            background: #f8f9fa;
        }

        .product-category {
            margin-bottom: 4rem;
        }

        .category-title {
            color: #2d3748;
            font-size: 1.8rem;
            margin-bottom: 2rem;
            padding-bottom: 0.5rem;
            border-bottom: 3px solid #28a745;
            display: inline-block;
        }

        .products-grid-detailed {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 2rem;
        }

        .product-card-detailed {
            background: #ffffff;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            border: 1px solid #e2e8f0;
            display: flex;
            align-items: stretch;
        }

        .product-card-detailed:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.12);
        }

        .product-image {
            background: linear-gradient(135deg, #28a745 0%, #20a143 100%);
            color: white;
            font-size: 3rem;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 120px;
            min-width: 120px;
        }

        .product-info {
            padding: 2rem;
            flex: 1;
        }

        .product-info h4 {
            color: #2d3748;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .product-info p {
            color: #4a5568;
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .product-specs {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .product-specs li {
            color: #4a5568;
            padding: 0.3rem 0;
            font-size: 0.9rem;
        }

        .product-specs li:before {
            color: #28a745;
            font-weight: bold;
            margin-right: 0.5rem;
        }

        /* Services Section */
        .services {
            padding: 5rem 0;
            background: linear-gradient(135deg, #e9ecef 0%, #f8f9fa 100%);
            color: #2d3748;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 20px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid rgba(74, 85, 104, 0.1);
        }

        .service-card:hover {
            transform: translateY(-10px) scale(1.02);
            background: rgba(255, 255, 255, 0.9);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            border-color: rgba(74, 85, 104, 0.2);
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .service-card h3 {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
            color: #2d3748;
        }

        .service-card p {
            color: #4a5568;
        }

        /* Map Section */
        .map-section {
            padding: 5rem 0;
            background: linear-gradient(135deg, #ffffff 0%, #e9ecef 100%);
            color: #2d3748;
        }

        .map-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .map-info {
            padding: 2rem;
        }

        .map-info h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            color: #2d3748;
        }

        .map-info p {
            margin-bottom: 2rem;
            font-size: 1.1rem;
            color: #4a5568;
        }

        .contact-now-button {
            background: #4a5568;
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            display: inline-block;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 8px 25px rgba(74, 85, 104, 0.3);
        }

        .contact-now-button:hover {
            background: #2d3748;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 12px 35px rgba(74, 85, 104, 0.4);
        }

        .map-embed {
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
        }

        .map-embed iframe {
            width: 100%;
            height: 400px;
            border: none;
        }

        /* Contact Section */
        .contact {
            padding: 5rem 0;
            background: linear-gradient(135deg, #4a5568 0%, #2d3748 100%);
            color: white;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .contact-info h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .contact-details {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 20px;
            border: 2px solid rgba(255, 255, 255, 0.2);
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .contact-item span {
            margin-right: 1rem;
            font-size: 1.5rem;
        }

        /* Mobile Menu */
        .mobile-menu-toggle {
            display: none;
            background: none;
            border: none;
            color: #4a5568;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .mobile-menu {
            display: none;
            position: fixed;
            top: 70px;
            left: 0;
            right: 0;
            background: #ffffff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            z-index: 999;
            padding: 1rem 0;
            max-height: 70vh;
            overflow-y: auto;
        }

        .mobile-menu.active {
            display: block;
        }

        .mobile-menu ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .mobile-menu li {
            border-bottom: 1px solid #e2e8f0;
        }

        .mobile-menu a {
            color: #4a5568;
            text-decoration: none;
            font-size: 1rem;
            display: block;
            padding: 1rem 1.5rem;
            transition: all 0.3s ease;
        }

        .mobile-menu a:hover {
            color: #2d3748;
            background: #f7fafc;
        }

        .mobile-submenu {
            background: #f8f9fa;
            padding: 0;
        }

        .mobile-submenu a {
            padding-left: 3rem;
            font-size: 0.9rem;
            color: #666;
        }

        .mobile-dropdown-toggle {
            background: none;
            border: none;
            color: #4a5568;
            font-size: 1rem;
            padding: 1rem 1.5rem;
            width: 100%;
            text-align: left;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .mobile-dropdown-toggle:hover {
            background: #f7fafc;
        }

        /* Footer */
        footer {
            background: #1a202c;
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .mobile-menu-toggle {
                display: block;
            }
            
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .contact-content,
            .map-container {
                grid-template-columns: 1fr;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <a href="#" class="logo">AzIoT.com</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li class="dropdown">
                    <a href="#technology">
                        Technology 
                        <span class="dropdown-icon">▼</span>
                    </a>
                    <div class="dropdown-content">
                        <a href="#data-collection">📊 Data Collection</a>
                        <a href="#automation">🤖 Automation</a>
                        <a href="#monitoring">🛡️ Protection and Monitoring</a>
                        <a href="#iot">🌐 Internet of Things</a>
                    </div>
                </li>
                <li class="dropdown">
                    <a href="#solutions">
                        Solutions 
                        <span class="dropdown-icon">▼</span>
                    </a>
                    <div class="dropdown-content">
                        <a href="#construction">🏗️ Construction</a>
                        <a href="#home">🏠 Home</a>
                        <a href="#manufacturing">🏭 Manufacturing</a>
                    </div>
                </li>
                <li class="dropdown">
                    <a href="#products">
                        Products 
                        <span class="dropdown-icon">▼</span>
                    </a>
                    <div class="dropdown-content">
                        <a href="#smart-home">🏠 Smart Home</a>
                        <a href="#controller-custom">🎛️ Controller Custom</a>
                        <a href="#smart-agriculture">🌱 Smart Agriculture System</a>
                        <a href="#smart-security">🔒 Smart Security</a>
                        <a href="#smart-trash">🗑️ Smart Trash Bin</a>
                        <a href="#site-safety">⚠️ Smart Site Safety System</a>
                        <a href="#materials-tracking">📦 Smart Construction Materials Tracking</a>
                        <a href="#vibration-detection">🌊 Sistem Pendeteksi Getaran atau Longsor</a>
                        <a href="#weather-station">🌤️ Smart Weather Station untuk Site</a>
                        <a href="#genset-monitoring">⚡ Smart Genset Monitoring</a>
                        <a href="#noise-monitoring">🔊 Pemantauan Kebisingan Proyek</a>
                        <a href="#machine-monitoring">⚙️ Machine Condition Monitoring</a>
                        <a href="#environment-monitoring">🌍 Sistem Pemantauan Lingkungan Pabrik</a>
                        <a href="#preventive-maintenance">🔧 Sistem Preventive Maintenance Otomatis</a>
                        <a href="#production-waste">♻️ Smart Bin untuk Limbah Produksi</a>
                    </div>
                </li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <button class="mobile-menu-toggle" onclick="toggleMobileMenu()">☰</button>
        </nav>
        <div class="mobile-menu" id="mobileMenu">
            <ul>
                <li><a href="#home" onclick="closeMobileMenu()">Home</a></li>
                <li>
                    <button class="mobile-dropdown-toggle" onclick="toggleMobileDropdown('technologyMobile')">
                        Technology <span>▼</span>
                    </button>
                    <ul class="mobile-submenu" id="technologyMobile" style="display: none;">
                        <li><a href="#data-collection" onclick="closeMobileMenu()">📊 Data Collection</a></li>
                        <li><a href="#automation" onclick="closeMobileMenu()">🤖 Automation</a></li>
                        <li><a href="#monitoring" onclick="closeMobileMenu()">🛡️ Protection and Monitoring</a></li>
                        <li><a href="#iot" onclick="closeMobileMenu()">🌐 Internet of Things</a></li>
                    </ul>
                </li>
                <li>
                    <button class="mobile-dropdown-toggle" onclick="toggleMobileDropdown('solutionsMobile')">
                        Solutions <span>▼</span>
                    </button>
                    <ul class="mobile-submenu" id="solutionsMobile" style="display: none;">
                        <li><a href="#construction" onclick="closeMobileMenu()">🏗️ Construction</a></li>
                        <li><a href="#home" onclick="closeMobileMenu()">🏠 Home</a></li>
                        <li><a href="#manufacturing" onclick="closeMobileMenu()">🏭 Manufacturing</a></li>
                    </ul>
                </li>
                <li>
                    <button class="mobile-dropdown-toggle" onclick="toggleMobileDropdown('productsMobile')">
                        Products <span>▼</span>
                    </button>
                    <ul class="mobile-submenu" id="productsMobile" style="display: none;">
                        <li><a href="#smart-home" onclick="closeMobileMenu()">🏠 Smart Home</a></li>
                        <li><a href="#controller-custom" onclick="closeMobileMenu()">🎛️ Controller Custom</a></li>
                        <li><a href="#smart-agriculture" onclick="closeMobileMenu()">🌱 Smart Agriculture System</a></li>
                        <li><a href="#smart-security" onclick="closeMobileMenu()">🔒 Smart Security</a></li>
                        <li><a href="#smart-trash" onclick="closeMobileMenu()">🗑️ Smart Trash Bin</a></li>
                        <li><a href="#site-safety" onclick="closeMobileMenu()">⚠️ Smart Site Safety System</a></li>
                        <li><a href="#materials-tracking" onclick="closeMobileMenu()">📦 Materials Tracking</a></li>
                        <li><a href="#vibration-detection" onclick="closeMobileMenu()">🌊 Pendeteksi Getaran</a></li>
                        <li><a href="#weather-station" onclick="closeMobileMenu()">🌤️ Weather Station</a></li>
                        <li><a href="#genset-monitoring" onclick="closeMobileMenu()">⚡ Genset Monitoring</a></li>
                        <li><a href="#noise-monitoring" onclick="closeMobileMenu()">🔊 Noise Monitoring</a></li>
                        <li><a href="#machine-monitoring" onclick="closeMobileMenu()">⚙️ Machine Monitoring</a></li>
                        <li><a href="#environment-monitoring" onclick="closeMobileMenu()">🌍 Environment Monitor</a></li>
                        <li><a href="#preventive-maintenance" onclick="closeMobileMenu()">🔧 Preventive Maintenance</a></li>
                        <li><a href="#production-waste" onclick="closeMobileMenu()">♻️ Smart Bin Limbah</a></li>
                    </ul>
                </li>
                <li><a href="#contact" onclick="closeMobileMenu()">Contact</a></li>
            </ul>
        </div>
    </header>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Innovative IoT Solutions</h1>
            <p>Transform your ideas into cutting-edge electronic devices with our expert IoT development services</p>
            <a href="#" class="cta-button" onclick="showLearnMore()">Discover More</a>
        </div>
    </section>

    <!-- Technology Section -->
    <section id="technology" class="technology-section">
        <div class="container">
            <h2 class="section-title">Our Technology</h2>
            <div class="tech-grid">
                <div class="tech-card" id="data-collection">
                    <div class="tech-icon">📊</div>
                    <h3>Data Collection</h3>
                    <p>Advanced data acquisition systems for real-time monitoring and analysis.</p>
                    <ul class="tech-features">
                        <li>Real-time sensor data gathering</li>
                        <li>Multi-protocol support (MQTT, HTTP, CoAP)</li>
                        <li>Edge computing capabilities</li>
                        <li>Data preprocessing and filtering</li>
                        <li>Cloud synchronization</li>
                    </ul>
                </div>
                <div class="tech-card" id="automation">
                    <div class="tech-icon">🤖</div>
                    <h3>Automation</h3>
                    <p>Intelligent process automation solutions for enhanced efficiency.</p>
                    <ul class="tech-features">
                        <li>Industrial process control</li>
                        <li>Smart workflow management</li>
                        <li>Predictive maintenance systems</li>
                        <li>Automated reporting and alerts</li>
                        <li>Machine learning integration</li>
                    </ul>
                </div>
                <div class="tech-card" id="monitoring">
                    <div class="tech-icon">🛡️</div>
                    <h3>Protection and Monitoring</h3>
                    <p>Comprehensive security and surveillance systems for 24/7 protection.</p>
                    <ul class="tech-features">
                        <li>24/7 monitoring capabilities</li>
                        <li>Intrusion detection systems</li>
                        <li>Access control management</li>
                        <li>Video surveillance integration</li>
                        <li>Environmental monitoring</li>
                    </ul>
                </div>
                <div class="tech-card" id="iot">
                    <div class="tech-icon">🌐</div>
                    <h3>Internet of Things</h3>
                    <p>End-to-end IoT platform and connectivity solutions.</p>
                    <ul class="tech-features">
                        <li>Device management platforms</li>
                        <li>Communication protocols (WiFi, LoRa, 4G/5G)</li>
                        <li>Cloud integration services</li>
                        <li>Data analytics and visualization</li>
                        <li>Remote device configuration</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Solutions Section -->
    <section id="solutions" class="solutions-section">
        <div class="container">
            <h2 class="section-title">Industry Solutions</h2>
            <div class="solutions-grid">
                <div class="solution-card" id="construction">
                    <div class="solution-header">
                        <div class="solution-icon">🏗️</div>
                        <h3>Construction</h3>
                    </div>
                    <div class="solution-content">
                        <p>Smart construction management solutions for modern building projects.</p>
                        <div class="solution-features">
                            <div class="feature-item">
                                <h4>Project Monitoring</h4>
                                <p>Real-time progress tracking and resource optimization</p>
                            </div>
                            <div class="feature-item">
                                <h4>Equipment Tracking</h4>
                                <p>GPS-based asset tracking and utilization monitoring</p>
                            </div>
                            <div class="feature-item">
                                <h4>Safety Systems</h4>
                                <p>Worker safety monitoring and compliance checking</p>
                            </div>
                            <div class="feature-item">
                                <h4>Material Management</h4>
                                <p>Inventory tracking and supply chain optimization</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="solution-card" id="home">
                    <div class="solution-header">
                        <div class="solution-icon">🏠</div>
                        <h3>Home</h3>
                    </div>
                    <div class="solution-content">
                        <p>Complete smart home automation for modern living.</p>
                        <div class="solution-features">
                            <div class="feature-item">
                                <h4>Home Automation</h4>
                                <p>Intelligent control of lighting, climate, and appliances</p>
                            </div>
                            <div class="feature-item">
                                <h4>Energy Management</h4>
                                <p>Smart energy monitoring and cost optimization</p>
                            </div>
                            <div class="feature-item">
                                <h4>Security Integration</h4>
                                <p>Advanced security systems with mobile alerts</p>
                            </div>
                            <div class="feature-item">
                                <h4>Voice Control</h4>
                                <p>Integration with popular voice assistants</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="solution-card" id="manufacturing">
                    <div class="solution-header">
                        <div class="solution-icon">🏭</div>
                        <h3>Manufacturing</h3>
                    </div>
                    <div class="solution-content">
                        <p>Industrial IoT solutions for smart manufacturing.</p>
                        <div class="solution-features">
                            <div class="feature-item">
                                <h4>Production Monitoring</h4>
                                <p>Real-time production line tracking and analytics</p>
                            </div>
                            <div class="feature-item">
                                <h4>Quality Control</h4>
                                <p>Automated quality assurance and defect detection</p>
                            </div>
                            <div class="feature-item">
                                <h4>Predictive Maintenance</h4>
                                <p>AI-powered maintenance scheduling and optimization</p>
                            </div>
                            <div class="feature-item">
                                <h4>Supply Chain</h4>
                                <p>End-to-end supply chain visibility and optimization</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="products-section">
        <div class="container">
            <h2 class="section-title">Our Products</h2>
            
            <!-- Smart Home Products -->
            <div class="product-category">
                <h3 class="category-title">Smart Home Solutions</h3>
                <div class="products-grid-detailed">
                    <div class="product-card-detailed" id="smart-home">
                        <div class="product-image">🏠</div>
                        <div class="product-info">
                            <h4>Smart Home System</h4>
                            <p>Complete home automation package with mobile app control, voice assistant integration, and energy monitoring dashboard.</p>
                            <ul class="product-specs">
                                <li>✓ Mobile app control</li>
                                <li>✓ Voice assistant integration</li>
                                <li>✓ Energy monitoring</li>
                                <li>✓ Remote access</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="controller-custom">
                        <div class="product-image">🎛️</div>
                        <div class="product-info">
                            <h4>Controller Custom</h4>
                            <p>Customizable control panels for multi-device management with user-friendly interfaces and remote access capabilities.</p>
                            <ul class="product-specs">
                                <li>✓ Customizable interfaces</li>
                                <li>✓ Multi-device control</li>
                                <li>✓ Remote access</li>
                                <li>✓ User-friendly design</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Agriculture & Environment -->
            <div class="product-category">
                <h3 class="category-title">Agriculture & Environment</h3>
                <div class="products-grid-detailed">
                    <div class="product-card-detailed" id="smart-agriculture">
                        <div class="product-image">🌱</div>
                        <div class="product-info">
                            <h4>Smart Agriculture System</h4>
                            <p>Comprehensive agricultural monitoring with soil sensors, automated irrigation, and crop health analysis.</p>
                            <ul class="product-specs">
                                <li>✓ Soil moisture monitoring</li>
                                <li>✓ Automated irrigation</li>
                                <li>✓ Weather integration</li>
                                <li>✓ Crop health monitoring</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="weather-station">
                        <div class="product-image">🌤️</div>
                        <div class="product-info">
                            <h4>Smart Weather Station</h4>
                            <p>Professional weather monitoring for construction sites with real-time data and historical logging.</p>
                            <ul class="product-specs">
                                <li>✓ Real-time weather data</li>
                                <li>✓ Temperature & humidity</li>
                                <li>✓ Wind speed & direction</li>
                                <li>✓ Historical data logging</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Security & Safety -->
            <div class="product-category">
                <h3 class="category-title">Security & Safety</h3>
                <div class="products-grid-detailed">
                    <div class="product-card-detailed" id="smart-security">
                        <div class="product-image">🔒</div>
                        <div class="product-info">
                            <h4>Smart Security System</h4>
                            <p>Integrated surveillance with motion detection, facial recognition, and mobile alerts with cloud backup.</p>
                            <ul class="product-specs">
                                <li>✓ Motion detection</li>
                                <li>✓ Facial recognition</li>
                                <li>✓ Mobile alerts</li>
                                <li>✓ Cloud storage</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="site-safety">
                        <div class="product-image">⚠️</div>
                        <div class="product-info">
                            <h4>Smart Site Safety System</h4>
                            <p>Comprehensive worker safety monitoring with hazard detection and emergency alert systems.</p>
                            <ul class="product-specs">
                                <li>✓ Worker safety monitoring</li>
                                <li>✓ Hazard detection</li>
                                <li>✓ Emergency alerts</li>
                                <li>✓ PPE compliance</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Waste Management -->
            <div class="product-category">
                <h3 class="category-title">Waste Management</h3>
                <div class="products-grid-detailed">
                    <div class="product-card-detailed" id="smart-trash">
                        <div class="product-image">🗑️</div>
                        <div class="product-info">
                            <h4>Smart Trash Bin</h4>
                            <p>Intelligent waste management with fill level monitoring and automated collection scheduling.</p>
                            <ul class="product-specs">
                                <li>✓ Fill level monitoring</li>
                                <li>✓ Collection scheduling</li>
                                <li>✓ Route optimization</li>
                                <li>✓ Cost analytics</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="production-waste">
                        <div class="product-image">♻️</div>
                        <div class="product-info">
                            <h4>Smart Bin Limbah Produksi</h4>
                            <p>Industrial waste monitoring with segregation compliance and environmental impact tracking.</p>
                            <ul class="product-specs">
                                <li>✓ Waste monitoring</li>
                                <li>✓ Segregation compliance</li>
                                <li>✓ Environmental tracking</li>
                                <li>✓ Regulatory reporting</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Construction & Infrastructure -->
            <div class="product-category">
                <h3 class="category-title">Construction & Infrastructure</h3>
                <div class="products-grid-detailed">
                    <div class="product-card-detailed" id="materials-tracking">
                        <div class="product-image">📦</div>
                        <div class="product-info">
                            <h4>Smart Materials Tracking</h4>
                            <p>Advanced material inventory management with supply chain visibility and theft prevention.</p>
                            <ul class="product-specs">
                                <li>✓ Inventory management</li>
                                <li>✓ Supply chain visibility</li>
                                <li>✓ Theft prevention</li>
                                <li>✓ Usage optimization</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="vibration-detection">
                        <div class="product-image">🌊</div>
                        <div class="product-info">
                            <h4>Sistem Pendeteksi Getaran</h4>
                            <p>Seismic monitoring system for landslide detection and structural health monitoring with early warning alerts.</p>
                            <ul class="product-specs">
                                <li>✓ Seismic monitoring</li>
                                <li>✓ Landslide detection</li>
                                <li>✓ Structural health</li>
                                <li>✓ Early warning system</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Monitoring & Maintenance -->
            <div class="product-category">
                <h3 class="category-title">Monitoring & Maintenance</h3>
                <div class="products-grid-detailed">
                    <div class="product-card-detailed" id="genset-monitoring">
                        <div class="product-image">⚡</div>
                        <div class="product-info">
                            <h4>Smart Genset Monitoring</h4>
                            <p>Comprehensive generator monitoring with fuel tracking, performance analysis, and remote control.</p>
                            <ul class="product-specs">
                                <li>✓ Fuel level tracking</li>
                                <li>✓ Performance monitoring</li>
                                <li>✓ Maintenance scheduling</li>
                                <li>✓ Remote control</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="noise-monitoring">
                        <div class="product-image">🔊</div>
                        <div class="product-info">
                            <h4>Noise Monitoring System</h4>
                            <p>Professional noise level monitoring for construction projects with compliance reporting and community impact assessment.</p>
                            <ul class="product-specs">
                                <li>✓ Sound level measurement</li>
                                <li>✓ Compliance reporting</li>
                                <li>✓ Impact assessment</li>
                                <li>✓ Real-time alerts</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="machine-monitoring">
                        <div class="product-image">⚙️</div>
                        <div class="product-info">
                            <h4>Machine Condition Monitoring</h4>
                            <p>Advanced machine health monitoring with vibration analysis and predictive maintenance capabilities.</p>
                            <ul class="product-specs">
                                <li>✓ Vibration analysis</li>
                                <li>✓ Temperature monitoring</li>
                                <li>✓ Predictive maintenance</li>
                                <li>✓ Performance optimization</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="environment-monitoring">
                        <div class="product-image">🌍</div>
                        <div class="product-info">
                            <h4>Environmental Monitoring</h4>
                            <p>Comprehensive factory environmental monitoring with air quality, water testing, and emission tracking.</p>
                            <ul class="product-specs">
                                <li>✓ Air quality monitoring</li>
                                <li>✓ Water quality testing</li>
                                <li>✓ Emission tracking</li>
                                <li>✓ Compliance reporting</li>
                            </ul>
                        </div>
                    </div>
                    <div class="product-card-detailed" id="preventive-maintenance">
                        <div class="product-image">🔧</div>
                        <div class="product-info">
                            <h4>Preventive Maintenance System</h4>
                            <p>Automated maintenance scheduling system with equipment health tracking and cost optimization.</p>
                            <ul class="product-specs">
                                <li>✓ Automated scheduling</li>
                                <li>✓ Health tracking</li>
                                <li>✓ Cost optimization</li>
                                <li>✓ Downtime reduction</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    <section id="learn" class="learn-more">
        <div class="container">
            <div class="highlight-products" id="highlightProducts">
                <div style="text-align: center; margin-bottom: 3rem;">
                    <span class="highlight-badge">HIGHLIGHT</span>
                    <h2 class="section-title">Product / Technology</h2>
                </div>
                <div class="products-grid">
                    <div class="product-item" onclick="toggleDescription('dataCollection')">
                        <div class="product-icon">📊</div>
                        <div class="product-content">
                            <h3>Data Collection</h3>
                            <p>Accurate data collection will help you understand ongoing business processes. Wasted resources and wasted time in collecting...</p>
                            <a href="#" class="see-detail-btn">See Detail</a>
                            <div class="product-description" id="dataCollection">
                                <p>Advanced data collection systems that gather, process, and analyze information from multiple sensors and devices in real-time. Our solutions ensure accurate data capture with minimal latency, supporting various data formats and protocols for seamless integration with existing infrastructure.</p>
                            </div>
                        </div>
                    </div>
                    <div class="product-item" onclick="toggleDescription('automation')">
                        <div class="product-icon">🤖</div>
                        <div class="product-content">
                            <h3>Automation</h3>
                            <p>Implementing automation will give employees more time, resources, and freedom. Automation also increases efficiency, effectiveness...</p>
                            <a href="#" class="see-detail-btn">See Detail</a>
                            <div class="product-description" id="automation">
                                <p>Intelligent automation solutions that streamline processes and reduce manual intervention. Our systems feature adaptive algorithms, predictive maintenance capabilities, and seamless integration with existing workflows to maximize efficiency and minimize operational costs.</p>
                            </div>
                        </div>
                    </div>
                    <div class="product-item" onclick="toggleDescription('protection')">
                        <div class="product-icon">🛡️</div>
                        <div class="product-content">
                            <h3>Protection and Monitoring</h3>
                            <p>Product protection and monitoring is very helpful in getting data about how our customers find, share...</p>
                            <a href="#" class="see-detail-btn">See Detail</a>
                            <div class="product-description" id="protection">
                                <p>Comprehensive security and monitoring systems that provide 24/7 surveillance and threat detection. Features include real-time alerts, encrypted communications, access control, and detailed logging for compliance and audit purposes.</p>
                            </div>
                        </div>
                    </div>
                    <div class="product-item" onclick="toggleDescription('iot')">
                        <div class="product-icon">🌐</div>
                        <div class="product-content">
                            <h3>Internet of Things</h3>
                            <p>The Internet of Things can enable us to get clear information from connected objects, perform analysis based on accurate data...</p>
                            <a href="#" class="see-detail-btn">See Detail</a>
                            <div class="product-description" id="iot">
                                <p>End-to-end IoT solutions that connect devices, sensors, and systems across various industries. Our platform supports multiple communication protocols, cloud integration, edge computing, and scalable architecture for growing business needs.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="pams-section">
                    <h2>PortS Asset Management System (PAMS)</h2>
                    <p>Comprehensive asset tracking and management solution designed for port operations and logistics management.</p>
                    <button class="explore-button" onclick="togglePamsDescription()">Explore</button>
                    <div class="pams-description" id="pamsDescription">
                        <h3>Advanced Port Asset Management</h3>
                        <p><strong>Real-time Asset Tracking:</strong> Monitor containers, vehicles, and equipment locations with GPS and RFID technology.</p>
                        <p><strong>Automated Inventory Management:</strong> Track asset movements, maintenance schedules, and utilization rates automatically.</p>
                        <p><strong>Performance Analytics:</strong> Generate detailed reports on asset performance, downtime analysis, and operational efficiency.</p>
                        <p><strong>Integration Capabilities:</strong> Seamless integration with existing port management systems and third-party logistics platforms.</p>
                        <p><strong>Mobile Access:</strong> Field personnel can access asset information and update status through mobile applications.</p>
                        <p><strong>Predictive Maintenance:</strong> AI-powered algorithms predict maintenance needs before equipment failures occur.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="services" class="services">
        <div class="container">
            <h2 class="section-title">Our Services</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🔧</div>
                    <h3>Custom IoT Device Creation</h3>
                    <p>Design and develop custom Internet of Things devices tailored to your specific needs and requirements</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">📱</div>
                    <h3>Mobile App Development</h3>
                    <p>Create companion mobile applications for seamless device control and monitoring</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">☁️</div>
                    <h3>Cloud Integration</h3>
                    <p>Implement robust cloud solutions for data storage, analytics, and remote device management</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🔒</div>
                    <h3>Security Solutions</h3>
                    <p>Ensure your IoT devices are secure with advanced encryption and authentication protocols</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">⚡</div>
                    <h3>Hardware Prototyping</h3>
                    <p>Rapid prototyping and testing of electronic circuits and components</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🎯</div>
                    <h3>Consultation Services</h3>
                    <p>Expert advice on IoT strategy, technology selection, and implementation planning</p>
                </div>
            </div>
        </div>
    </section>

    <section class="map-section">
        <div class="container">
            <div class="map-container">
                <div class="map-info">
                    <h3>Have a project or want to request a demo?</h3>
                    <p>Contact us immediately and consult further digital needs for your business. We're here to help transform your ideas into innovative IoT solutions.</p>
                    <a href="https://wa.me/085258600345" class="contact-now-button" target="_blank">Contact Now</a>
                </div>
                <div class="map-embed">
                    <iframe 
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d63256.95845318431!2d109.01234567890123!3d-7.456789012345678!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zN8KwMjcnMjQuNCJTIDEwOcKwMDAnNDQuNCJF!5e0!3m2!1sen!2sid!4v1690123456789!5m2!1sen!2sid&q=Jl.+Jend.+Ahmad+Yani+No.08,+Dusun+Krisik,+Kec.+Cipari,+Kabupaten+Cilacap,+Jawa+Tengah+53262" 
                        allowfullscreen="" 
                        loading="lazy">
                    </iframe>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Contact Us</h3>
                    <p>Consult your company's needs with our best consultants. We manage clients wholeheartedly for our loyal customers, with coverage almost throughout Indonesia.</p>
                </div>
                <div class="contact-details">
                    <div class="contact-item">
                        <span>👤</span>
                        <div>
                            <strong>Contact Person:</strong><br>
                            Muhammad Azharul Mangali, Lead IoT Engineer
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>📧</span>
                        <div>
                            <strong>Email:</strong><br>
                            azzamangali70@gmail.com
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>📞</span>
                        <div>
                            <strong>Phone:</strong><br>
                            085 258 600 345
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>🏢</span>
                        <div>
                            <strong>Office:</strong><br>
                            Jl. Jend. Ahmad Yani No.08, Dusun Krisik<br>
                            Kec. Cipari, Kab. Cilacap, Jawa Tengah 53262
                        </div>
                    </div>
                    <div class="contact-item">
                        <span>🕐</span>
                        <div>
                            <strong>Business Hours:</strong><br>
                            Mon-Fri: 8:00 AM - 5:00 PM
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2025 AzIoT.com - Custom IoT Solutions. All rights reserved. | Transforming Ideas into Smart Reality</p>
        </div>
    </footer>

    <script>
        // Show Learn More section
        function showLearnMore() {
            document.getElementById('highlightProducts').classList.add('active');
            document.getElementById('learn').scrollIntoView({ behavior: 'smooth' });
        }

        // Toggle product descriptions
        function toggleDescription(id) {
            const desc = document.getElementById(id);
            const isActive = desc.classList.contains('active');
            
            // Hide all descriptions
            document.querySelectorAll('.product-description').forEach(el => {
                el.classList.remove('active');
            });
            
            // Show clicked description if it wasn't active
            if (!isActive) {
                desc.classList.add('active');
            }
        }

        // Toggle PAMS description
        function togglePamsDescription() {
            const desc = document.getElementById('pamsDescription');
            desc.classList.toggle('active');
        }

        // Mobile menu functionality
        function toggleMobileMenu() {
            const mobileMenu = document.getElementById('mobileMenu');
            mobileMenu.classList.toggle('active');
        }

        function closeMobileMenu() {
            const mobileMenu = document.getElementById('mobileMenu');
            mobileMenu.classList.remove('active');
            
            // Close all mobile dropdowns
            document.querySelectorAll('.mobile-submenu').forEach(submenu => {
                submenu.style.display = 'none';
            });
        }

        function toggleMobileDropdown(id) {
            const submenu = document.getElementById(id);
            const isVisible = submenu.style.display === 'block';
            
            // Close all other submenus
            document.querySelectorAll('.mobile-submenu').forEach(menu => {
                if (menu.id !== id) {
                    menu.style.display = 'none';
                }
            });
            
            // Toggle current submenu
            submenu.style.display = isVisible ? 'none' : 'block';
        }

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                const href = this.getAttribute('href');
                if (href !== '#') {
                    e.preventDefault();
                    const target = document.querySelector(href);
                    if (target) {
                        target.scrollIntoView({ behavior: 'smooth' });
                    }
                }
            });
        });

        // Close mobile menu when clicking outside
        document.addEventListener('click', function(event) {
            const mobileMenu = document.getElementById('mobileMenu');
            const toggleButton = document.querySelector('.mobile-menu-toggle');
            
            if (!mobileMenu.contains(event.target) && !toggleButton.contains(event.target)) {
                mobileMenu.classList.remove('active');
                // Close all mobile dropdowns
                document.querySelectorAll('.mobile-submenu').forEach(submenu => {
                    submenu.style.display = 'none';
                });
            }
        });

        // Header background change on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.boxShadow = '0 2px 20px rgba(0, 0, 0, 0.15)';
            } else {
                header.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
            }
        });

        // Parallax effect for hero section
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            const rate = scrolled * -0.5;
            hero.style.transform = `translateY(${rate}px)`;
        });

        // Add floating animation to service cards
        document.querySelectorAll('.service-card').forEach((card, index) => {
            card.style.animationDelay = `${index * 0.1}s`;
            card.style.animation = 'float 6s ease-in-out infinite';
        });

        // CSS animation for floating effect
        const style = document.createElement('style');
        style.textContent = `
            @keyframes float {
                0%, 100% { transform: translateY(0px); }
                50% { transform: translateY(-10px); }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
