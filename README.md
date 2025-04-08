<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NOVA Algorithm | AI Trading Signals</title>
    <!-- GitHub Pages Deployment Ready -->
    <meta name="description" content="Advanced AI-powered trading indicators for TradingView">
    <!-- Favicon -->
    <link rel="icon" href="https://via.placeholder.com/50/FFD700/000000?text=NOVA">
    <!-- Fonts & Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        :root {
            --primary: #FFD700; /* Gold/Yellow */
            --primary-dark: #FFC000;
            --secondary: #FF0000; /* Red */
            --dark: #000000; /* Black */
            --light: #F8F9FA;
            --gradient: linear-gradient(135deg, #FFD700 0%, #FF0000 100%);
        }

        body {
            font-family: 'Kanit', sans-serif;
            background-color: var(--dark);
            color: white;
            overflow-x: hidden;
        }

        /* ===== NAVBAR ===== */
        .navbar {
            background-color: rgba(0, 0, 0, 0.9);
            border-bottom: 1px solid var(--primary);
        }

        .navbar-brand {
            font-weight: 700;
            font-size: 1.8rem;
            color: var(--primary);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .nav-link {
            color: white;
            font-weight: 500;
            margin: 0 0.5rem;
            position: relative;
        }

        .nav-link:hover {
            color: var(--primary);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary);
            transition: width 0.3s;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        /* ===== HERO SECTION ===== */
        .hero {
            min-height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)), 
                        url('https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-transform: uppercase;
        }

        .btn-primary {
            background: var(--primary);
            color: var(--dark);
            font-weight: 600;
            border: none;
            padding: 0.75rem 2rem;
            transition: all 0.3s;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);
            background: var(--primary-dark);
        }

        .btn-outline {
            border: 2px solid var(--primary);
            color: var(--primary);
            background: transparent;
        }

        .btn-outline:hover {
            background: var(--primary);
            color: var(--dark);
        }

        /* ===== FEATURES ===== */
        .feature-card {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 215, 0, 0.3);
            border-radius: 10px;
            transition: all 0.3s;
            height: 100%;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 10px 20px rgba(255, 215, 0, 0.1);
        }

        .feature-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        /* ===== PRICING ===== */
        .pricing-card {
            background: rgba(0, 0, 0, 0.7);
            border: 1px solid rgba(255, 0, 0, 0.3);
            border-radius: 10px;
            transition: all 0.3s;
        }

        .pricing-card.popular {
            border: 2px solid var(--primary);
            box-shadow: 0 0 30px rgba(255, 215, 0, 0.2);
        }

        .price {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
        }

        /* ===== TESTIMONIALS ===== */
        .testimonial-card {
            background: rgba(0, 0, 0, 0.5);
            border-left: 3px solid var(--primary);
        }

        /* ===== FOOTER ===== */
        .footer {
            background-color: #000;
            border-top: 1px solid var(--primary);
        }

        .social-icon {
            width: 40px;
            height: 40px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 215, 0, 0.1);
            border-radius: 50%;
            color: var(--primary);
            transition: all 0.3s;
        }

        .social-icon:hover {
            background: var(--primary);
            color: var(--dark);
            transform: translateY(-3px);
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-dark fixed-top">
        <div class="container">
            <a class="navbar-brand" href="#">NOVA</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item"><a class="nav-link" href="#features">Features</a></li>
                    <li class="nav-item"><a class="nav-link" href="#pricing">Pricing</a></li>
                    <li class="nav-item"><a class="nav-link" href="#testimonials">Testimonials</a></li>
                    <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
                </ul>
                <a href="#signup" class="btn btn-primary ms-lg-3">Get Started</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero d-flex align-items-center">
        <div class="container">
            <div class="row align-items-center">
                <div class="col-lg-6">
                    <h1 class="mb-4">AI-POWERED TRADING SIGNALS</h1>
                    <p class="lead mb-4">NOVA Algorithm delivers institutional-grade trading indicators with 90%+ accuracy across all markets.</p>
                    <div class="d-flex flex-wrap gap-3">
                        <a href="#signup" class="btn btn-primary">Start Free Trial</a>
                        <a href="#demo" class="btn btn-outline">Live Demo</a>
                    </div>
                </div>
                <div class="col-lg-6 d-none d-lg-block">
                    <img src="https://via.placeholder.com/800x600/000000/FFD700?text=NOVA+ALGORITHM" alt="NOVA Dashboard" class="img-fluid">
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="py-5">
        <div class="container">
            <div class="text-center mb-5">
                <h2 class="fw-bold mb-3">WHY CHOOSE NOVA?</h2>
                <div class="d-flex justify-content-center">
                    <div style="width: 100px; height: 3px; background: var(--gradient);"></div>
                </div>
            </div>
            <div class="row g-4">
                <div class="col-md-6 col-lg-4">
                    <div class="feature-card p-4">
                        <div class="feature-icon">
                            <i class="fas fa-robot"></i>
                        </div>
                        <h3>Adaptive AI</h3>
                        <p>Our machine learning models continuously improve based on live market conditions.</p>
                    </div>
                </div>
                <div class="col-md-6 col-lg-4">
                    <div class="feature-card p-4">
                        <div class="feature-icon">
                            <i class="fas fa-bolt"></i>
                        </div>
                        <h3>Real-Time Alerts</h3>
                        <p>Get instant notifications via SMS, Email, or Mobile App when signals trigger.</p>
                    </div>
                </div>
                <div class="col-md-6 col-lg-4">
                    <div class="feature-card p-4">
                        <div class="feature-icon">
                            <i class="fas fa-sliders-h"></i>
                        </div>
                        <h3>Fully Customizable</h3>
                        <p>Adjust every parameter to match your trading style and risk tolerance.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="py-5 bg-dark">
        <div class="container">
            <div class="text-center mb-5">
                <h2 class="fw-bold mb-3">SIMPLE PRICING</h2>
                <div class="d-flex justify-content-center">
                    <div style="width: 100px; height: 3px; background: var(--gradient);"></div>
                </div>
            </div>
            <div class="row g-4">
                <div class="col-md-4">
                    <div class="pricing-card h-100 p-4">
                        <h3>BASIC</h3>
                        <p>For beginner traders</p>
                        <div class="price my-3">$29<small>/mo</small></div>
                        <ul class="list-unstyled mb-4">
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> Core Indicators</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> Email Alerts</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> Basic Support</li>
                        </ul>
                        <a href="#signup" class="btn btn-outline w-100">Get Started</a>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="pricing-card h-100 p-4 popular">
                        <span class="badge bg-primary mb-3">POPULAR</span>
                        <h3>PRO</h3>
                        <p>For serious traders</p>
                        <div class="price my-3">$97<small>/mo</small></div>
                        <ul class="list-unstyled mb-4">
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> All Indicators</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> SMS & App Alerts</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> Priority Support</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> Backtesting Tools</li>
                        </ul>
                        <a href="#signup" class="btn btn-primary w-100">Get Started</a>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="pricing-card h-100 p-4">
                        <h3>ELITE</h3>
                        <p>For professionals</p>
                        <div class="price my-3">$297<small>/mo</small></div>
                        <ul class="list-unstyled mb-4">
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> All Pro Features</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> Custom Indicators</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> VIP Support</li>
                            <li class="mb-2"><i class="fas fa-check text-success me-2"></i> 1-on-1 Training</li>
                        </ul>
                        <a href="#signup" class="btn btn-outline w-100">Get Started</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section id="testimonials" class="py-5">
        <div class="container">
            <div class="text-center mb-5">
                <h2 class="fw-bold mb-3">TRADER TESTIMONIALS</h2>
                <div class="d-flex justify-content-center">
                    <div style="width: 100px; height: 3px; background: var(--gradient);"></div>
                </div>
            </div>
            <div class="row g-4">
                <div class="col-md-4">
                    <div class="testimonial-card p-4 h-100">
                        <div class="d-flex align-items-center mb-3">
                            <img src="https://randomuser.me/api/portraits/men/32.jpg" class="rounded-circle me-3" width="50" alt="">
                            <div>
                                <h5 class="mb-0">Michael T.</h5>
                                <small>Day Trader</small>
                            </div>
                        </div>
                        <p>"NOVA has increased my win rate by over 40%. The signals are incredibly accurate."</p>
                        <div class="text-warning">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="testimonial-card p-4 h-100">
                        <div class="d-flex align-items-center mb-3">
                            <img src="https://randomuser.me/api/portraits/women/44.jpg" class="rounded-circle me-3" width="50" alt="">
                            <div>
                                <h5 class="mb-0">Sarah K.</h5>
                                <small>Swing Trader</small>
                            </div>
                        </div>
                        <p>"The multi-timeframe analysis helps me capture bigger moves with confidence."</p>
                        <div class="text-warning">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star-half-alt"></i>
                        </div>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="testimonial-card p-4 h-100">
                        <div class="d-flex align-items-center mb-3">
                            <img src="https://randomuser.me/api/portraits/men/75.jpg" class="rounded-circle me-3" width="50" alt="">
                            <div>
                                <h5 class="mb-0">David R.</h5>
                                <small>Fund Manager</small>
                            </div>
                        </div>
                        <p>"We've integrated NOVA into our institutional trading desk with excellent results."</p>
                        <div class="text-warning">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="py-5" style="background: var(--gradient);">
        <div class="container text-center">
            <h2 class="fw-bold mb-4">READY TO TRANSFORM YOUR TRADING?</h2>
            <p class="lead mb-4">Start your 7-day free trial today. No credit card required.</p>
            <a href="#signup" class="btn btn-dark btn-lg px-5">GET STARTED NOW</a>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer py-5">
        <div class="container">
            <div class="row">
                <div class="col-lg-4 mb-4 mb-lg-0">
                    <h3 class="fw-bold mb-3">NOVA</h3>
                    <p class="mb-4">Advanced trading algorithms powered by artificial intelligence.</p>
                    <div class="social-links">
                        <a href="#" class="social-icon me-2"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-icon me-2"><i class="fab fa-telegram"></i></a>
                        <a href="#" class="social-icon me-2"><i class="fab fa-youtube"></i></a>
                        <a href="#" class="social-icon"><i class="fab fa-discord"></i></a>
                    </div>
                </div>
                <div class="col-lg-2 col-md-4 mb-4 mb-md-0">
                    <h5 class="mb-3">Products</h5>
                    <ul class="list-unstyled">
                        <li class="mb-2"><a href="#" class="text-decoration-none">NOVA Pro</a></li>
                        <li class="mb-2"><a href="#" class="text-decoration-none">NOVA Basic</a></li>
                        <li><a href="#" class="text-decoration-none">NOVA Elite</a></li>
                    </ul>
                </div>
                <div class="col-lg-2 col-md-4 mb-4 mb-md-0">
                    <h5 class="mb-3">Resources</h5>
                    <ul class="list-unstyled">
                        <li class="mb-2"><a href="#" class="text-decoration-none">Documentation</a></li>
                        <li class="mb-2"><a href="#" class="text-decoration-none">Tutorials</a></li>
                        <li><a href="#" class="text-decoration-none">Blog</a></li>
                    </ul>
                </div>
                <div class="col-lg-2 col-md-4 mb-4 mb-md-0">
                    <h5 class="mb-3">Company</h5>
                    <ul class="list-unstyled">
                        <li class="mb-2"><a href="#" class="text-decoration-none">About</a></li>
                        <li class="mb-2"><a href="#" class="text-decoration-none">Contact</a></li>
                        <li><a href="#" class="text-decoration-none">Careers</a></li>
                    </ul>
                </div>
                <div class="col-lg-2 col-md-4">
                    <h5 class="mb-3">Legal</h5>
                    <ul class="list-unstyled">
                        <li class="mb-2"><a href="#" class="text-decoration-none">Terms</a></li>
                        <li class="mb-2"><a href="#" class="text-decoration-none">Privacy</a></li>
                        <li><a href="#" class="text-decoration-none">Disclaimer</a></li>
                    </ul>
                </div>
            </div>
            <hr class="my-4" style="border-color: rgba(255,255,255,0.1);">
            <div class="text-center">
                <p class="mb-0">&copy; 2023 NOVA Algorithm. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Navbar background change on scroll
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 50) {
                navbar.style.backgroundColor = 'rgba(0, 0, 0, 0.95)';
                navbar.style.boxShadow = '0 2px 10px rgba(255, 215, 0, 0.1)';
            } else {
                navbar.style.backgroundColor = 'rgba(0, 0, 0, 0.9)';
                navbar.style.boxShadow = 'none';
            }
        });
    </script>
</body>
</html>
