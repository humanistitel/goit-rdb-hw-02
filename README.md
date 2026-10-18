# ДЗ 2 · Проєктування бази даних для ML: ER, DDL і point-in-time correctness

Матеріали домашньої роботи з курсу **Relational Databases for Data Science**.

[Відкрити notebook у Google Colab](https://colab.research.google.com/github/humanistitel/goit-rdb-hw-02/blob/main/Diuryk_hw2_semantic_design.ipynb) · [Завантажити `.ipynb`](https://raw.githubusercontent.com/humanistitel/goit-rdb-hw-02/main/Diuryk_hw2_semantic_design.ipynb)

## Google Colab

1. Відкрийте посилання Colab вище у стандартному **Python 3 / CPU** runtime.
2. Виконайте **Runtime → Run all**. Notebook сам підготує залежності, власний PostgreSQL 16 і потрібні дані. Додаткові клітинки або ручне копіювання файлів не потрібні.

Перший запуск потребує інтернету й часу на встановлення PostgreSQL та отримання даних. Сумісні встановлені бібліотеки зберігаються; фактичні версії відображаються під час виконання. Після завершення збережіть notebook із результатами. Якщо виконання перервано після запуску PostgreSQL, виконайте останню клітинку cleanup.

Файл `.ipynb` також можна завантажити та відкрити через **File → Upload notebook**.

## Запуск і залежності

Notebook містить усі SQL-команди та невеликий детермінований набір даних. Додаткові файли для виконання не потрібні; `er_diagram.mmd` містить окрему редаговану ER-діаграму.

У стандартному Colab з Python 3.13 PostgreSQL 16 встановлюється із системних пакетів Ubuntu й працює у власному кластері через локальний Unix socket. Зовнішня база або credentials не потрібні. Для локального запуску підтримується Python 3.9–3.12 з `pgserver==0.1.4`. Остання клітинка зупиняє власний PostgreSQL.

DDL, тестові INSERT, нормалізація, AS-OF SELECT/JOIN, перевірка перекриття інтервалів та Reflection містяться в notebook.
