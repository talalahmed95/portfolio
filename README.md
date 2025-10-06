<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Talal Ahmed | Data Engineer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary: #64748b;
            --dark: #1e293b;
            --light: #f8fafc;
            --accent: #0ea5e9;
            --gray: #94a3b8;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            background-color: var(--light);
            overflow-x: hidden;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header & Navigation */
        header {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
        }

        header.scrolled {
            padding: 10px 0;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--primary);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            padding: 180px 0 120px;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 500px;
            height: 500px;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(37, 99, 235, 0.1) 0%, rgba(14, 165, 233, 0.1) 100%);
            top: -250px;
            right: -100px;
        }

        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .hero-text {
            flex: 1;
            max-width: 600px;
        }

        .hero-image {
            flex: 1;
            text-align: center;
        }

        .hero-image img {
            max-width: 100%;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero h1 span {
            color: var(--primary);
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--secondary);
            margin-bottom: 30px;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--primary);
            color: white;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
            margin-left: 15px;
        }

        .btn-outline:hover {
            background-color: var(--primary);
            color: white;
        }

        /* Skills Section */
        .section {
            padding: 100px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-title h2 {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            width: 70px;
            height: 4px;
            background-color: var(--primary);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        .section-title p {
            color: var(--secondary);
            max-width: 600px;
            margin: 0 auto;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-card {
            background-color: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
            text-align: center;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.1);
        }

        .skill-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .skill-card p {
            color: var(--secondary);
        }

        /* Experience Section */
        .experience {
            background-color: #f1f5f9;
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            width: 4px;
            background-color: var(--primary);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
        }

        .timeline-item {
            padding: 20px 40px;
            position: relative;
            width: 50%;
            box-sizing: border-box;
        }

        .timeline-item:nth-child(odd) {
            left: 0;
        }

        .timeline-item:nth-child(even) {
            left: 50%;
        }

        .timeline-content {
            padding: 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .timeline-content h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .timeline-content .date {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 10px;
            display: block;
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: white;
            border: 4px solid var(--primary);
            border-radius: 50%;
            top: 30px;
            right: -10px;
        }

        .timeline-item:nth-child(even)::after {
            left: -10px;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.1);
        }

        .project-image {
            height: 200px;
            background-color: #e2e8f0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 3rem;
        }

        .project-content {
            padding: 25px;
        }

        .project-content h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .project-content p {
            color: var(--secondary);
            margin-bottom: 20px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 20px;
        }

        .project-tag {
            background-color: #e0f2fe;
            color: var(--primary);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* Contact Section */
        .contact {
            background-color: var(--dark);
            color: white;
        }

        .contact .section-title h2 {
            color: white;
        }

        .contact .section-title p {
            color: var(--gray);
        }

        .contact-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
        }

        .contact-info {
            flex: 1;
            min-width: 300px;
        }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
        }

        .contact-info p {
            color: var(--gray);
            margin-bottom: 30px;
        }

        .contact-details {
            margin-bottom: 30px;
        }

        .contact-detail {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
        }

        .contact-detail i {
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            color: var(--accent);
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-link {
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-link:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }

        .contact-form {
            flex: 1;
            min-width: 300px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: none;
            border-radius: 5px;
            background-color: rgba(255, 255, 255, 0.1);
            color: white;
            font-family: 'Inter', sans-serif;
        }

        .form-control::placeholder {
            color: var(--gray);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: #0f172a;
            color: var(--gray);
            padding: 40px 0;
            text-align: center;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .footer-logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: white;
            text-decoration: none;
        }

        .footer-links {
            display: flex;
            list-style: none;
            gap: 20px;
        }

        .footer-links a {
            color: var(--gray);
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: white;
        }

        .copyright {
            margin-top: 20px;
            width: 100%;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-text {
                margin-bottom: 50px;
            }
            
            .timeline::before {
                left: 31px;
            }
            
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            
            .timeline-item:nth-child(even) {
                left: 0;
            }
            
            .timeline-item::after {
                left: 21px;
            }
            
            .timeline-item:nth-child(even)::after {
                left: 21px;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .mobile-menu {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.3rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .footer-content {
                flex-direction: column;
                text-align: center;
            }
            
            .footer-links {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header id="header">
        <div class="container">
            <nav class="navbar">
                <a href="#" class="logo">Talal Ahmed</a>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#experience">Experience</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="mobile-menu">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Data Engineer & BI Specialist</h1>
                    <h1>Expert in <span>SQL Server & Power BI</span></h1>
                    <p>I design, build, and optimize data solutions that transform raw information into actionable insights. With expertise across the Microsoft data platform, I create robust ETL processes, data models, and interactive visualizations.</p>
                    <div class="hero-buttons">
                        <a href="#projects" class="btn">View My Work</a>
                        <a href="#contact" class="btn btn-outline">Get In Touch</a>
                    </div>
                </div>
                <div class="hero-image">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1170&q=80" alt="Data Visualization">
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="section" id="skills">
        <div class="container">
            <div class="section-title">
                <h2>Technical Expertise</h2>
                <p>Specialized in the Microsoft Data Platform with comprehensive experience across the entire data lifecycle</p>
            </div>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-database"></i>
                    </div>
                    <h3>SQL Server</h3>
                    <p>Database design, optimization, T-SQL development, performance tuning, and administration of SQL Server environments.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-cube"></i>
                    </div>
                    <h3>SSAS & Data Modeling</h3>
                    <p>Designing and implementing multidimensional and tabular models for efficient analytical processing.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-chart-bar"></i>
                    </div>
                    <h3>SSRS & Power BI</h3>
                    <p>Creating interactive reports, dashboards, and data visualizations that drive business decisions.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-exchange-alt"></i>
                    </div>
                    <h3>SSIS & ETL</h3>
                    <p>Building robust data integration solutions, data warehousing, and automated ETL processes.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-cloud"></i>
                    </div>
                    <h3>Azure Data Services</h3>
                    <p>Implementing cloud-based data solutions using Azure Data Factory, Synapse Analytics, and more.</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3>Data Analytics</h3>
                    <p>Transforming complex datasets into actionable insights through advanced analytics and visualization.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section class="section experience" id="experience">
        <div class="container">
            <div class="section-title">
                <h2>Professional Experience</h2>
                <p>Proven track record of delivering data solutions across various industries and business domains</p>
            </div>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="date">2021 - Present</span>
                        <h3>Senior Data Engineer</h3>
                        <p>Leading the design and implementation of enterprise data warehouse solutions, optimizing ETL processes, and developing interactive Power BI dashboards for executive reporting.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="date">2018 - 2021</span>
                        <h3>BI Developer</h3>
                        <p>Developed and maintained SSAS tabular models, created complex SSRS reports, and implemented data integration solutions using SSIS for multiple business units.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="date">2016 - 2018</span>
                        <h3>Data Analyst</h3>
                        <p>Performed data analysis, created reporting solutions, and supported database management activities while developing expertise in T-SQL and data visualization.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-content">
                        <span class="date">2014 - 2016</span>
                        <h3>Database Administrator</h3>
                        <p>Managed SQL Server instances, performed backups and recovery, optimized query performance, and ensured database security and availability.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="section" id="projects">
        <div class="container">
            <div class="section-title">
                <h2>Featured Projects</h2>
                <p>Real-world data solutions that demonstrate technical expertise and business impact</p>
            </div>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-warehouse"></i>
                    </div>
                    <div class="project-content">
                        <h3>Enterprise Data Warehouse</h3>
                        <p>Designed and implemented a comprehensive data warehouse solution integrating data from 10+ source systems using SSIS, with a tabular model in SSAS for analytics.</p>
                        <div class="project-tags">
                            <span class="project-tag">SQL Server</span>
                            <span class="project-tag">SSIS</span>
                            <span class="project-tag">SSAS</span>
                            <span class="project-tag">Data Modeling</span>
                        </div>
                        <a href="#" class="btn">View Details</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-chart-pie"></i>
                    </div>
                    <div class="project-content">
                        <h3>Executive Dashboard</h3>
                        <p>Developed an interactive Power BI dashboard for C-level executives providing real-time insights into sales performance, operational metrics, and financial KPIs.</p>
                        <div class="project-tags">
                            <span class="project-tag">Power BI</span>
                            <span class="project-tag">DAX</span>
                            <span class="project-tag">Data Visualization</span>
                        </div>
                        <a href="#" class="btn">View Details</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-sync-alt"></i>
                    </div>
                    <div class="project-content">
                        <h3>Automated ETL Pipeline</h3>
                        <p>Built a scalable ETL solution using SSIS that processes millions of records daily, with automated error handling, logging, and performance monitoring.</p>
                        <div class="project-tags">
                            <span class="project-tag">SSIS</span>
                            <span class="project-tag">ETL</span>
                            <span class="project-tag">Automation</span>
                            <span class="project-tag">SQL Server</span>
                        </div>
                        <a href="#" class="btn">View Details</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section contact" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Get In Touch</h2>
                <p>Ready to discuss your data engineering needs? Let's connect and explore how I can help transform your data into value.</p>
            </div>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Let's Talk About Your Project</h3>
                    <p>I'm currently available for freelance projects or full-time opportunities. Feel free to reach out if you're looking for a data engineer who can deliver robust, scalable solutions.</p>
                    <div class="contact-details">
                        <div class="contact-detail">
                            <i class="fas fa-envelope"></i>
                            <span>talal.ahmed@example.com</span>
                        </div>
                        <div class="contact-detail">
                            <i class="fas fa-phone"></i>
                            <span>+1 (555) 123-4567</span>
                        </div>
                        <div class="contact-detail">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>New York, NY</span>
                        </div>
                    </div>
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" class="form-control" placeholder="Your Name">
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" class="form-control" placeholder="Your Email">
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" class="form-control" placeholder="Subject">
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" class="form-control" placeholder="Your Message"></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <a href="#" class="footer-logo">Talal Ahmed</a>
                <ul class="footer-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#experience">Experience</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="copyright">
                    <p>&copy; 2023 Talal Ahmed. All rights reserved.</p>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Mobile menu toggle
        const mobileMenu = document.querySelector('.mobile-menu');
        const navLinks = document.querySelector('.nav-links');

        mobileMenu.addEventListener('click', function() {
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu if open
                    if (window.innerWidth <= 768) {
                        navLinks.style.display = 'none';
                    }
                }
            });
        });
    </script>
</body>
</html>
