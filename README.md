<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shibin - AI Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #333;
            min-height: 100vh;
            padding: 40px 20px;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 60px 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 400px;
            height: 400px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-30px); }
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        .avatar {
            width: 120px;
            height: 120px;
            margin: 0 auto 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            animation: pulse 3s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        h1 {
            color: white;
            font-size: 48px;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .subtitle {
            color: rgba(255, 255, 255, 0.9);
            font-size: 20px;
            margin-bottom: 20px;
            font-weight: 300;
        }

        .badge-container {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 25px;
        }

        .badge {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 14px;
            backdrop-filter: blur(10px);
            animation: slideIn 0.5s ease-out;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .content {
            padding: 60px 40px;
        }

        .section {
            margin-bottom: 50px;
        }

        .section-title {
            font-size: 28px;
            color: #667eea;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 3px solid #667eea;
            position: relative;
        }

        .section-title::before {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 0;
            height: 3px;
            background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
            width: 60px;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .contact-card {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
            padding: 20px;
            border-radius: 15px;
            border-left: 4px solid #667eea;
            transition: all 0.3s ease;
        }

        .contact-card:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.2);
        }

        .contact-card strong {
            color: #667eea;
            display: block;
            margin-bottom: 8px;
        }

        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin: 30px 0;
        }

        .social-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 24px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
        }

        .social-icon:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .skill-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
            border-radius: 15px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .skill-icon {
            font-size: 40px;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .skill-name {
            font-size: 14px;
            font-weight: 600;
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            border-top: 4px solid #667eea;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
        }

        .stat-number {
            font-size: 32px;
            font-weight: 700;
            color: #667eea;
            margin-bottom: 10px;
        }

        .stat-label {
            color: #666;
            font-size: 14px;
            font-weight: 600;
        }

        .footer {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 30px;
            text-align: center;
            color: white;
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 36px;
            }

            .subtitle {
                font-size: 16px;
            }

            .content {
                padding: 30px 20px;
            }

            .section-title {
                font-size: 22px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <div class="header-content">
                <div class="avatar">👨‍💻</div>
                <h1>Hi, I'm Shibin</h1>
                <p class="subtitle">AI Developer & Machine Learning Enthusiast</p>
                <div class="badge-container">
                    <div class="badge">🚀 Innovation-Driven</div>
                    <div class="badge">🤖 AI Specialist</div>
                    <div class="badge">💡 Problem Solver</div>
                    <div class="badge">🌍 From India</div>
                </div>
            </div>
        </div>

        <!-- Main Content -->
        <div class="content">
            <!-- Contact Section -->
            <div class="section">
                <h2 class="section-title">📬 Get In Touch</h2>
                <div class="contact-info">
                    <div class="contact-card">
                        <strong>Email</strong>
                        <a href="mailto:shibinpsbnp11@gmail.com" style="color: #666; text-decoration: none;">shibinpsbnp11@gmail.com</a>
                    </div>
                    <div class="contact-card">
                        <strong>Location</strong>
                        <span>India 🇮🇳</span>
                    </div>
                </div>

                <div class="social-links">
                    <a href="https://linkedin.com/in/shibin-p" class="social-icon" title="LinkedIn">🔗</a>
                    <a href="https://instagram.com/shibin_p__" class="social-icon" title="Instagram">📸</a>
                    <a href="https://github.com/neuro-forge" class="social-icon" title="GitHub">⚙️</a>
                </div>
            </div>

            <!-- Skills Section -->
            <div class="section">
                <h2 class="section-title">🛠️ Languages & Tools</h2>
                <div class="skills-grid">
                    <div class="skill-item">
                        <div class="skill-icon">🐍</div>
                        <div class="skill-name">Python</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">💻</div>
                        <div class="skill-name">JavaScript</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">©️</div>
                        <div class="skill-name">C/C++</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">🧠</div>
                        <div class="skill-name">TensorFlow</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">🔥</div>
                        <div class="skill-name">PyTorch</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">📊</div>
                        <div class="skill-name">Pandas</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">🤖</div>
                        <div class="skill-name">Scikit-Learn</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">👁️</div>
                        <div class="skill-name">OpenCV</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">💾</div>
                        <div class="skill-name">MySQL</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">📱</div>
                        <div class="skill-name">Flutter</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">🎨</div>
                        <div class="skill-name">Figma</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">⚡</div>
                        <div class="skill-name">Git</div>
                    </div>
                </div>
            </div>

            <!-- Stats Section -->
            <div class="section">
                <h2 class="section-title">📈 GitHub Statistics</h2>
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-number">🏆</div>
                        <div class="stat-label">GitHub Trophies</div>
                        <p style="font-size: 12px; margin-top: 10px; color: #999;">View on GitHub Profile</p>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">📚</div>
                        <div class="stat-label">Repositories</div>
                        <p style="font-size: 12px; margin-top: 10px; color: #999;">Check GitHub Profile</p>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number">🔥</div>
                        <div class="stat-label">Contribution Streak</div>
                        <p style="font-size: 12px; margin-top: 10px; color: #999;">Active Developer</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>✨ A passionate AI developer committed to building intelligent solutions</p>
            <p style="margin-top: 15px; font-size: 12px; opacity: 0.9;">Let's collaborate and create something amazing together!</p>
        </div>
    </div>
</body>
</html>
