<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nivesh AI - Your Financial Guide</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: system-ui, -apple-system, sans-serif;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideIn {
            from { transform: translateX(-100px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }

        .animate-in {
            animation: fadeIn 1s ease-out forwards;
        }

        body {
            background: linear-gradient(135deg, #0a0a0a, #1a1a1a);
            color: #ffd700;
            min-height: 100vh;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 5%;
            background: rgba(26, 26, 26, 0.9);
            position: fixed;
            width: 100%;
            z-index: 1000;
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 215, 0, 0.3);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #ffd700;
            animation: slideIn 1s ease-out;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: #ffd700;
            text-decoration: none;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .nav-links a:hover {
            color: #ffcc00;
            transform: translateY(-2px);
        }

        .get-started {
            background: linear-gradient(45deg, #ffcc00, #ffd700);
            color: black;
            padding: 0.5rem 1.5rem;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .get-started:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(255, 204, 0, 0.4);
        }

        section {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            padding: 5rem 5%;
            opacity: 0;
        }

        main {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 5%;
        }

        .hero-content {
            max-width: 600px;
            animation: fadeIn 1s ease-out;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            background: linear-gradient(45deg, #ffcc00, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            background: linear-gradient(45deg, #ffcc00, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #ffd700;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
        }

        .primary-btn {
            background: linear-gradient(45deg, #ffcc00, #ffd700);
            color: black;
            padding: 0.8rem 2rem;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .primary-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(255, 204, 0, 0.4);
        }

        .secondary-btn {
            background: transparent;
            color: #ffd700;
            padding: 0.8rem 2rem;
            border-radius: 25px;
            text-decoration: none;
            border: 1px solid #ffd700;
            transition: all 0.3s ease;
        }

        .secondary-btn:hover {
            background: rgba(255, 215, 0, 0.1);
            transform: scale(1.05);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .feature-card {
            background: rgba(26, 26, 26, 0.6);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 215, 0, 0.3);
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            border-color: #ffd700;
            box-shadow: 0 0 30px rgba(255, 204, 0, 0.2);
        }

        .steps-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .step-card {
            background: rgba(26, 26, 26, 0.6);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 215, 0, 0.3);
            position: relative;
        }

        .step-number {
            position: absolute;
            top: -20px;
            left: -20px;
            width: 40px;
            height: 40px;
            background: linear-gradient(45deg, #ffcc00, #ffd700);
            color: black;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .testimonial-card {
            background: rgba(26, 26, 26, 0.6);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 215, 0, 0.3);
        }

        .contact-form {
            max-width: 500px;
            margin: 0 auto;
            background: rgba(26, 26, 26, 0.6);
            padding: 2rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 215, 0, 0.3);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #ffd700;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border-radius: 5px;
            border: 1px solid rgba(255, 215, 0, 0.3);
            background: rgba(26, 26, 26, 0.3);
            color: white;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #ffd700;
            box-shadow: 0 0 10px rgba(255, 204, 0, 0.2);
        }

        .active {
            display: flex !important;
            animation: fadeIn 1s ease-out forwards;
        }
    </style>
</head>
<body>
    <nav>
        <div class="logo">Nivesh AI</div>
        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#features">Features</a>
            <a href="#how-it-works">How It Works</a>
            <a href="#testimonials">Testimonials</a>
            <a href="#contact">Contact</a>
        </div>
        <a href="#" class="get-started">Get Started</a>
    </nav>

    <main id="home">
        <div class="hero-content">
            <h1>Your AI-Powered Financial Guide</h1>
            <p>Nivesh AI helps you make smarter investment decisions with real-time insights and expert analysis.</p>
            <div class="cta-buttons">
                <a href="#" class="primary-btn">Try for Free</a>
                <a href="#" class="secondary-btn">Learn More</a>
            </div>
        </div>
    </main>

    <section id="features">
        <h2>Powerful Features</h2>
        <div class="features-grid">
            <div class="feature-card">
                <h3>Real-time Analysis</h3>
                <p>Get instant insights on market trends and investment opportunities as they happen.</p>
            </div>
            <div class="feature-card">
                <h3>Portfolio Optimization</h3>
                <p>AI-driven recommendations to optimize your portfolio for maximum returns.</p>
            </div>
            <div class="feature-card">
                <h3>Risk Management</h3>
                <p>Advanced risk assessment tools to protect your investments.</p>
            </div>
            <div class="feature-card">
                <h3>Market Predictions</h3>
                <p>Machine learning models to forecast market trends and potential opportunities.</p>
            </div>
        </div>
    </section>

    <section id="how-it-works">
        <h2>How It Works</h2>
        <div class="steps-container">
            <div class="step-card">
                <div class="step-number">1</div>
                <h3>Connect Your Portfolio</h3>
                <p>Securely link your investment accounts to get started with personalized analysis.</p>
            </div>
            <div class="step-card">
                <div class="step-number">2</div>
                <h3>Get AI Analysis</h3>
                <p>Our AI analyzes your portfolio and market conditions to generate insights.</p>
            </div>
            <div class="step-card">
                <div class="step-number">3</div>
                <h3>Optimize & Grow</h3>
                <p>Follow AI-powered recommendations to optimize your investment strategy.</p>
            </div>
        </div>
    </section>

    <section id="testimonials">
        <h2>What Our Users Say</h2>
        <div class="testimonials-grid">
            <div class="testimonial-card">
                <p>"Nivesh AI has transformed how I manage my investments. The AI insights are incredibly accurate."</p>
                <h4>- Sarah Johnson</h4>
                <p>Investment Manager</p>
            </div>
            <div class="testimonial-card">
                <p>"The real-time analysis and risk management features have helped me make better investment decisions."</p>
                <h4>- Michael Chen</h4>
                <p>Private Investor</p>
            </div>
            <div class="testimonial-card">
                <p>"Finally, an AI tool that makes sense of the complex world of investments!"</p>
                <h4>- Emily Rodriguez</h4>
                <p>Financial Advisor</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <h2>Get in Touch</h2>
        <div class="contact-form">
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" placeholder="Your name">
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" placeholder="Your email">
            </div>
            <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" rows="5" placeholder="Your message"></textarea>
            </div>
            <a href="#" class="primary-btn">Send Message</a>
        </div>
    </section>

    <script>
        // Navigation with animations
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const sectionId = link.getAttribute('href').substring(1);
                document.querySelectorAll('main, section').forEach(section => {
                    section.style.display = 'none';
                });
                document.getElementById(sectionId).style.display = 'flex';
            });
        });

        // Intersection Observer for scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate-in');
                }
            });
        }, { threshold: 0.1 });

        // Observe all sections and cards
        document.querySelectorAll('section, .feature-card, .step-card, .testimonial-card').forEach(element => {
            observer.observe(element);
        });
    </script>
</body>
</html>
