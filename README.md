<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Інтерактивний робочий аркуш</title>
    <style>
        body { font-family: Arial, sans-serif; max-width: 700px; margin: 30px auto; padding: 20px; background: #f4f7f6; color: #333; }
        .card { background: white; padding: 20px; border-radius: 10px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); margin-bottom: 20px; }
        h1 { color: #2c3e50; text-align: center; }
        input[type="text"], select { padding: 8px; font-size: 16px; border: 1px solid #ccc; border-radius: 5px; width: 120px; }
        button { background: #27ae60; color: white; border: none; padding: 12px 24px; font-size: 16px; border-radius: 6px; cursor: pointer; width: 100%; }
        button:hover { background: #219150; }
        .correct { border: 2px solid #27ae60 !important; background-color: #eafaf1; }
        .wrong { border: 2px solid #e74c3c !important; background-color: #fdedec; }
        #result { font-size: 18px; font-weight: bold; text-align: center; margin-top: 20px; }
    </style>
</head>
<body>

<h1>📐 Інтерактивний аркуш: Лінійні та квадратні рівняння</h1>

<div class="card">
    <p><strong>Завдання 1 (Введення числа).</strong> Розв'яжіть рівняння: 2x - 10 = 0.</p>
    <label>Відповідь: x = </label>
    <input type="text" id="q1" placeholder="?">
</div>

<div class="card">
    <p><strong>Завдання 2 (Вибір зі списку).</strong> Скільки коренів має рівняння, якщо дискримінант D &lt; 0?</p>
    <select id="q2">
        <option value="">-- Оберіть відповідь --</option>
        <option value="2">Два корені</option>
        <option value="1">Один корінь</option>
        <option value="0">Жодного кореня</option>
    </select>
</div>

<div class="card">
    <p><strong>Завдання 3 (Один правильний варіант).</strong> Обчисліть значення виразу 3² + 4²:</p>
    <label><input type="radio" name="q3" value="14"> 14</label><br>
    <label><input type="radio" name="q3" value="25"> 25</label><br>
    <label><input type="radio" name="q3" value="49"> 49</label>
</div>

<button onclick="checkAnswers()">Перевірити роботу</button>
<div id="result"></div>

<script>
function checkAnswers() {
    let score = 0;

    // Перевірка Завдання 1 (правильна відповідь: 5)
    const q1 = document.getElementById('q1');
    if (q1.value.trim() === '5') {
        q1.className = 'correct';
        score++;
    } else {
        q1.className = 'wrong';
    }

    // Перевірка Завдання 2 (правильна відповідь: 0)
    const q2 = document.getElementById('q2');
    if (q2.value === '0') {
        q2.className = 'correct';
        score++;
    } else {
        q2.className = 'wrong';
    }

    // Перевірка Завдання 3 (правильна відповідь: 25)
    const q3 = document.querySelector('input[name="q3"]:checked');
    if (q3 && q3.value === '25') {
        score++;
    }

    document.getElementById('result').innerText = `Ваш результат: ${score} із 3 балів!`;
}
</script>

</body>
</html>
