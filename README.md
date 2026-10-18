# ДЗ 2 · Проєктування бази даних для ML: ER, DDL і point-in-time correctness

Матеріали домашньої роботи з курсу **Relational Databases for Data Science**.

[Відкрити notebook у Google Colab](https://colab.research.google.com/github/humanistitel/goit-rdb-hw-02/blob/main/Diuryk_hw2_semantic_design.ipynb) · [Завантажити `.ipynb`](https://raw.githubusercontent.com/humanistitel/goit-rdb-hw-02/main/Diuryk_hw2_semantic_design.ipynb)

## Google Colab

1. Відкрийте посилання Colab вище. За потреби збережіть копію notebook у потрібній папці Google Drive.
2. **Обов’язково:** у **Runtime → Change runtime type** виберіть **Python 3**, **CPU**, **Runtime Version = 2026.07** і натисніть **Save** (Python **3.12.13**). [Довідка Colab](https://research.google.com/colaboratory/runtime-version-faq.html).
3. Підключіть runtime і виконайте клітинку підготовки робочої папки перед основним кодом notebook:

```python
from pathlib import Path
import os
import subprocess

repo_dir = Path("/content/goit-rdb-hw-02")
if not repo_dir.exists():
    subprocess.run([
        "git", "clone", "--depth", "1",
        "https://github.com/humanistitel/goit-rdb-hw-02.git", str(repo_dir)
    ], check=True)
os.chdir(repo_dir)
print(Path.cwd())
```

4. Виконайте **Runtime → Restart session and run all**, залишивши клітинку підготовки перед основним кодом. Перший запуск встановлює залежності та потребує мережі.
5. Збережіть notebook із результатами. Якщо виконання перервано після створення PostgreSQL, запустіть останню клітинку cleanup.

Пряме посилання на raw-файл також дозволяє завантажити `.ipynb` і відкрити його через **File → Upload notebook**; підготовка робочої папки залишається такою самою.

## Запуск і залежності

Notebook містить усі SQL-команди та невеликий детермінований набір даних. Додаткові файли для виконання не потрібні; `er_diagram.mmd` містить окрему редаговану ER-діаграму. Перша клітинка встановлює відсутні `pgserver==0.1.4`, `SQLAlchemy==2.0.54`, `psycopg2-binary==2.9.12`, `pandas==2.3.3`; наявні імпорти вона не перевстановлює автоматично. Фактичні версії відображаються під час виконання.

DDL, тестові INSERT, нормалізація, AS-OF SELECT/JOIN, перевірка перекриття інтервалів та Reflection містяться в notebook. PostgreSQL працює у власному тимчасовому кластері; стороння база або credentials не потрібні.
