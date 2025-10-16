<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>LUXARIA — Искусство соблазна</title>

  <!-- Красивый шрифт -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@500&family=Roboto&display=swap" rel="stylesheet">

  <style>
    body { 
      margin: 0; 
      font-family: 'Roboto', sans-serif; 
      background: linear-gradient(to bottom right, #fff0f5, #ffe4e1); 
      color: #111;
    }
    header { 
      background: #000; 
      color: white; 
      padding: 20px; 
      text-align: center; 
      letter-spacing: 1px;
    }
    nav a { 
      color: #fff; 
      margin: 0 12px; 
      text-decoration: none; 
      font-weight: bold;
    }
    nav a:hover { text-decoration: underline; }

    .hero {
      background: url('https://i.imgur.com/Fb2yfrn.jpg') center/cover no-repeat;
      height: 400px; 
      display: flex; 
      align-items: center; 
      justify-content: center; 
      color: white; 
      text-shadow: 0 0 6px black;
    }
    .hero h1 { 
      font-size: 32px; 
      font-family: 'Playfair Display', serif;
      background: rgba(0,0,0,0.4);
      padding: 10px 20px;
      border-radius: 10px;
    }

    .section { 
      padding: 40px 20px; 
      max-width: 1000px; 
      margin: auto; 
    }

    .products { 
      display: flex; 
      flex-wrap: wrap; 
      gap: 20px; 
      justify-content: center; 
    }

    .product { 
      background: white; 
      padding: 15px; 
      border-radius: 12px; 
      width: 180px; 
      text-align: center; 
      box-shadow: 0 0 10px rgba(0,0,0,0.1); 
      transition: transform 0.2s ease; 
    }
    .product:hover { transform: scale(1.05); }

    .product img { 
      width: 100%; 
      border-radius: 8px; 
      height: 200px; 
      object-fit: cover;
    }

    .product button {
      background: #000; 
      color: #fff; 
      border: none; 
      padding: 8px 12px; 
      border-radius: 6px; 
      margin-top: 8px; 
      cursor: pointer;
      transition: background 0.2s;
    }
    .product button:hover { background: #e60073; }

    footer { 
      background: #000; 
      color: white; 
      text-align: center; 
      padding: 20px; 
      margin-top: 40px; 
    }

    /* Форма заказа */
    .modal {
      display: none;
      position: fixed;
      z-index: 100;
      left: 0; top: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.5);
      justify-content: center; align-items: center;
    }
    .modal-content {
      background: white;
      padding: 20px;
      border-radius: 10px;
      width: 90%;
      max-width: 400px;
      text-align: center;
    }
    .modal-content input, .modal-content button {
      width: 100%;
      margin-top: 10px;
      padding: 10px;
      border-radius: 6px;
      border: 1px solid #ccc;
    }
    .modal-content button {
      background: #000;
      color: white;
      border: none;
      cursor: pointer;
    }

    @media (max-width: 600px) {
      .hero { height: 250px; }
      .hero h1 { font-size: 22px; }
      .product { width: 45%; }
    }
  </style>
</head>

<body>
  <header>
    <h1>LUXARIA</h1>
    <nav>
      <a href="#">Главная</a>
      <a href="#catalog">Каталог</a>
      <a href="#contacts">Контакты</a>
    </nav>
  </header>

  <div class="hero">
    <h1>Искусство соблазна: Новая коллекция</h1>
  </div>

  <div class="section" id="catalog">
    <h2 style="text-align:center;">Популярные модели</h2>
    <div class="products">
      <div class="product">
        <img src="https://i.imgur.com/XOVjqrs.jpg" alt="Scarlet Lace">
        <p>Scarlet Lace</p>
        <strong>12 000 ₸</strong>
        <button onclick="openModal('Scarlet Lace')">Купить</button>
      </div>
      <div class="product">
        <img src="https://i.imgur.com/FHdfrEb.jpg" alt="Noir Secret">
        <p>Noir Secret</p>
        <strong>14 500 ₸</strong>
        <button onclick="openModal('Noir Secret')">Купить</button>
      </div>
      <div class="product">
        <img src="https://i.imgur.com/9DwZ1Zq.jpg" alt="Velvet Touch">
        <p>Velvet Touch</p>
        <strong>13 200 ₸</strong>
        <button onclick="openModal('Velvet Touch')">Купить</button>
      </div>
    </div>
  </div>

  <!-- Модальное окно -->
  <div id="orderModal" class="modal">
    <div class="modal-content">
      <h3>Оформление заказа</h3>
      <p id="selectedProduct"></p>
      <input type="text" placeholder="Ваше имя">
      <input type="tel" placeholder="Номер телефона">
      <button onclick="closeModal()">Отправить заказ</button>
      <button onclick="closeModal()" style="background:#ccc;color:#000;">Отмена</button>
    </div>
  </div>

  <div class="section" id="contacts">
    <h2 style="text-align:center;">Контакты</h2>
    <p style="text-align:center;">📍 Казахстан, г. Костанай<br>
    📞 +7 777 123 4567<br>
    ✉️ luxaria.shop@gmail.com</p>
  </div>

  <footer>
    © 2025 LUXARIA — Все права защищены
  </footer>

  <script>
    function openModal(productName) {
      document.getElementById('orderModal').style.display = 'flex';
      document.getElementById('selectedProduct').innerText = 'Вы выбрали: ' + productName;
    }
    function closeModal() {
      document.getElementById('orderModal').style.display = 'none';
    }
  </script>
</body>
</html>
