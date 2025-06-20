<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kashi Store - Modern Grocery Delivery</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Modern CSS with CSS Variables */
        :root {
            --primary: #0066cc;
            --secondary: #ffcc00;
            --dark: #1a1a1a;
            --light: #ffffff;
            --gray: #f5f5f5;
            --dark-gray: #666666;
            --success: #28a745;
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            --radius: 12px;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            background-color: var(--gray);
            color: var(--dark);
            line-height: 1.6;
        }

        /* Modern Header with Hamburger Menu */
        header {
            background-color: var(--light);
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
            padding: 1rem 2rem;
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .logo i {
            color: var(--secondary);
        }

        .logo span {
            color: var(--secondary);
        }

        .nav-container {
            display: flex;
            align-items: center;
            gap: 2rem;
        }

        .main-nav {
            display: flex;
            gap: 1.5rem;
        }

        .main-nav a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .main-nav a:hover {
            color: var(--primary);
        }

        .main-nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary);
            transition: var(--transition);
        }

        .main-nav a:hover::after {
            width: 100%;
        }

        .nav-icons {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }

        .nav-icons a {
            color: var(--dark);
            font-size: 1.2rem;
            transition: var(--transition);
        }

        .nav-icons a:hover {
            color: var(--primary);
            transform: translateY(-2px);
        }

        .cart-icon {
            position: relative;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--secondary);
            color: var(--dark);
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 0.7rem;
            font-weight: bold;
        }

        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }

        /* Modern Search Bar */
        .search-container {
            background-color: var(--light);
            padding: 1rem 2rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        .search-bar {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .search-bar input {
            flex: 1;
            padding: 1rem;
            border: none;
            font-size: 1rem;
            outline: none;
        }

        .search-bar button {
            background-color: var(--primary);
            color: var(--light);
            border: none;
            padding: 0 1.5rem;
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
        }

        .search-bar button:hover {
            background-color: #0052a3;
        }

        /* Hero Section with Gradient */
        .hero {
            background: linear-gradient(135deg, var(--primary), #0099ff);
            color: var(--light);
            padding: 4rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://images.unsplash.com/photo-1606787366850-de6330128bfc?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') center/cover;
            opacity: 0.15;
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            font-weight: 800;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 0.8rem 1.8rem;
            border-radius: var(--radius);
            font-weight: 600;
            text-decoration: none;
            transition: var(--transition);
            display: inline-block;
            cursor: pointer;
        }

        .btn-primary {
            background-color: var(--secondary);
            color: var(--dark);
            border: 2px solid var(--secondary);
        }

        .btn-primary:hover {
            background-color: transparent;
            color: var(--secondary);
        }

        .btn-outline {
            background-color: transparent;
            color: var(--light);
            border: 2px solid var(--light);
        }

        .btn-outline:hover {
            background-color: var(--light);
            color: var(--primary);
        }

        /* Categories Section */
        .section {
            padding: 3rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 1.8rem;
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50px;
            height: 4px;
            background-color: var(--secondary);
            border-radius: 2px;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
            gap: 1.5rem;
        }

        .category-card {
            background-color: var(--light);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            cursor: pointer;
            text-align: center;
        }

        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }

        .category-img {
            width: 100%;
            height: 120px;
            object-fit: cover;
        }

        .category-name {
            padding: 1rem;
            font-weight: 600;
        }

        /* Products Section */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background-color: var(--light);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }

        .product-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background-color: var(--success);
            color: var(--light);
            padding: 0.3rem 0.6rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .product-img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-name {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .product-desc {
            color: var(--dark-gray);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .product-price {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .current-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--primary);
        }

        .original-price {
            font-size: 0.9rem;
            color: var(--dark-gray);
            text-decoration: line-through;
        }

        .add-to-cart {
            width: 100%;
            padding: 0.8rem;
            background-color: var(--primary);
            color: var(--light);
            border: none;
            border-radius: var(--radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .add-to-cart:hover {
            background-color: #0052a3;
        }

        /* Features Section */
        .features {
            background-color: var(--light);
            padding: 3rem 2rem;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .feature-card {
            text-align: center;
            padding: 2rem 1.5rem;
            border-radius: var(--radius);
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow);
        }

        .feature-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 1.5rem;
        }

        .feature-title {
            font-size: 1.2rem;
            margin-bottom: 1rem;
            font-weight: 600;
        }

        .feature-desc {
            color: var(--dark-gray);
            font-size: 0.95rem;
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: var(--light);
            padding: 4rem 2rem 2rem;
        }

        .footer-container {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 3rem;
        }

        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 1rem;
            display: inline-block;
        }

        .footer-logo span {
            color: var(--secondary);
        }

        .footer-about {
            margin-bottom: 1.5rem;
            opacity: 0.8;
            font-size: 0.95rem;
        }

        .footer-social {
            display: flex;
            gap: 1rem;
        }

        .footer-social a {
            color: var(--light);
            font-size: 1.2rem;
            transition: var(--transition);
        }

        .footer-social a:hover {
            color: var(--secondary);
            transform: translateY(-3px);
        }

        .footer-column h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 0.5rem;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background-color: var(--secondary);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            transition: var(--transition);
            font-size: 0.95rem;
        }

        .footer-links a:hover {
            color: var(--secondary);
            padding-left: 5px;
        }

        .footer-newsletter input {
            width: 100%;
            padding: 0.8rem;
            border: none;
            border-radius: var(--radius);
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .footer-newsletter button {
            width: 100%;
            padding: 0.8rem;
            background-color: var(--secondary);
            color: var(--dark);
            border: none;
            border-radius: var(--radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }

        .footer-newsletter button:hover {
            background-color: #e6b800;
        }

        .copyright {
            text-align: center;
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            opacity: 0.7;
            font-size: 0.9rem;
        }

        /* Mobile Menu */
        .mobile-menu {
            position: fixed;
            top: 0;
            left: -100%;
            width: 80%;
            max-width: 300px;
            height: 100vh;
            background-color: var(--light);
            z-index: 1000;
            transition: var(--transition);
            padding: 2rem;
            box-shadow: 2px 0 10px rgba(0, 0, 0, 0.1);
            overflow-y: auto;
        }

        .mobile-menu.active {
            left: 0;
        }

        .mobile-menu-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
        }

        .close-menu {
            font-size: 1.5rem;
            cursor: pointer;
        }

        .mobile-nav {
            list-style: none;
        }

        .mobile-nav li {
            margin-bottom: 1rem;
        }

        .mobile-nav a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            font-size: 1.1rem;
            display: block;
            padding: 0.5rem 0;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 999;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }

        @media (max-width: 768px) {
            .main-nav {
                display: none;
            }
            
            .hamburger {
                display: block;
            }
            
            .hero {
                padding: 3rem 1.5rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .section {
                padding: 2rem 1.5rem;
            }
            
            .category-grid {
                grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            }
        }

        @media (max-width: 480px) {
            .header-container {
                padding: 1rem;
            }
            
            .search-container {
                padding: 1rem;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .hero-buttons {
                flex-direction: column;
                gap: 0.8rem;
            }
            
            .btn {
                width: 100%;
                text-align: center;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-container {
                grid-template-columns: 1fr;
                gap: 2rem;
            }
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .animate-fade {
            animation: fadeIn 0.6s ease forwards;
        }

        .delay-1 {
            animation-delay: 0.2s;
        }

        .delay-2 {
            animation-delay: 0.4s;
        }

        .delay-3 {
            animation-delay: 0.6s;
        }
    </style>
</head>
<body>
    <!-- Mobile Menu -->
    <div class="mobile-menu" id="mobileMenu">
        <div class="mobile-menu-header">
            <a href="#" class="logo">KASHI<i class="fas fa-store"></i></a>
            <i class="fas fa-times close-menu" id="closeMenu"></i>
        </div>
        <ul class="mobile-nav">
            <li><a href="#"><i class="fas fa-home"></i> Home</a></li>
            <li><a href="#"><i class="fas fa-list"></i> Categories</a></li>
            <li><a href="#"><i class="fas fa-tag"></i> Deals</a></li>
            <li><a href="#"><i class="fas fa-box"></i> My Orders</a></li>
            <li><a href="#"><i class="fas fa-user"></i> Account</a></li>
            <li><a href="#"><i class="fas fa-question-circle"></i> Help</a></li>
        </ul>
    </div>
    <div class="overlay" id="overlay"></div>

    <!-- Header -->
    <header>
        <div class="header-container">
            <a href="#" class="logo">KASHI<i class="fas fa-store"></i></a>
            
            <div class="nav-container">
                <nav class="main-nav">
                    <a href="#">Home</a>
                    <a href="#">Categories</a>
                    <a href="#">Deals</a>
                    <a href="#">My Orders</a>
                </nav>
                
                <div class="nav-icons">
                    <a href="#"><i class="fas fa-user"></i></a>
                    <a href="#" class="cart-icon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </a>
                </div>
            </div>
            
            <i class="fas fa-bars hamburger" id="hamburger"></i>
        </div>
    </header>

    <!-- Search Bar -->
    <div class="search-container">
        <div class="search-bar">
            <input type="text" placeholder="Search for groceries, household items, and more...">
            <button><i class="fas fa-search"></i> Search</button>
        </div>
    </div>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content animate-fade">
            <h1>Fresh Groceries Delivered to Your Door</h1>
            <p>Shop the best quality products at the lowest prices with fast delivery</p>
            <div class="hero-buttons">
                <a href="#" class="btn btn-primary"><i class="fas fa-shopping-basket"></i> Shop Now</a>
                <a href="#" class="btn btn-outline"><i class="fas fa-tag"></i> View Deals</a>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="section">
        <h2 class="section-title">Shop by Category</h2>
        <div class="category-grid">
            <div class="category-card animate-fade delay-1">
                <img src="https://images.unsplash.com/photo-1518843875459-f738682238a6?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Fruits & Vegetables" class="category-img">
                <h3 class="category-name">Fruits & Vegetables</h3>
            </div>
            <div class="category-card animate-fade delay-1">
                <img src="https://images.unsplash.com/photo-1550583724-b2692b85b150?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Dairy & Eggs" class="category-img">
                <h3 class="category-name">Dairy & Eggs</h3>
            </div>
            <div class="category-card animate-fade delay-1">
                <img src="https://images.unsplash.com/photo-1509440159596-0249088772ff?ixlib=rb-1.2.1&auto=format&fit=crop&w=1352&q=80" alt="Meat & Seafood" class="category-img">
                <h3 class="category-name">Meat & Seafood</h3>
            </div>
            <div class="category-card animate-fade delay-2">
                <img src="https://images.unsplash.com/photo-1592921870789-04563d55041c?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Bakery" class="category-img">
                <h3 class="category-name">Bakery</h3>
            </div>
            <div class="category-card animate-fade delay-2">
                <img src="https://images.unsplash.com/photo-1606787366850-de6330128bfc?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Frozen Foods" class="category-img">
                <h3 class="category-name">Frozen Foods</h3>
            </div>
            <div class="category-card animate-fade delay-3">
                <img src="https://images.unsplash.com/photo-1615486364404-fbb476e7d7b6?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Beverages" class="category-img">
                <h3 class="category-name">Beverages</h3>
            </div>
        </div>
    </section>

    <!-- Popular Products -->
    <section class="section">
        <h2 class="section-title">Popular Products</h2>
        <div class="product-grid">
            <div class="product-card animate-fade">
                <span class="product-badge">Fresh</span>
                <img src="https://images.unsplash.com/photo-1589927986089-35812388d1f4?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Organic Apples" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Organic Apples</h3>
                    <p class="product-desc">Fresh, crisp and delicious, 1lb bag</p>
                    <div class="product-price">
                        <span class="current-price">$2.99</span>
                        <span class="original-price">$3.49</span>
                    </div>
                    <button class="add-to-cart"><i class="fas fa-cart-plus"></i> Add to Cart</button>
                </div>
            </div>
            <div class="product-card animate-fade delay-1">
                <img src="https://images.unsplash.com/photo-1550583724-b2692b85b150?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Fresh Milk" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Fresh Milk</h3>
                    <p class="product-desc">1 Gallon, 2% reduced fat</p>
                    <div class="product-price">
                        <span class="current-price">$3.49</span>
                    </div>
                    <button class="add-to-cart"><i class="fas fa-cart-plus"></i> Add to Cart</button>
                </div>
            </div>
            <div class="product-card animate-fade delay-1">
                <span class="product-badge">Sale</span>
                <img src="https://images.unsplash.com/photo-1509440159596-0249088772ff?ixlib=rb-1.2.1&auto=format&fit=crop&w=1352&q=80" alt="Chicken Breast" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Chicken Breast</h3>
                    <p class="product-desc">Boneless, skinless, 1 lb pack</p>
                    <div class="product-price">
                        <span class="current-price">$4.99</span>
                        <span class="original-price">$5.99</span>
                    </div>
                    <button class="add-to-cart"><i class="fas fa-cart-plus"></i> Add to Cart</button>
                </div>
            </div>
            <div class="product-card animate-fade delay-2">
                <img src="https://images.unsplash.com/photo-1592921870789-04563d55041c?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Whole Wheat Bread" class="product-img">
                <div class="product-info">
                    <h3 class="product-name">Whole Wheat Bread</h3>
                    <p class="product-desc">20 oz, freshly baked</p>
                    <div class="product-price">
                        <span class="current-price">$2.49</span>
                    </div>
                    <button class="add-to-cart"><i class="fas fa-cart-plus"></i> Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="section">
            <h2 class="section-title">Why Choose Kashi Store</h2>
            <div class="features-grid">
                <div class="feature-card animate-fade">
                    <div class="feature-icon">
                        <i class="fas fa-truck"></i>
                    </div>
                    <h3 class="feature-title">Fast Delivery</h3>
                    <p class="feature-desc">Get your groceries delivered in as little as 2 hours with our express service.</p>
                </div>
                <div class="feature-card animate-fade delay-1">
                    <div class="feature-icon">
                        <i class="fas fa-leaf"></i>
                    </div>
                    <h3 class="feature-title">Fresh Quality</h3>
                    <p class="feature-desc">We source only the freshest products from trusted local suppliers.</p>
                </div>
                <div class="feature-card animate-fade delay-2">
                    <div class="feature-icon">
                        <i class="fas fa-percent"></i>
                    </div>
                    <h3 class="feature-title">Best Prices</h3>
                    <p class="feature-desc">Enjoy competitive prices and weekly deals on thousands of items.</p>
                </div>
                <div class="feature-card animate-fade delay-3">
                    <div class="feature-icon">
                        <i class="fas fa-undo"></i>
                    </div>
                    <h3 class="feature-title">Easy Returns</h3>
                    <p class="feature-desc">Not satisfied? Return any item within 7 days for a full refund.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-column">
                <a href="#" class="footer-logo">KASHI<span>STORE</span></a>
                <p class="footer-about">Your one-stop shop for all grocery needs. Fresh, fast, and affordable delivery to your doorstep.</p>
                <div class="footer-social">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h3>Quick Links</h3>
                <ul class="footer-links">
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Shop</a></li>
                    <li><a href="#">About Us</a></li>
                    <li><a href="#">Contact</a></li>
                    <li><a href="#">FAQ</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Categories</h3>
                <ul class="footer-links">
                    <li><a href="#">Fruits & Vegetables</a></li>
                    <li><a href="#">Dairy & Eggs</a></li>
                    <li><a href="#">Meat & Seafood</a></li>
                    <li><a href="#">Bakery</a></li>
                    <li><a href="#">Beverages</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Newsletter</h3>
                <p>Subscribe to get updates on new products and special offers</p>
                <div class="footer-newsletter">
                    <input type="email" placeholder="Your email address">
                    <button>Subscribe</button>
                </div>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 Kashi Store. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Modern JavaScript with ES6 features
        document.addEventListener('DOMContentLoaded', function() {
            // Mobile Menu Toggle
            const hamburger = document.getElementById('hamburger');
            const closeMenu = document.getElementById('closeMenu');
            const mobileMenu = document.getElementById('mobileMenu');
            const overlay = document.getElementById('overlay');
            
            hamburger.addEventListener('click', () => {
                mobileMenu.classList.add('active');
                overlay.classList.add('active');
                document.body.style.overflow = 'hidden';
            });
            
            closeMenu.addEventListener('click', () => {
                mobileMenu.classList.remove('active');
                overlay.classList.remove('active');
                document.body.style.overflow = '';
            });
            
            overlay.addEventListener('click', () => {
                mobileMenu.classList.remove('active');
                overlay.classList.remove('active');
                document.body.style.overflow = '';
            });
            
            // Cart Functionality
            let cartCount = 0;
            const cartCountElement = document.querySelector('.cart-count');
            const addToCartButtons = document.querySelectorAll('.add-to-cart');
            
            addToCartButtons.forEach(button => {
                button.addEventListener('click', function() {
                    cartCount++;
                    cartCountElement.textContent = cartCount;
                    
                    // Get product info
                    const productCard = this.closest('.product-card');
                    const productName = productCard.querySelector('.product-name').textContent;
                    const productPrice = productCard.querySelector('.current-price').textContent;
                    
                    // Animation
                    this.innerHTML = '<i class="fas fa-check"></i> Added';
                    this.style.backgroundColor = 'var(--success)';
                    
                    setTimeout(() => {
                        this.innerHTML = '<i class="fas fa-cart-plus"></i> Add to Cart';
                        this.style.backgroundColor = 'var(--primary)';
                    }, 2000);
                    
                    // Cart icon animation
                    const cartIcon = document.querySelector('.cart-icon');
                    cartIcon.classList.add('animate-bounce');
                    setTimeout(() => {
                        cartIcon.classList.remove('animate-bounce');
                    }, 1000);
                });
            });
            
            // Search Functionality
            const searchInput = document.querySelector('.search-bar input');
            const searchButton = document.querySelector('.search-bar button');
            
            searchButton.addEventListener('click', () => {
                const searchTerm = searchInput.value.trim();
                if (searchTerm) {
                    alert(`Searching for: ${searchTerm}`);
                    // In a real app, filter products or make API call
                }
            });
            
            searchInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    searchButton.click();
                }
            });
            
            // Category Card Click
            const categoryCards = document.querySelectorAll('.category-card');
            categoryCards.forEach(card => {
                card.addEventListener('click', () => {
                    const categoryName = card.querySelector('.category-name').textContent;
                    alert(`Showing products in ${categoryName} category`);
                    // In a real app, filter products by category
                });
            });
            
            // Hero Button Click
            document.querySelector('.hero .btn-primary').addEventListener('click', (e) => {
                e.preventDefault();
                alert('Showing all products!');
            });
            
            document.querySelector('.hero .btn-outline').addEventListener('click', (e) => {
                e.preventDefault();
                alert('Showing current deals!');
            });
            
            // Newsletter Subscription
            const newsletterButton = document.querySelector('.footer-newsletter button');
            newsletterButton.addEventListener('click', () => {
                const emailInput = document.querySelector('.footer-newsletter input');
                if (emailInput.value.includes('@')) {
                    alert('Thank you for subscribing to our newsletter!');
                    emailInput.value = '';
                } else {
                    alert('Please enter a valid email address');
                }
            });
            
            // Intersection Observer for animations
            const animateElements = document.querySelectorAll('.animate-fade');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, { threshold: 0.1 });
            
            animateElements.forEach(element => {
                element.style.opacity = 0;
                element.style.transform = 'translateY(20px)';
                element.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(element);
            });
        });
    </script>
</body>
</html>
