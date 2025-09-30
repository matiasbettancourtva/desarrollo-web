<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Registro de Cliente</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f7fa;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .container {
      display: flex;
      background: white;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      overflow: hidden;
      width: 900px;
      max-width: 100%;
    }
    .promo {
      background: #f0f4ff;
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      color: #333;
    }
    .promo-circle {
      background: #ffdddd;
      border-radius: 50%;
      width: 120px;
      height: 120px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-weight: bold;
      color: red;
      margin-bottom: 10px;
    }
    .form-section {
      flex: 2;
      padding: 40px;
    }
    h2 {
      margin-bottom: 10px;
    }
    p {
      margin-bottom: 20px;
      color: #555;
    }
    input[type="text"], input[type="email"], input[type="password"] {
      width: 100%;
      padding: 12px;
      margin: 8px 0;
      border-radius: 6px;
      border: 1px solid #ccc;
      box-sizing: border-box;
    }
    .checkbox {
      margin: 10px 0;
    }
    button {
      background: linear-gradient(to right, #4facfe, #00f2fe);
      border: none;
      color: white;
      padding: 14px;
      border-radius: 8px;
      width: 100%;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      opacity: 0.9;
    }
    .link {
      font-size: 14px;
      float: right;
      color: #007BFF;
      text-decoration: none;
    }
    .message {
      margin-top: 15px;
      font-weight: bold;
    }
    .success { color: green; }
    .error { color: red; }
  </style>
</head>
<body>
  <div class="container">
    <div class="promo">
      <div class="promo-circle">Frío Natural</div>
      <span>Ilustración / promo</span>
    </div>
    <div class="form-section">
      <h2>Registro de Cliente</h2>
      <p>Crea tu cuenta para gestionar pedidos y perfil</p>
      <form id="registerForm">
        <input type="email" id="email" placeholder="ejemplo@correo.com" required>
        <input type="text" id="name" placeholder="Nombre completo" required>
        <input type="password" id="password" placeholder="Contraseña" required>
        
        <div class="checkbox">
          <input type="checkbox" id="terms" required>
          <label for="terms">Acepto términos y condiciones</label>
          <a href="#" class="link">¿Olvidaste tu contraseña?</a>
        </div>

        <button type="submit">Registrar</button>
      </form>
      <div class="message" id="message"></div>
    </div>
  </div>

  <script>
    const form = document.getElementById('registerForm');
    const message = document.getElementById('message');

    form.addEventListener('submit', (e) => {
      e.preventDefault();

      const email = document.getElementById('email').value;
      if (email === "ya@existe.com") {
        message.textContent = "Error: Email ya está en uso";
        message.className = "message error";
      } else {
        message.textContent = "Registro exitoso: Bienvenido 🎉";
        message.className = "message success";
      }
    });
  </script>
</body>
</html>
