# Flask API з SQLAlchemy

Цей REST API створений на основі Flask для управління магазинами та товарами. Для роботи з базою даних використовується SQLAlchemy.

## Основні функції
- **Магазини**: додавання, перегляд та видалення магазинів.
- **Товари**: створення, перегляд та видалення товарів, які прив’язані до певних магазинів.

## Вимоги
- Python 3.x
- Flask
- Flask-SQLAlchemy
- Flask-Smorest
- Marshmallow

## Інструкція з налаштування
1. **Клонуйте репозиторій**  
   ```bash
   git clone https://github.com/Lutvunenko-Dmutro/flask-api.git
   cd flask-api
   ```

2. **Створіть віртуальне середовище**  
   ```bash
   python -m venv venv
   ```

3. **Активуйте віртуальне середовище**  
   - Windows:
     ```bash
     venv\Scripts\activate
     ```
   - macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Встановіть залежності**  
   ```bash
   pip install -r requirements.txt
   ```

5. **Запустіть додаток**  
   ```bash
   flask run
   ```
   API буде доступним за адресою [http://127.0.0.1:5000/](http://127.0.0.1:5000/).

## API Ендпоінти
### Магазини
- `GET /stores` — отримання списку магазинів.
- `GET /stores/<int:store_id>` — перегляд магазину за ID.
- `POST /stores` — створення нового магазину.
- `DELETE /stores/<int:store_id>` — видалення магазину за ID.

### Товари
- `GET /item/<int:item_id>` — отримання інформації про товар за ID.
- `POST /item` — додавання нового товару.
- `DELETE /item/<int:item_id>` — видалення товару за ID.

## Приклади запитів
### Додавання магазину  
**POST /stores**  
```json
{
  "name": "Техніка Світ"
}
```

### Додавання товару  
**POST /item**  
```json
{
  "name": "Смартфон",
  "price": 799.99,
  "store_id": 1
}
```

## Структура проекту
- **`app.py`** — головний файл додатку, який відповідає за налаштування Flask і реєстрацію ендпоінтів.
- **`models/`** — моделі SQLAlchemy:
  - `store.py` — описує структуру даних для магазинів.
  - `item.py` — визначає модель для товарів.
- **`resources/`** — логіка роботи з HTTP-запитами:
  - `store.py` — обробляє запити, пов’язані з магазинами.
  - `item.py` — обробляє запити, пов’язані з товарами.
- **`schemas.py`** — описує серіалізацію та валідацію даних за допомогою Marshmallow.
- **`db.py`** — конфігурація бази даних SQLAlchemy.
- **`requirements.txt`** — список усіх необхідних залежностей для проекту.

## Автор
Нікіта Сидоров  
Група I-23  
