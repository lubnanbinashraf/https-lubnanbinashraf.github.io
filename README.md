# https-lubnanbinashraf.github.io
My personal portfolio website
 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lubnan Bin Ashraf - Portfolio</title>
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
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
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
            color: white;
            text-decoration: none;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 25px;
        }

        .nav-links a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><polygon fill="rgba(255,255,255,0.1)" points="0,0 1000,300 1000,1000 0,700"/><polygon fill="rgba(255,255,255,0.05)" points="0,200 1000,0 1000,400 0,600"/></svg>') no-repeat center center;
            background-size: cover;
            animation: float 20s ease-in-out infinite;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease-out;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease-out 0.3s both;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            padding: 1rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease-out 0.6s both;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .cta-button:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        /* Sections */
        section {
            padding: 5rem 0;
            background: white;
            margin: 2rem 0;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }

        .about-image {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 8rem;
            color: white;
            margin: 0 auto;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .about-text {
            font-size: 1.1rem;
            color: #666;
            line-height: 1.8;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-card {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: #667eea;
        }

        .skill-card h3 {
            margin-bottom: 1rem;
            color: #333;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            margin-bottom: 1rem;
            color: #333;
        }

        .project-content p {
            color: #666;
            margin-bottom: 1rem;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-link {
            color: #667eea;
            text-decoration: none;
            font-weight: bold;
            padding: 0.5rem 1rem;
            border: 2px solid #667eea;
            border-radius: 25px;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            background: #667eea;
            color: white;
        }

        /* Contact Section */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: start;
        }

        .contact-info {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2rem;
            border-radius: 15px;
        }

        .contact-info h3 {
            margin-bottom: 1rem;
        }

        .contact-item {
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .contact-form {
            background: #f8f9fa;
            padding: 2rem;
            border-radius: 15px;
        }

        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #333;
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
        }

        .submit-btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
        }

        /* Footer */
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 2rem 0;
            margin-top: 2rem;
        }

        /* Animations */
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

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .contact-content {
                grid-template-columns: 1fr;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <a href="#" class="logo">Lubnan Bin Ashraf</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Lubnan Bin Ashraf</h1>
            <p>Full Stack Developer & Creative Problem Solver</p>
            <a href="#about" class="cta-button">Discover My Work</a>
        </div>
    </section>

    <div class="container">
        <section id="about">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-image">
                    👨‍💻
                </div>
                <div class="about-text">
                    <p>Hello! I'm Lubnan Bin Ashraf, a passionate full-stack developer with a love for creating innovative digital solutions. I specialize in building responsive web applications and have experience working with modern technologies.</p>
                    <p>My journey in software development began with a curiosity about how things work behind the scenes. Today, I combine technical expertise with creative problem-solving to deliver exceptional user experiences.</p>
                    <p>When I'm not coding, you can find me exploring new technologies, contributing to open-source projects, or sharing knowledge with the developer community.</p>
                </div>
            </div>
        </section>

        <section id="skills">
            <h2 class="section-title">Skills & Expertise</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-icon">💻</div>
                    <h3>Frontend Development</h3>
                    <p>HTML, CSS, JavaScript, React, Vue.js, responsive design, and modern UI frameworks</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">⚙️</div>
                    <h3>Backend Development</h3>
                    <p>Node.js, Python, PHP, database design, API development, and server management</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🎨</div>
                    <h3>UI/UX Design</h3>
                    <p>User interface design, user experience optimization, prototyping, and design systems</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🚀</div>
                    <h3>DevOps & Deployment</h3>
                    <p>Git, CI/CD, cloud platforms, containerization, and automated testing</p>
                </div>
            </div>
        </section>

        <section id="projects">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">🌐</div>
                    <div class="project-content">
                        <h3>E-Commerce Platform</h3>
                        <p>A full-featured online shopping platform with user authentication, payment integration, and admin dashboard.</p>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">📱</div>
                    <div class="project-content">
                        <h3>Task Management App</h3>
                        <p>A responsive task management application with real-time updates and collaborative features.</p>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">📊</div>
                    <div class="project-content">
                        <h3>Data Visualization Dashboard</h3>
                        <p>An interactive dashboard for data visualization with charts, graphs, and real-time analytics.</p>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Let's Connect!</h3>
                    <div class="contact-item">
                        <span>📧</span>
                        <span>lubnan.ashraf@email.com</span>
                    </div>
                    <div class="contact-item">
                        <span>📱</span>
                        <span>+880 XXX-XXX-XXXX</span>
                    </div>
                    <div class="contact-item">
                        <span>📍</span>
                        <span>Dhaka, Bangladesh</span>
                    </div>
                    <div class="contact-item">
                        <span>🌐</span>
                        <span>github.com/lubnanbinashraf</span>
                    </div>
                </div>
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Send Message</button>
                </form>
            </div>
        </section>
    </div>

    <footer>
        <div class="container">
            <p>&copy; 2025 Lubnan Bin Ashraf. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add scroll effect to header
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.backdropFilter = 'blur(20px)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.1)';
                header.style.backdropFilter = 'blur(10px)';
            }
        });

        // Form submission
        document.querySelector('.contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for your message! I\'ll get back to you soon.');
            this.reset();
        });

        // Add animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe all sections
        document.querySelectorAll('section').forEach(section => {
            section.style.opacity = '0';
            section.style.transform = 'translateY(20px)';
            section.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(section);
        });
    </script>
</body>
</html>
