
 
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes" />
  <meta name="theme-color" content="#667eea" />
  <title>Login - B25 CHEATS</title>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"
  />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --primary: #667eea;
      --secondary: #764ba2;
      --success: #27ae60;
      --error: #e74c3c;
      --text: #1a1a1a;
      --text-light: #666;
      --bg: #f8f9fa;
      --white: #ffffff;
    }

    body {
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', sans-serif;
      padding: 20px;
    }

    .container {
      background: var(--white);
      border-radius: 24px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.25);
      max-width: 480px;
      width: 100%;
      overflow: hidden;
    }

    .header {
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      padding: 40px 30px;
      text-align: center;
      color: white;
    }

    .header i {
      font-size: 3rem;
      margin-bottom: 12px;
    }

    .header h1 {
      font-size: 2rem;
      font-weight: 700;
      margin-bottom: 6px;
    }

    .tabs {
      display: flex;
      background: var(--bg);
      padding: 8px;
    }

    .tab {
      flex: 1;
      padding: 14px;
      text-align: center;
      background: transparent;
      border: none;
      border-radius: 12px;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s;
      color: var(--text-light);
    }

    .tab.active {
      background: white;
      color: var(--primary);
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
    }

    .form-container {
      padding: 32px 30px;
    }

    .form-content {
      display: none;
    }

    .form-content.active {
      display: block;
      animation: fadeIn 0.4s;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(10px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .form-group {
      margin-bottom: 20px;
    }

    .form-group label {
      display: block;
      margin-bottom: 8px;
      font-weight: 600;
      color: var(--text);
      font-size: 0.95rem;
    }

    .input-wrapper {
      position: relative;
    }

    .input-icon {
      position: absolute;
      left: 16px;
      top: 50%;
      transform: translateY(-50%);
      color: #999;
      pointer-events: none;
    }

    .form-group input {
      width: 100%;
      padding: 14px 16px 14px 44px;
      border: 2px solid #e0e0e0;
      border-radius: 12px;
      font-size: 1rem;
      transition: all 0.3s;
      outline: none;
      background: var(--bg);
    }

    .form-group input:focus {
      border-color: var(--primary);
      background: white;
      box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.1);
    }

    .btn {
      width: 100%;
      padding: 16px;
      border: none;
      border-radius: 12px;
      font-size: 1.05rem;
      font-weight: 700;
      cursor: pointer;
      transition: all 0.3s;
      margin-top: 10px;
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--success), #229954);
      color: white;
      box-shadow: 0 4px 15px rgba(39, 174, 96, 0.3);
    }

    .btn-primary:hover {
      transform: translateY(-2px);
    }

    .btn-primary.loading {
      color: transparent;
      position: relative;
    }

    .btn-primary.loading::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      top: 50%;
      left: 50%;
      margin-left: -10px;
      margin-top: -10px;
      border: 3px solid rgba(255, 255, 255, 0.3);
      border-top-color: white;
      border-radius: 50%;
      animation: spin 0.8s linear infinite;
    }

    @keyframes spin {
      to {
        transform: rotate(360deg);
      }
    }

    .message {
      padding: 14px;
      border-radius: 12px;
      margin-bottom: 20px;
      display: none;
      font-size: 0.95rem;
      font-weight: 600;
      text-align: center;
    }

    .message.show {
      display: block;
      animation: slideDown 0.4s;
    }

    .message.error {
      background: linear-gradient(135deg, #fee, #fdd);
      color: var(--error);
      border: 2px solid #fcc;
    }

    .message.success {
      background: linear-gradient(135deg, #d4edda, #c3e6cb);
      color: #155724;
      border: 2px solid #c3e6cb;
    }

    .social-links {
      display: flex;
      gap: 10px;
      margin-top: 24px;
      padding-top: 24px;
      border-top: 2px solid #f0f0f0;
    }

    .social-link {
      flex: 1;
      padding: 12px;
      border-radius: 12px;
      text-decoration: none;
      color: white;
      font-weight: 600;
      text-align: center;
      font-size: 0.85rem;
      transition: all 0.3s;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 4px;
    }

    .social-link.discord {
      background: linear-gradient(135deg, #5865f2, #4752c4);
    }

    .social-link.telegram {
      background: linear-gradient(135deg, #0088cc, #006699);
    }

    .social-link.youtube {
      background: linear-gradient(135deg, #ff0000, #cc0000);
    }

    .countdown {
      text-align: center;
      font-size: 0.9rem;
      color: var(--text-light);
      margin-top: 12px;
    }

    .countdown span {
      color: var(--error);
      font-weight: 700;
    }

    @media (max-width: 480px) {
      .container {
        border-radius: 20px;
      }

      .social-links {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <i class="fas fa-shield-alt"></i>
      <h1>B25 CHEATS</h1>
      <p>Secure Access Portal</p>
    </div>

    <div class="tabs">
      <button class="tab active" onclick="switchTab('login', event)">
        <i class="fas fa-sign-in-alt"></i> Login
      </button>
      <button class="tab" onclick="switchTab('register', event)">
        <i class="fas fa-user-plus"></i> Register
      </button>
    </div>

    <div class="form-container">
      <!-- Login -->
      <div class="form-content active" id="login-form">
        <div id="login-message" class="message"></div>
        <form onsubmit="handleLogin(event)">
          <div class="form-group">
            <label><i class="fas fa-user"></i> Username or Email</label>
            <div class="input-wrapper">
              <i class="fas fa-user input-icon"></i>
              <input type="text" id="login-identifier" placeholder="Enter username or email" required />
            </div>
          </div>

          <div class="form-group">
            <label><i class="fas fa-lock"></i> Password</label>
            <div class="input-wrapper">
              <i class="fas fa-lock input-icon"></i>
              <input type="password" id="login-password" placeholder="Enter password" required />
            </div>
          </div>

          <button type="submit" class="btn btn-primary" id="login-btn">
            <i class="fas fa-sign-in-alt"></i> Login
          </button>
        </form>

        <div class="social-links">
          <a href="https://discord.gg/7PG6MF9wCN" class="social-link discord"><i class="fab fa-discord"></i><span>Discord</span></a>
          <a href="https://t.me/b25cheats" class="social-link telegram"><i class="fab fa-telegram-plane"></i><span>Telegram</span></a>
          <a href="https://www.youtube.com/@b25-cheats" class="social-link youtube"><i class="fab fa-youtube"></i><span>YouTube</span></a>
        </div>
      </div>

      <!-- Register -->
      <div class="form-content" id="register-form">
        <div id="register-message" class="message"></div>
        <form onsubmit="handleRegister(event)">
          <div class="form-group">
            <label><i class="fas fa-user"></i> Username (min 6 characters)</label>
            <div class="input-wrapper">
              <i class="fas fa-user input-icon"></i>
              <input type="text" id="register-username" minlength="6" required />
            </div>
          </div>

          <div class="form-group">
            <label><i class="fas fa-envelope"></i> Gmail Address</label>
            <div class="input-wrapper">
              <i class="fas fa-envelope input-icon"></i>
              <input type="email" id="register-email" placeholder="your.email@gmail.com" required />
            </div>
          </div>

          <div class="form-group">
            <label><i class="fas fa-lock"></i> Password</label>
            <div class="input-wrapper">
              <i class="fas fa-lock input-icon"></i>
              <input type="password" id="register-password" required />
            </div>
          </div>

          <div class="form-group">
            <label><i class="fas fa-lock"></i> Confirm Password</label>
            <div class="input-wrapper">
              <i class="fas fa-lock input-icon"></i>
              <input type="password" id="register-password-confirm" required />
            </div>
          </div>

          <button type="submit" class="btn btn-primary" id="register-btn">
            <i class="fas fa-user-plus"></i> Register
          </button>

          <div id="countdown" class="countdown" style="display:none;">
            Please wait <span id="countdown-timer">10</span> seconds...
          </div>
        </form>

        <div class="social-links">
          <a href="https://discord.gg/7PG6MF9wCN" class="social-link discord"><i class="fab fa-discord"></i><span>Discord</span></a>
          <a href="https://t.me/b25cheats" class="social-link telegram"><i class="fab fa-telegram-plane"></i><span>Telegram</span></a>
          <a href="https://www.youtube.com/@b25-cheats" class="social-link youtube"><i class="fab fa-youtube"></i><span>YouTube</span></a>
        </div>
      </div>
    </div>
  </div>

  <script>
    function switchTab(tab, event) {
      document.querySelectorAll('.tab').forEach((t) => t.classList.remove('active'));
      event.currentTarget.classList.add('active');
      document.querySelectorAll('.form-content').forEach((f) => f.classList.remove('active'));
      document.getElementById(tab + '-form').classList.add('active');
    }

    function showMessage(formType, message, isError = true) {
      const msgEl = document.getElementById(formType + '-message');
      msgEl.textContent = message;
      msgEl.className = 'message show ' + (isError ? 'error' : 'success');
    }

    function setLoading(btnId, isLoading) {
      const btn = document.getElementById(btnId);
      btn.disabled = isLoading;
      btn.classList.toggle('loading', isLoading);
    }

    async function handleLogin(e) {
      e.preventDefault();
      const id = document.getElementById('login-identifier').value.trim();
      const pw = document.getElementById('login-password').value;
      if (!id || !pw) return showMessage('login', 'Please fill in all fields');
      setLoading('login-btn', true);
      await new Promise((r) => setTimeout(r, 1000)); // simulate
      showMessage('login', 'Login successful!', false);
      setLoading('login-btn', false);
    }

    async function handleRegister(e) {
      e.preventDefault();
      const u = document.getElementById('register-username').value.trim();
      const eMail = document.getElementById('register-email').value.trim().toLowerCase();
      const p1 = document.getElementById('register-password').value;
      const p2 = document.getElementById('register-password-confirm').value;

      if (u.length < 6) return showMessage('register', 'Username must be at least 6 characters');
      if (!eMail.endsWith('@gmail.com')) return showMessage('register', 'Use Gmail only');
      if (p1 !== p2) return showMessage('register', 'Passwords do not match');
      if (p1.length < 6) return showMessage('register', 'Password too short');

      const countdownEl = document.getElementById('countdown');
      const timerEl = document.getElementById('countdown-timer');
      countdownEl.style.display = 'block';
      let s = 10;
      const interval = setInterval(() => {
        s--;
        timerEl.textContent = s;
        if (s <= 0) {
          clearInterval(interval);
          countdownEl.style.display = 'none';
          showMessage('register', 'Registered successfully!', false);
        }
      }, 1000);
    }
  </script>
</body>
</html>
