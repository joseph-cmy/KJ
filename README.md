<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bush ♻️ Login</title>
    <style>
        /* General Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        /* Login Page Styles */
        body {
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .login-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 300px;
            text-align: center;
        }

        h2 {
            margin-bottom: 20px;
        }

        .input-group {
            margin-bottom: 15px;
            text-align: left;
        }

        .input-group label {
            display: block;
            margin-bottom: 5px;
        }

        .input-group input {
            width: 100%;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .options {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .options label {
            display: flex;
            align-items: center;
        }

        .options a {
            text-decoration: none;
            color: #007bff;
        }

        button {
            width: 100%;
            padding: 10px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0056b3;
        }

        p {
            margin-top: 15px;
        }

        p a {
            text-decoration: none;
            color: #007bff;
        }

        /* Hide Main Content Initially */
        .main-content {
            display: none;
        }
    </style>
</head>
<body>
    <!-- Login Section -->
    <div class="login-container" id="login-section">
        <h2>Login</h2>
        <form id="login-form">
            <div class="input-group">
                <label for="username">Username</label>
                <input type="text" id="username" name="username" required>
            </div>
            <div class="input-group">
                <label for="password">Password</label>
                <input type="password" id="password" name="password" required>
            </div>
            <div class="options">
                <label>
                    <input type="checkbox" name="remember"> Remember me
                </label>
                <a href="#">Forgot password?</a>
            </div>
            <button type="submit">Login</button>
        </form>
        <p>Don't have an account? <a href="#">Register</a></p>
    </div>

    <!-- Main Video Platform -->
    <div class="main-content" id="main-content">
        <header style="background-color: #333; color: white; padding: 1em; text-align: center;">
            <h1>BUSH ♻️</h1>
        </header>

        <main>
            <!-- Video Area -->
            <div class="video-area" id="video-area" style="width: 100%; height: 400px; background-color: #000; display: flex; justify-content: center; align-items: center; color: white; position: relative;">
                <p>Loading video...</p>
                <button onclick="toggleFullScreen()" style="position: absolute; top: 10px; right: 10px;">Fullscreen</button>
                <div class="progress-bar" style="position: absolute; bottom: 0; width: 100%; height: 5px; background: rgba(255,255,255,0.5);">
                    <div class="progress-bar-inner" id="progress-bar-inner" style="height: 100%; background: #ff6347; width: 0%;"></div>
                </div>
            </div>

            <!-- App Navigation -->
            <div class="app-boxes" style="display: flex; justify-content: center; margin-top: 30px;">
                <div id="tiktok" onclick="loadVideo('TikTok')" style="width: 120px; height: 120px; background: #f4f4f4; border-radius: 50%; display: flex; justify-content: center; align-items: center; font-weight: bold; cursor: pointer; margin: 0 10px;">
                    <span>TikTok</span>
                </div>
                <div id="instagram" onclick="loadVideo('Instagram')" style="width: 120px; height: 120px; background: #f4f4f4; border-radius: 50%; display: flex; justify-content: center; align-items: center; font-weight: bold; cursor: pointer; margin: 0 10px;">
                    <span>Instagram</span>
                </div>
            </div>
        </main>

        <!-- Bottom Navigation -->
        <div class="bottom-nav" style="position: fixed; bottom: 0; left: 0; width: 100%; background: #333; text-align: center; padding: 10px 0; display: flex; justify-content: space-between;">
            <a href="#">Home</a>
            <a href="#">Live</a>
            <a href="#">Account</a>
            <a href="#">Settings</a>
            <a href="#" onclick="alert('Messages coming soon!')">Messages</a>
        </div>
    </div>

    <script>
        // Handle Login
        document.getElementById("login-form").addEventListener("submit", function(event) {
            event.preventDefault();
            document.getElementById("login-section").style.display = "none";
            document.getElementById("main-content").style.display = "block";
        });

        // Load Videos from Different Platforms
        function loadVideo(platform) {
            const videoArea = document.getElementById('video-area');
            const videoUrls = {
                TikTok: 'https://www.tiktok.com/embed/12345',
                Instagram: 'https://www.instagram.com/reel/12345/embed/'
            };

            videoArea.innerHTML = `<iframe src="${videoUrls[platform]}" width="100%" height="400" allowfullscreen></iframe>`;
        }

        // Fullscreen Mode
        function toggleFullScreen() {
            const videoArea = document.getElementById('video-area');
            if (videoArea.requestFullscreen) {
                videoArea.requestFullscreen();
            } else if (videoArea.mozRequestFullScreen) {
                videoArea.mozRequestFullScreen();
            } else if (videoArea.webkitRequestFullscreen) {
                videoArea.webkitRequestFullscreen();
            }
        }
    </script>
</body>
</html>
