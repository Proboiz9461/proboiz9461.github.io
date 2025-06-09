<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Shaurya's Cool Creations</title>
    <style>
        :root {
            --bg-color: #1f1c2c;
            --text-color: #fff;
            --section-bg: rgba(255, 255, 255, 0.1);
            --accent-color: #ff4081;
        }

        body.light {
            --bg-color: #f9f9f9;
            --text-color: #000;
            --section-bg: rgba(0, 0, 0, 0.05);
            --accent-color: #6200ea;
        }

        body {
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: var(--bg-color);
            color: var(--text-color);
            display: flex;
            transition: background 0.5s, color 0.5s;
        }

        .sidebar {
            width: 220px;
            background: rgba(0, 0, 0, 0.5);
            padding: 1rem;
            position: fixed;
            height: 100%;
            overflow-y: auto;
            transition: transform 0.3s ease-in-out;
        }

        .sidebar h2 {
            color: var(--accent-color);
            font-size: 1.5rem;
            text-align: center;
            margin-bottom: 1rem;
        }

        .sidebar a {
            display: block;
            padding: 0.7rem;
            color: var(--text-color);
            text-decoration: none;
            border-radius: 5px;
            margin-bottom: 0.5rem;
            transition: background 0.3s;
        }

        .sidebar a:hover {
            background: var(--accent-color);
            color: #fff;
        }

        .content {
            margin-left: 240px;
            padding: 2rem;
            width: 100%;
            box-sizing: border-box;
        }

        header {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 1rem;
            text-align: center;
        }

        .section {
            margin-bottom: 2rem;
            border-radius: 10px;
            padding: 1rem;
            background: var(--section-bg);
            border: 2px solid var(--text-color);
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s forwards;
        }

        .section:nth-child(even) {
            animation-delay: 0.2s;
        }

        .section h2 {
            margin-top: 0;
            font-size: 2rem;
            color: var(--accent-color);
        }

        .section a {
            display: inline-block;
            margin: 0.5rem;
            padding: 0.5rem 1rem;
            background: var(--text-color);
            color: var(--bg-color);
            text-decoration: none;
            border-radius: 5px;
            transition: transform 0.3s ease, background 0.3s, color 0.3s;
        }

        .section a:hover {
            transform: scale(1.1);
            background: var(--accent-color);
            color: #fff;
        }

        footer {
            text-align: center;
            padding: 1rem;
            margin-top: 2rem;
            border-top: 1px solid var(--text-color);
            font-size: 1rem;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .toggle-btn {
            position: fixed;
            top: 10px;
            right: 10px;
            padding: 0.5rem 1rem;
            background: var(--accent-color);
            border: none;
            color: #fff;
            font-size: 1rem;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s;
            z-index: 999;
        }

        .toggle-btn:hover {
            background: #ff79a8;
        }

        @media (max-width: 768px) {
            .sidebar {
                transform: translateX(-240px);
            }

            .sidebar.show {
                transform: translateX(0);
            }

            .content {
                margin-left: 0;
                padding: 1rem;
            }

            .toggle-sidebar-btn {
                display: block;
                position: fixed;
                top: 10px;
                left: 10px;
                padding: 0.5rem 1rem;
                background: var(--accent-color);
                border: none;
                color: #fff;
                font-size: 1rem;
                border-radius: 5px;
                cursor: pointer;
                z-index: 1000;
            }
        }

        .toggle-sidebar-btn {
            display: none;
        }
    </style>
</head>
<body class="dark">

    <!-- Sidebar -->
    <div class="sidebar" id="sidebar">
        <h2>Shaurya</h2>
        <a href="#games">Games</a>
        <a href="#wallpapers">Wallpapers</a>
        <a href="#music">Music</a>
        <a href="#projects">Coding Projects</a>
        <a href="#about">About</a>
    </div>

    <!-- Sidebar toggle button (for mobile) -->
    <button class="toggle-sidebar-btn" onclick="toggleSidebar()">☰ Menu</button>

    <!-- Dark mode toggle button -->
    <button class="toggle-btn" onclick="toggleDarkMode()">Toggle Dark Mode</button>

    <!-- Main content -->
    <div class="content">
        <header>Shaurya's Cool Creations 🚀</header>

        <div class="section" id="games">
            <h2>Games</h2>
            <a href="file:///C:/Users/ASUS/Documents/GitHub/flappy%20bird.html" target="_blank">Flappy Bird Game</a>
            <!-- Add more games here -->
        </div>

        <div class="section" id="wallpapers">
            <h2>Wallpapers</h2>
            <a href="https://images.wallpapersden.com/image/download/batman-4k-cool_bWVrbm6UmZqaraWkpJRmbmdlrWZlbWU.jpg" target="_blank">Wallpaper Gallery</a>
        </div>

        <div class="section" id="music">
            <h2>Music</h2>
            <a href="https://www.youtube.com/watch?v=qiFk9GYZL5s" target="_blank">My First Track</a>
        </div>

        <div class="section" id="projects">
            <h2>Coding Projects</h2>
            <a href="#" target="_blank">Coming Soon</a>
        </div>

        <div class="section" id="about">
            <h2>About Me</h2>
            <p>Hi, I'm Shaurya Chauhan! I love making games, music, wallpapers, and cool coding projects. Stay tuned for more 🚀.</p>
        </div>

        <footer>
            © 2025 Shaurya Chauhan | SH Open Coders
        </footer>
    </div>

    <!-- JavaScript -->
    <script>
        function toggleDarkMode() {
            document.body.classList.toggle('light');
        }

        function toggleSidebar() {
            document.getElementById('sidebar').classList.toggle('show');
        }
    </script>

</body>
</html>
