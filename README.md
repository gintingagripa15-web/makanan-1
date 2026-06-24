<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
  <title>Login - IDE JUALAN MAKANAN KEKINIAN</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #0b0d10;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      padding: 16px;
    }

    /* ===== HALAMAN LOGIN ===== */
    .login-container {
      max-width: 400px;
      width: 100%;
      background: #14181c;
      border-radius: 40px;
      padding: 36px 28px 40px;
      border: 1px solid #2c2f33;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.8), 0 0 0 1px rgba(255, 215, 0, 0.1);
    }

    .login-header {
      text-align: center;
      margin-bottom: 32px;
    }

    .login-header .logo-icon {
      font-size: 3rem;
      color: #f5b342;
      margin-bottom: 8px;
      display: block;
    }

    .login-header h1 {
      font-size: 1.8rem;
      font-weight: 800;
      color: #fefae0;
      letter-spacing: -0.5px;
    }

    .login-header h1 span {
      background: linear-gradient(135deg, #f5b342, #f7d44a);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .login-header p {
      color: #8a8f96;
      font-size: 0.9rem;
      margin-top: 4px;
    }

    .form-group {
      margin-bottom: 18px;
    }

    .form-group label {
      display: block;
      color: #cbc3b0;
      font-weight: 600;
      font-size: 0.8rem;
      margin-bottom: 6px;
      letter-spacing: 0.3px;
      text-transform: uppercase;
    }

    .form-group .input-wrapper {
      display: flex;
      align-items: center;
      background: #0f1318;
      border-radius: 16px;
      border: 1px solid #2f353d;
      padding: 0 16px;
      transition: border 0.2s ease;
    }

    .form-group .input-wrapper:focus-within {
      border-color: #f5b342;
      box-shadow: 0 0 0 3px rgba(245, 179, 66, 0.15);
    }

    .form-group .input-wrapper i {
      color: #6b717a;
      font-size: 1rem;
      margin-right: 12px;
    }

    .form-group .input-wrapper input {
      width: 100%;
      background: transparent;
      border: none;
      outline: none;
      padding: 14px 0;
      color: #f0e6d3;
      font-size: 1rem;
      font-family: 'Inter', sans-serif;
    }

    .form-group .input-wrapper input::placeholder {
      color: #5a6068;
    }

    .form-group .input-wrapper .toggle-password {
      cursor: pointer;
      color: #6b717a;
      font-size: 0.9rem;
      padding: 8px;
      transition: color 0.2s;
    }

    .form-group .input-wrapper .toggle-password:hover {
      color: #f5b342;
    }

    .login-btn {
      width: 100%;
      background: linear-gradient(135deg, #f5b342, #e09d30);
      border: none;
      padding: 16px;
      border-radius: 60px;
      font-weight: 700;
      font-size: 1.1rem;
      color: #0b0d10;
      cursor: pointer;
      transition: all 0.2s ease;
      margin-top: 8px;
      font-family: 'Inter', sans-serif;
      box-shadow: 0 6px 0 #a0722a;
      letter-spacing: 0.5px;
    }

    .login-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 0 #a0722a;
    }

    .login-btn:active {
      transform: translateY(4px);
      box-shadow: 0 2px 0 #a0722a;
    }

    .login-error {
      background: #2c1518;
      border: 1px solid #8f2a33;
      color: #ff7a85;
      padding: 12px 16px;
      border-radius: 16px;
      font-size: 0.85rem;
      margin-top: 16px;
      display: none;
      align-items: center;
      gap: 10px;
    }

    .login-error.show {
      display: flex;
    }

    .login-error i {
      font-size: 1.1rem;
    }

    .login-footer {
      margin-top: 20px;
      text-align: center;
      color: #5a6068;
      font-size: 0.75rem;
      border-top: 1px solid #23282e;
      padding-top: 20px;
    }

    .login-footer .demo-hint {
      color: #8a8f96;
      background: #1e2329;
      padding: 8px 16px;
      border-radius: 60px;
      display: inline-block;
      font-size: 0.75rem;
      border: 1px solid #2f353d;
      margin-top: 6px;
    }

    .login-footer .demo-hint strong {
      color: #f5b342;
    }

    /* ===== HALAMAN UTAMA (setelah login) ===== */
    .card {
      max-width: 420px;
      width: 100%;
      background: #14181c;
      border-radius: 40px;
      padding: 28px 22px 32px;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.8), 0 0 0 1px rgba(255, 215, 0, 0.15);
      border: 1px solid #2c2f33;
      display: none;
    }

    .card.show {
      display: block;
    }

    .badge-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 18px;
    }

    .badge-number {
      background: #f5b342;
      color: #0b0d10;
      font-weight: 800;
      font-size: 2rem;
      line-height: 1;
      padding: 4px 14px 6px 14px;
      border-radius: 100px;
      letter-spacing: -0.5px;
      box-shadow: 0 6px 0 #a0722a;
      border: 1px solid #ffd966;
    }

    .badge-label {
      background: #23272b;
      padding: 8px 18px;
      border-radius: 60px;
      color: #f0e6d3;
      font-weight: 600;
      font-size: 0.85rem;
      text-transform: uppercase;
      border: 1px solid #3b3f44;
    }

    .main-title {
      font-size: 1.9rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      line-height: 1.2;
      color: #fefae0;
      margin-top: 6px;
      margin-bottom: 18px;
      text-shadow: 0 2px 0 #00000055;
    }

    .main-title span {
      background: linear-gradient(135deg, #f5b342, #f7d44a);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .tetta-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-start;
      gap: 8px 10px;
      margin: 16px 0 22px 0;
    }

    .tetta-item {
      background: #1e2329;
      padding: 8px 18px;
      border-radius: 60px;
      font-weight: 700;
      font-size: 1.1rem;
      color: #f5e7c8;
      border: 1px solid #3d424a;
      box-shadow: 0 4px 0 #0d0f12;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .tetta-item i {
      color: #f5b342;
      font-size: 0.9rem;
    }

    .divider-tiara {
      display: flex;
      align-items: center;
      gap: 12px;
      margin: 18px 0 16px 0;
    }

    .divider-line {
      flex: 1;
      height: 2px;
      background: linear-gradient(90deg, #f5b34255, #f5b342, #f5b34255);
    }

    .divider-icon {
      color: #f5b342;
      font-size: 1.2rem;
      font-weight: 700;
      background: #1e2329;
      padding: 0 10px;
      border-radius: 40px;
      border: 1px solid #f5b34233;
    }

    .tiara-profile {
      background: #1b2026;
      border-radius: 28px;
      padding: 18px 20px;
      margin: 10px 0 8px 0;
      border: 1px solid #31373e;
      box-shadow: inset 0 0 0 1px #2e343b;
    }

    .tiara-name {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 700;
      font-size: 1.5rem;
      color: #fefae0;
      letter-spacing: -0.3px;
    }

    .tiara-name i {
      color: #f5b342;
      font-size: 1.8rem;
      filter: drop-shadow(0 0 4px #f5b34266);
    }

    .tiara-name small {
      font-weight: 400;
      font-size: 0.75rem;
      color: #ab9f8b;
      margin-left: auto;
      background: #0d0f12;
      padding: 4px 12px;
      border-radius: 60px;
      border: 1px solid #3d424a;
    }

    .tiara-details {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 12px 16px;
      margin-top: 4px;
    }

    .detail-item {
      display: flex;
      align-items: center;
      gap: 10px;
      background: #0f1318;
      padding: 6px 16px 6px 12px;
      border-radius: 60px;
      border: 1px solid #2f353d;
      font-size: 0.9rem;
      color: #d4cdbc;
      font-weight: 500;
    }

    .detail-item i {
      color: #f5b342;
      width: 18px;
      font-size: 1rem;
      text-align: center;
    }

    .detail-item a {
      color: #d4cdbc;
      text-decoration: none;
      font-weight: 500;
      transition: 0.2s;
    }

    .detail-item a:hover {
      color: #f5b342;
      text-decoration: underline;
    }

    .detail-item .highlight {
      color: #f5b342;
      font-weight: 700;
    }

    .alamat-sunter {
      margin-top: 6px;
      display: flex;
      align-items: center;
      gap: 10px;
      background: #0d1115;
      border-radius: 60px;
      padding: 8px 18px 8px 16px;
      border: 1px solid #2f353d;
      color: #cbc3b0;
      font-weight: 500;
      font-size: 0.9rem;
    }

    .alamat-sunter i {
      color: #f5b342;
      font-size: 1rem;
      width: 20px;
    }

    .alamat-sunter strong {
      color: #f0e6d3;
      font-weight: 700;
    }

    .footer-note {
      margin-top: 20px;
      display: flex;
      justify-content: flex-end;
      font-size: 0.7rem;
      color: #5b6150;
      letter-spacing: 1px;
      border-top: 1px solid #262b30;
      padding-top: 16px;
      text-transform: uppercase;
      gap: 8px;
    }

    .footer-note i {
      color: #f5b34266;
    }

    .logout-btn {
      background: transparent;
      border: 1px solid #3d424a;
      color: #8a8f96;
      padding: 6px 16px;
      border-radius: 60px;
      font-size: 0.7rem;
      cursor: pointer;
      transition: all 0.2s;
      font-family: 'Inter', sans-serif;
      margin-top: 4px;
    }

    .logout-btn:hover {
      border-color: #f5b342;
      color: #f5b342;
    }

    .bottom-meta {
      margin-top: 12px;
      font-size: 0.65rem;
      color: #5d6357;
      display: flex;
      justify-content: center;
      gap: 16px;
      border-top: 1px dashed #2c3138;
      padding-top: 14px;
    }

    .bottom-meta i {
      color: #f5b342;
    }

    @media (max-width: 450px) {
      .login-container {
        padding: 28px 20px 32px;
      }
      .card {
        padding: 20px 16px 24px;
      }
      .main-title {
        font-size: 1.6rem;
      }
      .tetta-item {
        font-size: 1rem;
        padding: 6px 14px;
      }
      .tiara-name {
        font-size: 1.3rem;
      }
      .detail-item {
        font-size: 0.75rem;
        padding: 4px 12px 4px 8px;
      }
    }
  </style>
</head>
<body>

  <!-- ===== HALAMAN LOGIN ===== -->
  <div id="loginPage" class="login-container">
    <div class="login-header">
      <span class="logo-icon"><i class="fas fa-utensils"></i></span>
      <h1><span>MAKANAN</span> KEKINIAN</h1>
      <p>Login untuk akses ide jualan</p>
    </div>

    <form id="loginForm" autocomplete="off">
      <div class="form-group">
        <label><i class="fas fa-envelope" style="margin-right: 6px;"></i> Email</label>
        <div class="input-wrapper">
          <i class="fas fa-envelope"></i>
          <input type="email" id="emailInput" placeholder="tiaraafriyani1@gmail.com" value="tiaraafriyani1@gmail.com" required>
        </div>
      </div>

      <div class="form-group">
        <label><i class="fas fa-lock" style="margin-right: 6px;"></i> Password</label>
        <div class="input-wrapper">
          <i class="fas fa-key"></i>
          <input type="password" id="passwordInput" placeholder="Masukkan password" value="12345" required>
          <span class="toggle-password" id="togglePassword"><i class="fas fa-eye"></i></span>
        </div>
      </div>

      <button type="submit" class="login-btn"><i class="fas fa-arrow-right-to-bracket" style="margin-right: 10px;"></i> MASUK</button>

      <div id="loginError" class="login-error">
        <i class="fas fa-circle-exclamation"></i>
        <span id="errorMessage">Email atau password salah!</span>
      </div>
    </form>

    <div class="login-footer">
      <div class="demo-hint">
        <i class="fas fa-info-circle"></i> Email: <strong>tiaraafriyani1@gmail.com</strong> &nbsp;·&nbsp; Pass: <strong>12345</strong>
      </div>
    </div>
  </div>

  <!-- ===== HALAMAN UTAMA (setelah login) ===== -->
  <div id="mainPage" class="card">
    <div class="badge-top">
      <div class="badge-number">10</div>
      <div class="badge-label"><i class="fas fa-fire" style="margin-right: 6px; color: #f5b342;"></i> IDE JUALAN</div>
    </div>

    <div class="main-title">
      <span>MAKANAN</span> KEKINIAN
    </div>

    <div class="tetta-grid">
      <div class="tetta-item"><i class="fas fa-utensils"></i> TETTA</div>
      <div class="tetta-item"><i class="fas fa-utensils"></i> TETTA</div>
      <div class="tetta-item"><i class="fas fa-utensils"></i> TETTA</div>
      <div class="tetta-item"><i class="fas fa-utensils"></i> TETTA</div>
      <div class="tetta-item"><i class="fas fa-utensils"></i> TETTA</div>
      <div class="tetta-item"><i class="fas fa-utensils"></i> TETTA</div>
    </div>

    <div class="divider-tiara">
      <span class="divider-line"></span>
      <span class="divider-icon"><i class="fas fa-crown"></i> TIARA</span>
      <span class="divider-line"></span>
    </div>

    <div class="tiara-profile">
      <div class="tiara-name">
        <i class="fas fa-user-astronaut"></i> TIARA 
        <small><i class="fas fa-check-circle" style="color: #4caf50;"></i> verified</small>
        <button class="logout-btn" id="logoutBtn"><i class="fas fa-sign-out-alt"></i> Keluar</button>
      </div>

      <div class="tiara-details">
        <div class="detail-item">
          <i class="fas fa-phone-alt"></i>
          <a href="tel:+6288212922715" class="highlight">0882-1292-2715</a>
        </div>
        <div class="detail-item">
          <i class="fas fa-envelope"></i>
          <a href="mailto:tiaraafriyani1@gmail.com">tiaraafriyani1</a>
        </div>
        <div class="detail-item" style="border-color: #f5b34233;">
          <i class="fas fa-map-pin"></i>
          <span>Sunter</span>
        </div>
      </div>

      <div class="alamat-sunter">
        <i class="fas fa-location-dot"></i>
        <span><strong>Jl. Sunter Agung</strong> · Jakarta Utara</span>
        <i class="fas fa-arrow-right" style="margin-left: auto; opacity: 0.5;"></i>
      </div>
    </div>

    <div class="footer-note">
      <span><i class="fas fa-tag"></i> #tiaraafriyani1</span>
      <span><i class="fas fa-circle" style="font-size: 4px; color: #f5b342;"></i></span>
      <span><i class="fas fa-mobile-alt"></i> 0882-1292-2715</span>
    </div>

    <div class="bottom-meta">
      <span><i class="fas fa-crown"></i> TIARA • IDE JUALAN MAKANAN</span>
      <span>⚡ 2026</span>
    </div>
  </div>

  <script>
    (function() {
      const loginPage = document.getElementById('loginPage');
      const mainPage = document.getElementById('mainPage');
      const loginForm = document.getElementById('loginForm');
      const emailInput = document.getElementById('emailInput');
      const passwordInput = document.getElementById('passwordInput');
      const loginError = document.getElementById('loginError');
      const errorMessage = document.getElementById('errorMessage');
      const togglePassword = document.getElementById('togglePassword');
      const logoutBtn = document.getElementById('logoutBtn');

      // Credentials yang valid - UBAH KE TIARA
      const VALID_EMAIL = 'tiaraafriyani1@gmail.com';
      const VALID_PASSWORD = '12345';

      // Toggle show/hide password
      togglePassword.addEventListener('click', function() {
        const icon = this.querySelector('i');
        if (passwordInput.type === 'password') {
          passwordInput.type = 'text';
          icon.classList.remove('fa-eye');
          icon.classList.add('fa-eye-slash');
        } else {
          passwordInput.type = 'password';
          icon.classList.remove('fa-eye-slash');
          icon.classList.add('fa-eye');
        }
      });

      // Cek session login di localStorage
      function checkSession() {
        const isLoggedIn = localStorage.getItem('tiaraLoggedIn');
        if (isLoggedIn === 'true') {
          loginPage.style.display = 'none';
          mainPage.classList.add('show');
        } else {
          loginPage.style.display = 'block';
          mainPage.classList.remove('show');
        }
      }

      // Fungsi login
      function handleLogin(e) {
        e.preventDefault();

        const email = emailInput.value.trim();
        const password = passwordInput.value.trim();

        // Validasi sederhana
        if (!email || !password) {
          errorMessage.textContent = 'Email dan password harus diisi!';
          loginError.classList.add('show');
          return;
        }

        if (email === VALID_EMAIL && password === VALID_PASSWORD) {
          // Login berhasil
          loginError.classList.remove('show');
          localStorage.setItem('tiaraLoggedIn', 'true');
          loginPage.style.display = 'none';
          mainPage.classList.add('show');
        } else {
          // Login gagal
          errorMessage.textContent = 'Email atau password salah! Coba lagi.';
          loginError.classList.add('show');
          // Kosongkan password
          passwordInput.value = '';
          passwordInput.focus();
        }
      }

      // Fungsi logout
      function handleLogout() {
        localStorage.removeItem('tiaraLoggedIn');
        loginPage.style.display = 'block';
        mainPage.classList.remove('show');
        // Reset form
        loginForm.reset();
        loginError.classList.remove('show');
        emailInput.value = 'tiaraafriyani1@gmail.com';
        passwordInput.value = '';
      }

      // Event listeners
      loginForm.addEventListener('submit', handleLogin);
      logoutBtn.addEventListener('click', handleLogout);

      // Cek session saat halaman dimuat
      checkSession();

      // Jika user menekan Enter di input password, submit form
      passwordInput.addEventListener('keydown', function(e) {
        if (e.key === 'Enter') {
          loginForm.dispatchEvent(new Event('submit'));
        }
      });

    })();
  </script>

</body>
</html>
