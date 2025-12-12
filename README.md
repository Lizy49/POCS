# calculator.
```HTML
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>ПР7 — Вариант 2</title>
  <style>
    body { font-family: Arial; padding: 20px; }
    input, button { margin: 8px 0; padding: 6px; }
    #result { margin-top: 15px; font-weight: bold; color: #2c5; }
  </style>
</head>
<body>
  <h2>Сумма между первым и последним нулём</h2>

  <!-- Способ 1: ввод через поле -->
  <div>
    <label>Введите массив (через запятую):</label><br>
    <input type="text" id="input-field" placeholder="1,0,3,4,0,5">
    <button onclick="handleFieldInput()">Посчитать</button>
  </div>

  <!-- Способ 2: ввод через prompt -->
  <div>
    <button id="prompt-btn">Ввести через всплывающее окно</button>
  </div>

  <!-- Место вывода результата -->
  <div id="result"></div>

  <script src="script.js"></script>
</body>
</html>
```
# script.js #
```js
// Обработчик для ввода через текстовое поле (использует onclick в HTML)
function handleFieldInput() {
  const input = document.getElementById('input-field').value.trim();
  processInput(input);
}

// Обработчик для ввода через prompt (привязан через addEventListener)
document.getElementById('prompt-btn').addEventListener('click', function () {
  const input = prompt('Введите массив через запятую (например: 1,0,2,3,0,4)');
  if (input !== null) processInput(input.trim());
});

// Основная логика обработки
function processInput(str) {
  if (!str) {
    showResult('Ошибка: пустой ввод.');
    return;
  }

  const arr = str.split(',').map(item => {
    const num = parseFloat(item.trim());
    return isNaN(num) ? NaN : num;
  });

  if (arr.some(isNaN)) {
    showResult('Ошибка: введены некорректные данные.');
    return;
  }

  const firstZero = arr.indexOf(0);
  const lastZero = arr.lastIndexOf(0);

  if (firstZero === -1 || lastZero === -1 || firstZero === lastZero) {
    showResult('Недостаточно нулей в массиве (нужно хотя бы два).');
    return;
  }

  let sum = 0;
  for (let i = firstZero + 1; i < lastZero; i++) {
    sum += arr[i];
  }

  showResult(`Сумма элементов между первым и последним нулём: ${sum}`);
}

// Вывод результата на страницу
function showResult(text) {
  document.getElementById('result').textContent = text;
}
```
