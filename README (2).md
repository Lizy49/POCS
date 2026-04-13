# Практическая работа №10 #

### Тема: ПР 10. Конструкторы и деструкторы ###

### Цель: совершенствование навыков составления  программ  на основе классов ###

#### Ход работы ####

##### Задача: #####

> повторить структуру алгоритмов решения задач с классами;  
> повторить синтаксис операторов описания класса;  
> приобрести навыки составления программ на основе ООП  




##### Контрольный пример: #####

> Ввожу число 1, получаю результат 1.   
> Ввожу число 2 получаю результат 2.

##### Системный анализ: #####

> Входные данные: `int z`   
> Промежуточные данные: `int n`  
> Выходные данные: `int distance`


##### Блок схема: #####

![sxema.png](123.png)

##### Код программы для консоли: #####
```python
class MatrixWithLifecycle:
    def __init__(self, rows, cols, default_value=0):
        self.rows = rows
        self.cols = cols
        self.data = [[default_value for _ in range(cols)] for _ in range(rows)]
        print(f"Создана матрица размером {rows}x{cols}")

    def __del__(self):
        print(f"Матрица размером {self.rows}x{self.cols} уничтожена")

    def print_matrix(self):
        for row in self.data:
            print(row)


print("--- Начало программы ---")
m = MatrixWithLifecycle(2, 2)
m.set_element = lambda r, c, v: m.data.__setitem__(r, m.data[r].__setitem__(c, v)) if 0<=r<m.rows and 0<=c<m.cols else None

del m
print("--- Конец программы ---")
```

##### Код программы для окна: #####
```python
import tkinter as tk

def find_word():
    text = entry_text.get()
    try:
        k = int(entry_k.get())
    except ValueError:
        result_label.config(text="Ошибка: k должно быть числом!")
        return

    if k < 0 or k >= len(text):
        result_label.config(text="Ошибка: позиция k вне диапазона строки.")
        return

    words = text.split()
    current_pos = 0
    found_word_num = -1

    for i, word in enumerate(words):
        word_len = len(word)
        start = current_pos
        end = current_pos + word_len
        
        if start <= k < end:
            found_word_num = i + 1
            break
        
        if k == end:
            found_word_num = i + 1
            break
            
        current_pos = end + 1
    

    if found_word_num == -1:
        found_word_num = len(words)

    if found_word_num > 0:
        word_text = words[found_word_num - 1]
        result_label.config(text=f"Номер слова: {found_word_num}\nСлово: '{word_text}'")
    else:
        result_label.config(text="Слово не найдено.")


root = tk.Tk()
root.title("Строки")


tk.Label(root, text="Введите строку:").pack()
entry_text = tk.Entry(root, width=50)
entry_text.pack()

tk.Label(root, text="Введите позицию k:").pack()
entry_k = tk.Entry(root, width=10)
entry_k.pack()

btn = tk.Button(root, text="Найти слово", command=find_word)
btn.pack(pady=5)

result_label = tk.Label(root, text="", justify="left", fg="blue")
result_label.pack(pady=10)

root.mainloop()
```

##### Результат работы программы: #####
-

##### Вывод по проделанной работе: #####
> Я совершенствовал навыки составления программ с использованием функций.