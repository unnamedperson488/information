---
title: My Site
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Site</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&family=Source+Code+Pro&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --bg: #0a0a0a;
            --text: #e0e0e0;
            --accent: #00ff9f;
            --secondary: #1a1a1a;
            --terminal-bg: #000000;
            --terminal-text: #00ff00;
            --gradient: linear-gradient(to left, #f7ba2b 0%, #ea5358 100%);
            --hero-gradient: linear-gradient(135deg, #00ff9f 0%, #ea5358 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: var(--secondary);
            display: flex;
            justify-content: center;
            padding: 1.5rem;
            z-index: 10;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.6);
        }

        nav button {
            background-color: transparent;
            color: var(--text);
            border: 2px solid var(--accent);
            padding: 0.75rem 1.5rem;
            margin: 0 1rem;
            cursor: pointer;
            transition: all 0.4s ease;
            border-radius: 8px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        nav button:hover {
            background-color: var(--accent);
            color: var(--bg);
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 255, 159, 0.4);
        }

        section {
            padding: 8rem 2rem 4rem;
            max-width: 1200px;
            margin: 0 auto;
            opacity: 0;
            transition: opacity 0.6s ease-in-out;
            display: none;
        }

        section.active {
            opacity: 1;
            display: block;
        }

        h1, h2 {
            font-weight: 700;
            margin-bottom: 1.5rem;
            letter-spacing: 1px;
            text-align: center;
        }

        h1.animated {
            animation: fadeInDown 1.2s ease;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        p {
            margin-bottom: 1rem;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            text-align: center;
        }

        .home-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4rem;
        }

        .hero {
            background: var(--hero-gradient);
            padding: 4rem 2rem;
            border-radius: 20px;
            text-align: center;
            max-width: 1000px;
            box-shadow: 0 10px 30px rgba(0, 255, 159, 0.3);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.02); }
            100% { transform: scale(1); }
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
        }

        .cta-button {
            background-color: var(--accent);
            color: var(--bg);
            border: none;
            padding: 1rem 2rem;
            cursor: pointer;
            transition: all 0.4s ease;
            border-radius: 8px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 2rem;
            display: inline-block;
            text-decoration: none;
        }

        .cta-button:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(0, 255, 159, 0.4);
        }

        .intro-text {
            max-width: 900px;
            text-align: center;
        }

        .intro-text p {
            margin-bottom: 1.5rem;
        }

        .placeholders {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
            width: 100%;
        }

        .placeholder-card {
            background-color: var(--secondary);
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .placeholder-card:hover {
            transform: translateY(-10px);
        }

        .placeholder-card h3 {
            margin-bottom: 1rem;
            color: var(--accent);
        }

        .features-list {
            max-width: 800px;
            margin: 2rem auto;
            text-align: left;
        }

        .features-list ul {
            list-style: none;
        }

        .features-list li {
            margin-bottom: 1rem;
            padding-left: 2rem;
            position: relative;
        }

        .features-list li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: var(--accent);
        }

        .testimonials {
            max-width: 1000px;
            margin: 3rem auto;
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .testimonial-card {
            background-color: var(--secondary);
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
            text-align: center;
        }

        .testimonial-card p {
            font-style: italic;
        }

        .testimonial-card .author {
            margin-top: 1rem;
            font-weight: 700;
            color: var(--accent);
        }

        .socials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1000px;
            margin: 2rem auto;
        }

        .social-card {
            --background: var(--gradient);
            width: 100%;
            height: 280px;
            padding: 5px;
            border-radius: 1rem;
            overflow: visible;
            background: var(--background);
            position: relative;
            z-index: 1;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.5);
        }

        .social-card::after {
            position: absolute;
            content: "";
            top: 30px;
            left: 0;
            right: 0;
            z-index: -1;
            height: 100%;
            width: 100%;
            transform: scale(0.8);
            filter: blur(25px);
            background: var(--background);
            transition: opacity .5s;
        }

        .social-card .content {
            --color: #181818;
            background: var(--color);
            color: var(--text);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            width: 100%;
            height: 100%;
            overflow: visible;
            border-radius: .7rem;
            padding: 1rem;
        }

        .social-card .title {
            font-weight: bold;
            letter-spacing: .1em;
            color: var(--text);
            text-align: center;
        }

        .social-card .sci {
            display: flex;
            list-style: none;
            gap: 1.5rem;
            margin-top: 1rem;
        }

        .social-card .sci li a {
            color: var(--text);
            transition: color 0.3s, transform 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .social-card .sci li a:hover {
            color: var(--accent);
            transform: scale(1.2);
        }

        .social-card:hover::after {
            opacity: 0;
        }

        .social-card:hover .content {
            color: #f7ba2b;
            transition: color 1s;
        }

        .social-desc {
            margin-top: 1rem;
            text-align: center;
        }

        .community-links {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2.5rem;
            max-width: 700px;
            margin: 0 auto;
        }

        .community-desc {
            text-align: center;
            margin: 2rem 0;
            max-width: 800px;
        }

        .discord-container {
            width: 100%;
            position: relative;
        }

        .discord-button {
            background-color: var(--secondary);
            color: var(--text);
            border: 2px solid var(--accent);
            padding: 1.2rem 2.5rem;
            cursor: pointer;
            transition: all 0.4s ease;
            border-radius: 10px;
            font-weight: 700;
            text-align: center;
            width: 100%;
            display: block;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }

        .discord-button:hover {
            background-color: var(--accent);
            color: var(--bg);
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 255, 159, 0.5);
        }

        .dropdown {
            display: none;
            background-color: var(--terminal-bg);
            color: var(--terminal-text);
            padding: 2rem;
            border: 1px solid var(--accent);
            border-radius: 0 0 10px 10px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5);
            font-family: 'Source Code Pro', monospace;
            font-size: 1rem;
            line-height: 1.5;
            margin-top: -1px;
        }

        .discord-container:hover .dropdown {
            display: block;
        }

        .dropdown p {
            margin-bottom: 1rem;
            color: var(--accent);
        }

        .dropdown ul {
            list-style: none;
            margin-bottom: 1.5rem;
        }

        .dropdown li::before {
            content: '$ ';
            color: var(--accent);
            margin-right: 0.5rem;
        }

        .join-button {
            background-color: var(--accent);
            color: var(--bg);
            border: none;
            padding: 1.2rem 2.5rem;
            cursor: pointer;
            transition: all 0.4s ease;
            border-radius: 10px;
            font-weight: 700;
            text-align: center;
            width: 100%;
            display: block;
            text-decoration: none;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }

        .join-button:hover {
            background-color: var(--text);
            color: var(--accent);
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0, 255, 159, 0.5);
        }

        .support-section p {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 1.1rem;
        }

        .support-buttons {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 2.5rem;
            max-width: 900px;
            margin: 0 auto;
        }

        .support-buttons a {
            text-decoration: none;
        }

        .support-buttons button {
            background-color: var(--secondary);
            color: var(--text);
            border: 2px solid var(--accent);
            padding: 1.2rem 2.5rem;
            cursor: pointer;
            transition: all 0.4s ease;
            border-radius: 10px;
            font-weight: 700;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }

        .support-buttons button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 25px var(--accent);
            background-color: var(--accent);
            color: var(--bg);
        }

        @media (max-width: 768px) {
            nav {
                flex-wrap: wrap;
                padding: 1rem;
            }

            nav button {
                margin: 0.5rem;
                padding: 0.5rem 1rem;
            }

            section {
                padding: 6rem 1rem 2rem;
            }

            .socials-grid {
                grid-template-columns: 1fr;
            }

            .placeholders {
                grid-template-columns: 1fr;
            }

            .support-buttons {
                grid-template-columns: 1fr;
            }
        }

        /* Additional Uiverse.io Component: Example Neon Button for Navigation */
        .neon-button {
            background-color: transparent;
            color: var(--text);
            border: 2px solid var(--accent);
            padding: 0.75rem 1.5rem;
            margin: 0 1rem;
            cursor: pointer;
            transition: all 0.4s ease;
            border-radius: 8px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 0 10px var(--accent);
        }

        .neon-button:hover {
            box-shadow: 0 0 20px var(--accent), 0 0 30px var(--accent);
            transform: translateY(-5px);
        }
    </style>
