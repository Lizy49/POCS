# index.html #
'''HTML
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Авто-Люкс | Продажа автомобилей</title>
  <style>
    body { font-family: 'Segoe UI', sans-serif; background: #0d0d0d; color: white; margin: 0; padding: 0; }
    header { background: #c00; padding: 20px; text-align: center; }
    nav { padding: 20px; background: #1a1a1a; }
    nav a { color: #fff; text-decoration: none; font-size: 18px; margin: 0 15px; }
    nav a:hover { color: #ff6666; }
    .hero { text-align: center; padding: 60px 20px; background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://images.unsplash.com/photo-1503376780353-7e6692767b70?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80'); background-size: cover; color: white; }
    .hero h1 { font-size: 3rem; margin: 0; }
    .hero p { font-size: 1.2rem; margin-top: 10px; }
    footer { text-align: center; padding: 20px; background: #111; color: #888; font-size: 0.9rem; }
  </style>
</head>
<body>
  <header>
    <h1>Авто-Люкс</h1>
    <p>Премиальные автомобили с гарантией</p>
  </header>

  <div class="hero">
    <h1>Ваш путь к идеальному автомобилю</h1>
    <p>Официальный дилер новых и подержанных авто</p>
  </div>

  <nav>
    <a href="index.html">Главная</a>
    <a href="cars.html">Каталог</a>
    <a href="order.html">Оформить заказ</a>
    <a href="calculator.html">Калькулятор</a>
  </nav>

  <footer>
    &copy; 2025 Авто-Люкс. Все права защищены.
  </footer>
</body>
</html>
'''

# cars.html #
'''HTML
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Каталог | Авто-Люкс</title>
  <style>
    body { font-family: 'Segoe UI', sans-serif; background: #121212; color: #eee; margin: 0; padding: 0; }
    header { background: #c00; padding: 15px; text-align: center; }
    nav { padding: 15px; background: #1a1a1a; }
    nav a { color: white; margin: 0 12px; text-decoration: none; }
    nav a:hover { color: #ff6666; }
    .container { padding: 30px; max-width: 1000px; margin: 0 auto; }
    table { width: 100%; border-collapse: collapse; margin-top: 20px; }
    th, td { border: 1px solid #444; padding: 12px; text-align: center; }
    th { background: #333; }
    td { background: #1f1f1f; }
    img { max-width: 150px; border-radius: 6px; margin-top: 8px; }
    footer { text-align: center; padding: 20px; background: #111; color: #888; }
  </style>
</head>
<body>
  <header><h2>Каталог автомобилей</h2></header>

  <nav>
    <a href="index.html">Главная</a>
    <a href="cars.html">Каталог</a>
    <a href="order.html">Оформить заказ</a>
    <a href="calculator.html">Калькулятор</a>
  </nav>

  <div class="container">
    <table>
      <tr><th>Модель</th><th>Год</th><th>Цена (руб)</th><th>Фото</th></tr>
      <tr>
        <td>BMW X5</td><td>2023</td><td>6 500 000</td>
        <td><img src="https://images.unsplash.com/photo-1580273916550-e323be2ae537?w=150" alt="BMW"></td>
      </tr>
      <tr>
        <td>Audi A6</td><td>2022</td><td>4 200 000</td>
        <td><img src="https://images.unsplash.com/photo-1542362567-b07e54358753?w=150" alt="Audi"></td>
      </tr>
      <tr>
        <td>Mercedes C-Class</td><td>2023</td><td>5 100 000</td>
        <td><img src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?w=150" alt="Mercedes"></td>
      </tr>
    </table>
  </div>

  <footer>&copy; 2025 Авто-Люкс</footer>
</body>
</html>
'''

# order.html #
'''HTML
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Заказ | Авто-Люкс</title>
  <style>
    body { background: #111; color: white; font-family: Arial; padding: 20px; }
    header { background: #c00; padding: 15px; text-align: center; }
    nav { padding: 15px; background: #222; }
    nav a { color: white; margin: 0 12px; text-decoration: none; }
    form { max-width: 600px; margin: 30px auto; background: #1e1e1e; padding: 25px; border-radius: 8px; }
    label { display: block; margin-top: 15px; font-weight: bold; }
    input, select, textarea { width: 100%; padding: 8px; margin-top: 5px; border: 1px solid #444; background: #333; color: white; }
    button { margin-top: 20px; padding: 10px 20px; background: #c00; color: white; border: none; font-size: 16px; cursor: pointer; }
    footer { text-align: center; margin-top: 40px; color: #888; }
  </style>
</head>
<body>
  <header><h2>Оформить заказ</h2></header>

  <nav>
    <a href="index.html">Главная</a>
    <a href="cars.html">Каталог</a>
    <a href="order.html">Оформить заказ</a>
    <a href="calculator.html">Калькулятор</a>
  </nav>

  <form>
    <label>Имя:</label>
    <input type="text" required>

    <label>Телефон:</label>
    <input type="tel" required>

    <label>Email:</label>
    <input type="email" required>

    <label>Выберите авто:</label>
    <select required>
      <option>—</option>
      <option>BMW X5</option>
      <option>Audi A6</option>
      <option>Mercedes C-Class</option>
    </select>

    <label>Комментарий:</label>
    <textarea rows="4"></textarea>

    <button type="submit">Отправить заявку</button>
  </form>

  <footer>&copy; 2025 Авто-Люкс</footer>
</body>
</html>
'''
