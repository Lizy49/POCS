# calculator.html #
```html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Калькулятор | Авто-Люкс</title>
  <style>
    body { background: #0a0a0a; color: white; font-family: Arial; padding: 20px; }
    header { background: #c00; padding: 15px; text-align: center; }
    nav { padding: 15px; background: #222; }
    nav a { color: white; margin: 0 12px; text-decoration: none; }
    .calc { max-width: 500px; margin: 30px auto; background: #1a1a1a; padding: 25px; border-radius: 8px; }
    label { display: block; margin-top: 15px; font-weight: bold; }
    input { width: 100%; padding: 8px; margin-top: 5px; background: #333; color: white; border: 1px solid #555; }
    button { margin-top: 20px; padding: 10px 20px; background: #c00; color: white; border: none; width: 100%; font-size: 16px; cursor: pointer; }
    #result { margin-top: 20px; padding: 15px; background: #2a2a2a; border-radius: 6px; text-align: center; font-size: 18px; }
    footer { text-align: center; margin-top: 40px; color: #888; }
  </style>
</head>
<body>
  <header><h2>Кредитный калькулятор</h2></header>

  <nav>
    <a href="index.html">Главная</a>
    <a href="cars.html">Каталог</a>
    <a href="order.html">Оформить заказ</a>
    <a href="calculator.html">Калькулятор</a>
  </nav>

  <div class="calc">
    <label>Стоимость авто (руб):</label>
    <input type="number" id="price" value="5000000">

    <label>Первоначальный взнос (%):</label>
    <input type="number" id="down" value="20" min="0" max="100">

    <label>Срок кредита (месяцы):</label>
    <input type="number" id="term" value="36" min="1">

    <button onclick="calculate()">Рассчитать</button>
    <div id="result">Результат появится здесь</div>
  </div>

  <footer>&copy; 2025 Авто-Люкс</footer>

  <script src="calc.js"></script>
</body>
</html>
```
# script.js #
```js
function calculate() {
  let price = Number(document.getElementById("price").value);
  let downPercent = Number(document.getElementById("down").value);
  let term = Number(document.getElementById("term").value);

  if (price <= 0 || term <= 0 || downPercent < 0 || downPercent > 100) {
    document.getElementById("result").innerText = "Ошибка: проверьте данные";
    return;
  }

  let downPayment = price * (downPercent / 100);
  let loanAmount = price - downPayment;
  let monthly = loanAmount / term;

  let msg = "Первоначальный взнос: " + Math.round(downPayment).toLocaleString() + " ₽\n" +
            "Ежемесячный платёж: " + Math.round(monthly).toLocaleString() + " ₽\n" +
            "Сумма кредита: " + Math.round(loanAmount).toLocaleString() + " ₽";

  document.getElementById("result").innerText = msg;
}
```
