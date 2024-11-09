import tkinter as tk
from tkinter import messagebox

# Функция для вывода приветствия
def show_greeting():
    try:
        time = int(entry.get())  # Получаем значение времени из поля ввода
    except ValueError:
        messagebox.showerror("Ошибка", "Пожалуйста, введите число.")
        return
    
    # Проверяем время и выводим соответствующее приветствие
    if 8 <= time < 12:
        greeting = "Доброе утро!"
    elif 12 <= time < 17:
        greeting = "Добрый день!"
    elif 17 <= time < 23:
        greeting = "Добрый вечер!"
    else:
        greeting = "Доброй ночи!"
    
    # Обновляем метку с приветствием
    label_result.config(text=greeting)

# Создание основного окна
root = tk.Tk()
root.title("Приветствие по времени суток")

# Создаем виджеты
label_prompt = tk.Label(root, text="Введите время (в часах):")
label_prompt.pack(padx=10, pady=5)

entry = tk.Entry(root)
entry.pack(padx=10, pady=5)

button_show = tk.Button(root, text="Показать", command=show_greeting)
button_show.pack(padx=10, pady=5)

label_result = tk.Label(root, text="", font=("Helvetica", 16))
label_result.pack(padx=10, pady=20)

# Запуск основного цикла программы
root.mainloop()
