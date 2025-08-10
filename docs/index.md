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
            --light-bg: #f0f0f0;
            --light-text: #121212;
            --light-accent: #007f5f;
            --light-secondary: #e0e0e0;
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
            transition: background-color 0.3s, color 0.3s;
        }

        body.light {
            --bg: var(--light-bg);
            --text: var(--light-text);
            --accent: var(--light-accent);
            --secondary: var(--light-secondary);
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
            transition: background-color 0.3s;
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
            transition: color 0.3s;
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
            transition: color 0.3s;
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
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 10%, transparent 40%);
            animation: parallax 10s linear infinite;
        }

        @keyframes parallax {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50%, 50%); }
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
            transition: transform 0.3s ease, background-color 0.3s;
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
            font-size: 1.1rem;
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
            transition: background-color 0.3s;
        }

        .testimonial-card p {
            font-style: italic;
        }

        .testimonial-card .author {
            margin-top: 1rem;
            font-weight: 700;
            color: var(--accent);
        }

        .social-card {
            --background: var(--gradient);
            width: 220px;
            height: 280px;
            padding: 5px;
            border-radius: 1rem;
            overflow: visible;
            background: var(--background);
            position: relative;
            z-index: 1;
            margin: 2rem auto;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.5);
            transition: box-shadow 0.3s;
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
            transition: color 0.3s;
        }

        .social-card .title {
            font-weight: bold;
            letter-spacing: .1em;
            color: var(--text);
            text-align: center;
            margin-bottom: 1rem;
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

        .icons {
            display: flex;
            flex-direction: column;
            gap: 2rem;
            align-items: flex-start;
            max-width: 300px;
            margin: 0 auto 0 4rem;
        }

        .icons a {
            display: flex;
            align-items: center;
            text-decoration: none;
            position: relative;
            transition: all 0.4s ease;
        }

        .icons a .icon-wrapper {
            background-color: var(--secondary);
            color: var(--text);
            padding: 1.5rem;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 80px;
            height: 80px;
            transition: all 0.4s ease;
        }

        .icons a:hover .icon-wrapper {
            transform: scale(1.15);
            box-shadow: 0 0 20px var(--accent);
            color: var(--accent);
        }

        .icons a .info {
            position: absolute;
            left: 100%;
            top: 50%;
            transform: translateY(-50%) translateX(-20px);
            opacity: 0;
            background-color: var(--secondary);
            color: var(--accent);
            padding: 0.5rem 1rem;
            border-radius: 8px;
            white-space: nowrap;
            transition: transform 0.4s ease, opacity 0.4s ease;
            pointer-events: none;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
        }

        .icons a:hover .info {
            transform: translateY(-50%) translateX(0);
            opacity: 1;
        }

        .social-descriptions {
            max-width: 800px;
            margin: 3rem auto;
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .social-desc-card {
            background-color: var(--secondary);
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
            transition: background-color 0.3s;
        }

        .social-desc-card h3 {
            color: var(--accent);
            margin-bottom: 1rem;
        }

        .community-links {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2.5rem;
            max-width: 700px;
            margin: 0 auto;
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
            transition: background-color 0.3s, color 0.3s;
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
            margin: 0 auto 3rem;
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

        .support-tiers {
            max-width: 900px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .tier-card {
            background-color: var(--secondary);
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.4);
            text-align: center;
            transition: background-color 0.3s;
        }

        .tier-card h3 {
            color: var(--accent);
            margin-bottom: 1rem;
        }

        .tier-card ul {
            list-style: none;
            margin-bottom: 1.5rem;
        }

        .tier-card li {
            margin-bottom: 0.5rem;
        }

        .tier-card .cta-button {
            margin-top: 1rem;
        }

        footer {
            background-color: var(--secondary);
            color: var(--text);
            text-align: center;
            padding: 1rem;
            position: relative;
            bottom: 0;
            width: 100%;
            transition: background-color 0.3s, color 0.3s;
        }

        footer a {
            color: var(--accent);
            text-decoration: none;
            margin-left: 1rem;
        }

        footer a:hover {
            text-decoration: underline;
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

            .icons {
                flex-direction: row;
                justify-content: center;
                margin: 0 auto;
                max-width: none;
                flex-wrap: wrap;
            }

            .icons a .icon-wrapper {
                width: 60px;
                height: 60px;
                padding: 1rem;
            }

            .icons a .info {
                left: 50%;
                top: 100%;
                transform: translateX(-50%) translateY(-20px);
            }

            .icons a:hover .info {
                transform: translateX(-50%) translateY(0);
            }

            .support-buttons {
                grid-template-columns: 1fr;
            }

            .placeholders {
                grid-template-columns: 1fr;
            }

            .social-card {
                width: 190px;
                height: 254px;
            }

            .hero {
                padding: 3rem 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .support-tiers {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav>
        <button onclick="showSection('home')">Home</button>
        <button onclick="showSection('socials')">Socials</button>
        <button onclick="showSection('community')">Community</button>
        <button onclick="showSection('support')">Support</button>
        <button id="theme-toggle" onclick="toggleTheme()">Toggle Theme</button>
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
                <p>Our platform is built with passion and designed to foster meaningful interactions and growth.</p>
            </div>
            <div class="social-card">
                <b></b>
                <div class="content">
                    <p class="title">Unnamed Person<br><span>Creative Designer & Developer</span></p>
                    <ul class="sci">
                        <li>
                            <a href="https://facebook.com">
                                <svg class="fa-brands fa-facebook" width="20" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512"><path d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"></path></svg>
                            </a>
                        </li>
                        <li>
                            <a href="https://twitter.com">
                                <svg class="fa-brands fa-twitter" width="24" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                            </a>
                        </li>
                        <li>
                            <a href="https://linkedin.com">
                                <svg class="fa-brands fa-linkedin-in" width="24" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M100.28 448H7.4V148.9h92.88zM53.79 108.1C24.09 108.1 0 83.5 0 53.8a53.79 53.79 0 0 1 107.58 0c0 29.7-24.1 54.3-53.79 54.3zM447.9 448h-92.68V302.4c0-34.7-.7-79.2-48.29-79.2-48.29 0-55.69 37.7-55.69 76.7V448h-92.78V148.9h89.08v40.8h1.3c12.4-23.5 42.69-48.3 87.88-48.3 94 0 111.28 61.9 111.28 142.3V448z"></path></svg>
                            </a>
                        </li>
                        <li>
                            <a href="https://instagram.com/unnamedperson488">
                                <svg class="fa-brands fa-instagram" width="24" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"></path></svg>
                            </a>
                        </li>
                    </ul>
                </div>
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
        <div class="icons">
            <a href="https://instagram.com/unnamedperson488" target="_blank">
                <div class="icon-wrapper"><i class="fab fa-instagram fa-2x"></i></div>
                <span class="info">@unnamedperson488</span>
            </a>
            <a href="https://tiktok.com/@unnamedperson488" target="_blank">
                <div class="icon-wrapper"><i class="fab fa-tiktok fa-2x"></i></div>
                <span class="info">@unnamedperson488</span>
            </a>
            <a href="https://youtube.com/@unnamedperson488" target="_blank">
                <div class="icon-wrapper"><i class="fab fa-youtube fa-2x"></i></div>
                <span class="info">@unnamedperson488</span>
            </a>
            <a href="https://discord.com/users/unnamedperson" target="_blank">
                <div class="icon-wrapper"><i class="fab fa-discord fa-2x"></i></div>
                <span class="info">unnamedperson</span>
            </a>
        </div>
        <div class="social-descriptions">
            <div class="social-desc-card">
                <h3>Instagram</h3>
                <p>Follow us on Instagram for daily updates, behind-the-scenes content, and visual inspirations. Join our growing community of creators.</p>
            </div>
            <div class="social-desc-card">
                <h3>TikTok</h3>
                <p>Check out our TikTok for short, engaging videos, tutorials, and fun challenges. Don't miss out on the latest trends!</p>
            </div>
            <div class="social-desc-card">
                <h3>YouTube</h3>
                <p>Subscribe to our YouTube channel for in-depth videos, live streams, and comprehensive guides on various topics.</p>
            </div>
            <div class="social-desc-card">
                <h3>Discord</h3>
                <p>Join our Discord for real-time chats, voice calls, and community events. Connect with others in a dynamic environment.</p>
            </div>
        </div>
    </section>

    <section id="community">
        <h2>Community</h2>
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
                    </ul>
                    <a href="https://discord.gg/server2" target="_blank" class="join-button">Join EuroThrottle TECHHAULS</a>
                </div>
            </div>
        </div>
    </section>

    <section id="support" class="support-section">
        <h2>Support</h2>
        <p>Help sustain our community and content creation by contributing through your preferred method. Your support enables us to host events, create more content, maintain our platforms, and expand our reach. Every contribution, big or small, makes a huge difference and is greatly appreciated!</p>
        <div class="support-buttons">
            <a href="https://paypal.me/your" target="_blank"><button><i class="fab fa-paypal"></i> PayPal</button></a>
            <a href="https://cash.app/$your" target="_blank"><button><i class="fas fa-dollar-sign"></i> CashApp</button></a>
            <a href="https://venmo.com/your" target="_blank"><button><i class="fas fa-money-bill"></i> Venmo</button></a>
            <a href="https://yourcrypto" target="_blank"><button><i class="fab fa-bitcoin"></i> Crypto</button></a>
        </div>
        <div class="support-tiers">
            <div class="tier-card">
                <h3>Basic Supporter</h3>
                <p>$5/month</p>
                <ul>
                    <li>Access to exclusive updates</li>
                    <li>Supporter badge</li>
                </ul>
                <a href="https://paypal.me/your?amount=5" class="cta-button">Support Now</a>
            </div>
            <div class="tier-card">
                <h3>Premium Supporter</h3>
                <p>$10/month</p>
                <ul>
                    <li>All basic benefits</li>
                    <li>Early access to content</li>
                    <li>Personal shoutout</li>
                </ul>
                <a href="https://paypal.me/your?amount=10" class="cta-button">Support Now</a>
            </div>
            <div class="tier-card">
                <h3>VIP Supporter</h3>
                <p>$20/month</p>
                <ul>
                    <li>All premium benefits</li>
                    <li>Custom role in Discord</li>
                    <li>One-on-one session</li>
                </ul>
                <a href="https://paypal.me/your?amount=20" class="cta-button">Support Now</a>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 My Site. All rights reserved.</p>
        <a href="#home" onclick="showSection('home')">Back to Top</a>
    </footer>

    <script>
        function showSection(id) {
            document.querySelectorAll('section').forEach(section => {
                section.classList.remove('active');
            });
            const target = document.getElementById(id);
            target.classList.add('active');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function toggleTheme() {
            document.body.classList.toggle('light');
            localStorage.setItem('theme', document.body.classList.contains('light') ? 'light' : 'dark');
        }

        // Load theme from localStorage
        if (localStorage.getItem('theme') === 'light') {
            document.body.classList.add('light');
        }
    </script>
</body>
</html>
