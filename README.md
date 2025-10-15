# DjangoCoursesShop 🛒📚

Онлайн-магазин обучающих курсов, созданный на Django с REST API через Tastypie.  
Позволяет просматривать курсы, фильтровать по категориям, добавлять новые курсы через API и управлять ими через админку.

---

## 🚀 Быстрый старт

### 1. Клонируем репозиторий

```bash
git clone https://github.com/IlyaSv1/DjangoCoursesShop.git
cd DjangoCoursesShop
```

---

### 2. Устанавливаем зависимости
```bash
pip install pipenv
pipenv install
pipenv shell
```

---

### 3. Применяем миграции
```bash
python manage.py migrate
```

---

### 4. Запускаем сервер
```bash
python manage.py runserver
```
Откройте в браузере:
http://127.0.0.1:8000/

---

### 🧰 Технологии и стек
- Python 3.11+
- Django 4.x
- Django Tastypie (REST API)
- Bootstrap 5 (frontend)
- SQLite (для разработки)
- Pipenv (управление зависимостями)

---

### 📂 Структура проекта
```bash
DjangoCoursesShop/
├── base/                 # Настройки проекта
├── shop/                 # Приложение магазина
│   ├── models.py         # Модели Category и Course
│   ├── views.py          # index и single_course
│   ├── urls.py           # Маршруты приложения
│   └── admin.py          # Кастомизация админки
├── api/                  # REST API через Tastypie
│   ├── models.py         # Ресурсы Course и Category
│   ├── authentication.py # Кастомная аутентификация
│   └── urls.py           # Маршруты API
├── templates/
│   ├── base.html         # Базовый шаблон
│   └── shop/
│       ├── courses.html
│       └── single_course.html
├── manage.py
├── Pipfile
└── db.sqlite3
```

---

### 🖥 Web-интерфейс
/ — список всех курсов в таблице: Title, Category, Price, Students Quantity, кнопка Buy.

/<course_id> — детальный просмотр курса с основной информацией и кнопкой Buy.

Навигация: ссылка на главную страницу, админку (/admin/) и API (/api/v1/).

---

### 🔗 API (Tastypie)
| Метод   | URL                      | Описание                  |
|---------|--------------------------|---------------------------|
| GET     | `/api/v1/categories/`    | Список всех категорий     |
| GET     | `/api/v1/courses/`       | Список всех курсов        |
| POST    | `/api/v1/courses/`       | Создать новый курс        |
| DELETE  | `/api/v1/courses/<id>/`  | Удалить курс по ID        |

Для POST и DELETE используется кастомная аутентификация CustomAuthentication. GET-запросы открыты для всех.