</head>
<body>
    <nav>
        <button class="neon-button" onclick="showSection('home')">Home</button>
        <button class="neon-button" onclick="showSection('socials')">Socials</button>
        <button class="neon-button" onclick="showSection('community')">Community</button>
        <button class="neon-button" onclick="showSection('support')">Support</button>
    </nav>

    <section id="home" class="active">
        <div class="home-content">
            <div class="hero">
                <h1 class="animated">Welcome to My Site</h1>
                <p>Discover a vibrant digital space dedicated to creativity, community, and connection. Join us in exploring innovative ideas and sharing experiences.</p>
                <a href="#socials" class="cta-button" onclick="showSection('socials')">Connect Now</a>
            </div>
            <div class="intro-text">
                <p>A clean, modern hub for connecting, sharing, and supporting in a digital world. Whether you're here for discussions, content creation, or just to connect, we've got something for everyone.</p>
                <p>Our platform is built with passion and designed to foster meaningful interactions and growth. We offer a variety of resources, events, and opportunities to engage with like-minded individuals.</p>
                <p>Explore our latest projects, join ongoing discussions, and contribute to our ever-growing community. With regular updates and user feedback, we strive to make this space better every day.</p>
            </div>
            <div class="features-list">
                <h2>Key Features</h2>
                <ul>
                    <li>Engaging community discussions and events with real-time interaction</li>
                    <li>Exclusive content on social platforms including tutorials and live streams</li>
                    <li>Multiple ways to support and contribute to our ongoing projects</li>
                    <li>Modern, responsive design optimized for all devices and browsers</li>
                    <li>Regular updates, new features, and community-driven improvements</li>
                    <li>Secure and private environment for sharing ideas and collaborations</li>
                </ul>
            </div>
            <div class="placeholders">
                <div class="placeholder-card">
                    <h3>About Us</h3>
                    <p>Detailed placeholder information about the site, its mission, vision for the future, and the team behind it.</p>
                </div>
                <div class="placeholder-card">
                    <h3>Latest Updates</h3>
                    <p>Placeholder for recent news, updates, announcements, and changelog to keep you informed.</p>
                </div>
                <div class="placeholder-card">
                    <h3>Featured Content</h3>
                    <p>Placeholder for highlighted features, videos, articles, or user-generated content curated just for you.</p>
                </div>
                <div class="placeholder-card">
                    <h3>Upcoming Events</h3>
                    <p>Placeholder for future events, webinars, community meetups, and special occasions.</p>
                </div>
                <div class="placeholder-card">
                    <h3>Our Partners</h3>
                    <p>Placeholder for information about our collaborators, sponsors, and partner organizations.</p>
                </div>
                <div class="placeholder-card">
                    <h3>Get Involved</h3>
                    <p>Placeholder for ways to contribute, volunteer, or participate in our community initiatives.</p>
                </div>
            </div>
            <div class="testimonials">
                <h2>What Our Community Says</h2>
                <div class="testimonial-card">
                    <p>"This site has transformed how I connect with like-minded individuals. Highly recommended!"</p>
                    <div class="author">- Community Member A</div>
                </div>
                <div class="testimonial-card">
                    <p>"Amazing content and supportive community. I've learned so much here."</p>
                    <div class="author">- Community Member B</div>
                </div>
                <div class="testimonial-card">
                    <p>"The best place for creative sharing and inspiration."</p>
                    <div class="author">- Community Member C</div>
                </div>
            </div>
        </div>
    </section>

    <section id="socials">
        <h2>Socials</h2>
        <div class="socials-grid">
            <div class="social-card">
                <div class="content">
                    <p class="title">Instagram</p>
                    <p class="social-desc">Follow us on Instagram for daily updates, behind-the-scenes content, and visual inspirations. Join our growing community of creators.</p>
                    <ul class="sci">
                        <li>
                            <a href="https://instagram.com/unnamedperson488" target="_blank">
                                <i class="fab fa-instagram fa-2x"></i>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="social-card">
                <div class="content">
                    <p class="title">TikTok</p>
                    <p class="social-desc">Check out our TikTok for short, engaging videos, tutorials, and fun challenges. Don't miss out on the latest trends!</p>
                    <ul class="sci">
                        <li>
                            <a href="https://tiktok.com/@unnamedperson488" target="_blank">
                                <i class="fab fa-tiktok fa-2x"></i>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="social-card">
                <div class="content">
                    <p class="title">YouTube</p>
                    <p class="social-desc">Subscribe to our YouTube channel for in-depth videos, live streams, and comprehensive guides on various topics.</p>
                    <ul class="sci">
                        <li>
                            <a href="https://youtube.com/@unnamedperson488" target="_blank">
                                <i class="fab fa-youtube fa-2x"></i>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="social-card">
                <div class="content">
                    <p class="title">Discord</p>
                    <p class="social-desc">Join our Discord for real-time chats, voice calls, and community events. Connect with others in a dynamic environment.</p>
                    <ul class="sci">
                        <li>
                            <a href="https://discord.com/users/unnamedperson" target="_blank">
                                <i class="fab fa-discord fa-2x"></i>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <section id="community">
        <h2>Community</h2>
        <p class="community-desc">Our community is a vibrant place for discussions, collaborations, and events. Join one of our Discord servers or visit vacban.wtf for more. We host regular giveaways, gaming sessions, and creative workshops to keep things exciting.</p>
        <div class="community-links">
            <a href="https://vacban.wtf" target="_blank"><button class="discord-button">Visit vacban.wtf</button></a>
            <div class="discord-container">
                <button class="discord-button">TheInnerMinds</button>
                <div class="dropdown">
                    <p>Features:</p>
                    <ul>
                        <li>Active discussions</li>
                        <li>Events and giveaways</li>
                        <li>Support channels</li>
                        <li>Exclusive member roles</li>
                        <li>Voice chat rooms</li>
                    </ul>
                    <a href="https://discord.gg/server1" target="_blank" class="join-button">Join TheInnerMinds</a>
                </div>
            </div>
            <div class="discord-container">
                <button class="discord-button">EuroThrottle TECHHAULS</button>
                <div class="dropdown">
                    <p>Features:</p>
                    <ul>
                        <li>Gaming sessions</li>
                        <li>Creative sharing</li>
                        <li>Moderated chats</li>
                        <li>Tech reviews</li>
                        <li>Haul unboxings</li>
                    </ul>
                    <a href="https://discord.gg/server2" target="_blank" class="join-button">Join EuroThrottle TECHHAULS</a>
                </div>
            </div>
            <div class="discord-container">
                <button class="discord-button">Additional Server 1</button>
                <div class="dropdown">
                    <p>Features:</p>
                    <ul>
                        <li>Community building</li>
                        <li>Collaboration projects</li>
                        <li>Feedback channels</li>
                    </ul>
                    <a href="https://discord.gg/server3" target="_blank" class="join-button">Join Additional Server 1</a>
                </div>
            </div>
        </div>
    </section>

    <section id="support" class="support-section">
        <h2>Support</h2>
        <p>Help sustain our community and content creation by contributing through your preferred method. Your support enables us to host events, create more content, maintain our platforms, and expand our reach. We accept one-time donations via the following methods. Every contribution, big or small, makes a huge difference and is greatly appreciated! If you have questions or want to contribute in other ways, reach out via our community channels.</p>
        <div class="support-buttons">
            <a href="https://paypal.me/your" target="_blank"><button><i class="fab fa-paypal"></i> PayPal</button></a>
            <a href="https://cash.app/$your" target="_blank"><button><i class="fas fa-dollar-sign"></i> CashApp</button></a>
            <a href="https://venmo.com/your" target="_blank"><button><i class="fas fa-money-bill"></i> Venmo</button></a>
            <a href="https://yourcrypto" target="_blank"><button><i class="fab fa-bitcoin"></i> Crypto</button></a>
        </div>
    </section>

    <script>
        function showSection(id) {
            document.querySelectorAll('section').forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(id).classList.add('active');
        }
    </script>
</body>
</html>
