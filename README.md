<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Portfolio - Full Stack Developer</title>
    <style>
        body {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            padding: 60px 0;
            color: white;
        }

        .profile-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            margin: 0 auto 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: white;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            overflow: hidden;
            position: relative;
        }

        .profile-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
        }

        .profile-image .placeholder {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            height: 100%;
        }

        .header h1 {
            font-size: 3rem;
            margin: 0 0 10px 0;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .header p {
            font-size: 1.3rem;
            opacity: 0.9;
            margin: 0;
        }

        .main-content {
            background: #2d3748;
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            color: #e2e8f0;
        }

        .skills-section {
            margin-bottom: 40px;
        }

        .skills-section h2 {
            color: #81e6d9;
            font-size: 2rem;
            margin-bottom: 30px;
            text-align: center;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
            align-items: start;
        }

        .skill-card {
            background: linear-gradient(135deg, #4a5568 0%, #2d3748 100%);
            color: #e2e8f0;
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transform: translateY(0);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            border: 1px solid #4a5568;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            min-height: 120px;
            align-self: start;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.5);
            background: linear-gradient(135deg, #5a6578 0%, #3d4758 100%);
        }

        .skill-description {
            opacity: 0;
            max-height: 0;
            overflow: hidden;
            transition: opacity 0.3s ease, max-height 0.3s ease, margin-top 0.3s ease;
            margin-top: 0;
            font-size: 0.9rem;
            color: #cbd5e0;
            line-height: 1.4;
        }

        .skill-card.expanded .skill-description {
            opacity: 1;
            max-height: 200px;
            margin-top: 15px;
        }

        .skill-card.expanded {
            background: linear-gradient(135deg, #5a6578 0%, #3d4758 100%);
        }

        .skill-card h3 {
            margin: 0 0 10px 0;
            font-size: 1.3rem;
        }

        .skill-card p {
            margin: 0;
            opacity: 0.9;
        }

        .contact-section {
            text-align: center;
            padding: 40px 0;
        }

        .contact-section h2 {
            color: #81e6d9;
            font-size: 2rem;
            margin-bottom: 20px;
        }

        .whatsapp-button {
            display: inline-flex;
            align-items: center;
            gap: 15px;
            background: #25D366;
            color: white;
            padding: 20px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-size: 1.2rem;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(37, 211, 102, 0.3);
            margin: 20px 0;
        }

        .whatsapp-button:hover {
            background: #128C7E;
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(37, 211, 102, 0.4);
        }

        .whatsapp-icon {
            width: 30px;
            height: 30px;
            fill: currentColor;
        }

        .about-section {
            background: linear-gradient(135deg, #4a5568 0%, #2d3748 100%);
            padding: 40px;
            border-radius: 15px;
            margin-bottom: 40px;
            border: 1px solid #4a5568;
        }

        .about-section h2 {
            color: #81e6d9;
            font-size: 2rem;
            margin-bottom: 20px;
            text-align: center;
        }

        .about-section p {
            font-size: 1.1rem;
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
            color: #cbd5e0;
        }

        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }

            .header h1 {
                font-size: 2rem;
            }

            .header p {
                font-size: 1.1rem;
            }

            .main-content {
                padding: 20px;
                margin: 20px 0;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .whatsapp-button {
                padding: 15px 30px;
                font-size: 1rem;
            }

            .profile-image {
                width: 120px;
                height: 120px;
                font-size: 50px;
            }
        }

        @media (max-width: 480px) {
            .header {
                padding: 40px 0;
            }

            .header h1 {
                font-size: 1.8rem;
            }

            .about-section, .main-content {
                padding: 15px;
            }

            .whatsapp-button {
                padding: 12px 25px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="header">
            <div class="profile-image">
                <!-- Replace the URL below with your actual photo URL -->
                <img src="prabha.jpg.png" alt="Prabha Sapkota" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                <div class="placeholder" style="display: none;">👨‍💻</div>
            </div>
            <h1>Prabha Sapkota</h1>
            <p>Full Stack Developer & Programming Enthusiast</p>
        </header>

        <main class="main-content">
            <section class="about-section">
                <h2>About Me</h2>
                <p>
                    I'm a passionate developer with expertise in multiple programming languages and technologies. 
                    I love creating efficient solutions and building amazing applications that make a difference. 
                    Let's connect and discuss your next project!
                </p>
            </section>

            <section class="skills-section">
                <h2>My Skills</h2>
                <div class="skills-grid">
                    <div class="skill-card" onclick="toggleSkillDescription(this)">
                        <h3>🌐 Web Development</h3>
                        <p>HTML, CSS, JavaScript</p>
                        <div class="skill-description">
                            I create responsive, interactive websites using modern HTML5, CSS3, and JavaScript. I can build everything from simple landing pages to complex web applications with smooth animations and user-friendly interfaces.
                        </div>
                    </div>
                    <div class="skill-card" onclick="toggleSkillDescription(this)">
                        <h3>🐍 Python</h3>
                        <p>Backend Development & Automation</p>
                        <div class="skill-description">
                            I use Python for web backends, data analysis, automation scripts, and API development. Experienced with frameworks like Django, Flask, and libraries for data processing and machine learning.
                        </div>
                    </div>
                    <div class="skill-card" onclick="toggleSkillDescription(this)">
                        <h3>⚡ C/C++</h3>
                        <p>System Programming & Performance</p>
                        <div class="skill-description">
                            I develop high-performance applications, system-level programs, and embedded software using C/C++. Perfect for projects requiring speed, memory efficiency, and direct hardware interaction.
                        </div>
                    </div>
                    <div class="skill-card" onclick="toggleSkillDescription(this)">
                        <h3>🚀 Problem Solving</h3>
                        <p>Algorithms & Data Structures</p>
                        <div class="skill-description">
                            I excel at breaking down complex problems into manageable solutions. Strong foundation in algorithms, data structures, and optimization techniques to create efficient, scalable code.
                        </div>
                    </div>
                </div>
            </section>

            <section class="contact-section">
                <h2>Let's Work Together!</h2>
                <p>Ready to start your next project? Get in touch with me on WhatsApp!</p>
                
                <a href="https://wa.me/919745387908?text=Hi! I found your portfolio and would like to discuss a project with you." 
                   class="whatsapp-button" 
                   target="_blank" 
                   rel="noopener noreferrer">
                    <svg class="whatsapp-icon" viewBox="0 0 24 24">
                        <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.890-5.335 11.893-11.893A11.821 11.821 0 0020.885 3.488"/>
                    </svg>
                    Contact me on WhatsApp
                </a>
                
                <p style="margin-top: 20px; color: #666; font-size: 0.9rem;">
                    📱 +91 9745387908
                </p>
            </section>
        </main>
    </div>

    <script>
        // Toggle skill description function
        function toggleSkillDescription(card) {
            const isExpanded = card.classList.contains('expanded');
            
            // Close all other expanded cards
            document.querySelectorAll('.skill-card.expanded').forEach(otherCard => {
                if (otherCard !== card) {
                    otherCard.classList.remove('expanded');
                }
            });
            
            // Toggle current card
            if (isExpanded) {
                card.classList.remove('expanded');
            } else {
                card.classList.add('expanded');
            }
        }

        // Add smooth scrolling animation for better UX
        document.addEventListener('DOMContentLoaded', function() {
            // Animate skill cards on scroll
            const skillCards = document.querySelectorAll('.skill-card');
            
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);

            skillCards.forEach(card => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(card);
            });

            // Add click tracking for WhatsApp button
            const whatsappButton = document.querySelector('.whatsapp-button');
            whatsappButton.addEventListener('click', function() {
                console.log('WhatsApp contact initiated');
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'987140aaa13a9e82',t:'MTc1OTIwOTQzMy4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
