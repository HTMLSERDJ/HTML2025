# HTML--
Верстка сайта, базовые основы 
<div>Всем привет тут я расскажу как сделать сайт с клоунами.</div>
Мы будем использовать Bootstrap для верстки и базовые css


Для начала обьясню базовые вещи на примере файла регистрации клоунов
И так создайте папку Project и в нем папку public ( В public нужно скидывать все html файлы)

И так у нас есть готовый шаблон в котором мы будем создавать страницу регистрации 

```
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Регистрация — СахарОК</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" />
  <style>


</style>
</head>
<body>


  <script>
  </script>
</body>
</html>
```
<h1>Главная страница</h1>
<h2>Шапка</h2>
шапка состоит из 

```
<nav class="navbar navbar-expand-lg navbar-dark bg-primary">
  
</nav>
```
<div> Класс | Что делает </div>
<div>navbar	         |  Определяет, что это навигационная панель</div>
<div>navbar-expand-lg | Панель будет свернута в "бургер" на экранах меньше lg (≥992px)</div>
<div>navbar-dark	     |  Тёмные цвета для текста (лучше на тёмном фоне)</div>
<div>bg-primary	     |  Фоновый цвет — основной (синий по умолчанию в Bootstrap)</div>

После этого нужно добавить контейнер для того что бы внутрь него поместить обьекты
```
<div class="container-fluid">

</div>
```
container-fluid — контейнер на всю ширину экрана.
Теперь добавим текст логотипа
``` <a class="navbar-brand" href="/">Счастливые клоуны</a>```
navbar-brand — стиль Bootstrap для логотипа/заголовка в шапке.
href="/" — переход на главную страницу.

Теперь нам нужен  блок с навигационными ссылками
```
<div class="" id="">
  <ul class="navbar-nav ms-auto">

  </ul>
</div>
```
Внутри этого блока можно разместить ссылки к примеру
```
<li class="nav-item">
            <a class="nav-link" href="/">Главная</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="/register.html">Регистрация</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/login.html">Вход</a>
          </li>
```
Класс                        	Значение
collapse navbar-collapse	    Позволяет сворачивать меню на маленьких экранах
id="navbarNav"	              Идентификатор, связанный с data-bs-target в кнопке
ul.navbar-nav	Список ссылок, отформатированный как навигационное меню
ms-auto	Выравнивает список вправо (margin-start: auto)
<h3>*Пометка*</h3>
Если хотите выровнить по центру используйте style = 'margin-right...'
Так же 

justify-content-center — центрирует содержимое внутри flex-контейнера.

Убираем ms-auto (иначе будет конфликт: margin-left: auto вытолкнет вправо).

Список (ul.navbar-nav) остаётся без дополнительных отступов.

<h2>Форма</h2>
Ниже представлен контейнер который содержит внутри себя все обьекты и влияет на их внешний вид

```
<div class="container mt-5" style="max-width: 30%;"> 
</div>
```
container — центрирует форму и задаёт ширину.
mt-5 — отступ сверху (margin-top: 3rem).

Ниже форма которая отвечает за хранение внутри себя самих обьектов как кнопка поля для ввода и тд
```
 <form id="registerForm" novalidate>
</form>
```
Дальше в саму форму необходимо вписать поля для ввода 

Пример формы

```
 <div class="container form-container">
    <h2 class="mb-4 text-center">Регистрация</h2>
    <form id="registerForm" novalidate>
      <div class="mb-3">
        <label for="login" class="form-label">Логин</label>
        <input type="text" class="form-control" id="login" required />
        <div id="loginError" class="error-text"></div>
      </div>

      <div class="mb-3">
        <label for="password" class="form-label">Пароль</label>
        <input type="password" class="form-control" id="password" required />
        <div id="passwordError" class="error-text"></div>
      </div>

      <div class="mb-3">
        <label for="fullname" class="form-label">ФИО</label>
        <input type="text" class="form-control" id="fullname" required />
        <div id="fullnameError" class="error-text"></div>
      </div>

      <div class="mb-3">
        <label for="phone" class="form-label">Телефон</label>
        <input type="text" class="form-control" id="phone" placeholder="+7(XXX)-XXX-XX-XX" required />
        <div id="phoneError" class="error-text"></div>
      </div>

      <div class="mb-3">
        <label for="email" class="form-label">Электронная почта</label>
        <input type="email" class="form-control" id="email" required />
        <div id="emailError" class="error-text"></div>
      </div>

      <div class="d-grid">
        <button type="submit" class="btn btn-success">Зарегистрироваться</button>
      </div>

      <div id="submitError" class="error-text mt-3 text-center"></div>
      <div id="successMessage" class="text-success mt-3 text-center"></div>
    </form>
  </div>

```
Можно менять такие формы и требовать разнообразные данные

1.  container mt-5
container — центрирует форму и задаёт ширину.

mt-5 — отступ сверху (margin-top: 3rem).

2.  form-label и form-control
form-label — красиво стилизованный заголовок поля.

form-control — сам элемент ввода (input), растягивается на всю ширину.

3.  required, minlength, type
HTML-валидация:

required — поле обязательно.

minlength="4" — минимум 4 символа (для пароля).

type="email" — браузер сам проверит, что email в правильном формате.

placeholder — показывает пример ввода (например, телефон).

4.  ```<div class="text-danger" id="...Error">```
Это блоки, куда JavaScript будет выводить сообщения об ошибках валидации.
Класс text-danger делает текст красным (Bootstrap стиль для ошибок).

<h2>База данных</h2>
1. Структура проекта
project/
├── server.js
├── routes/
│   └── auth.js
├── models/
│   └── userModel.js
├── db.js
├── package.json
2.

```
npm install express pg bcrypt body-parser
```
3. Нужно создать файл подключения к bd
   <h2>db.js</h2>
```
const { Pool } = require('pg');

const pool = new Pool({
  user: 'postgres',
  host: 'localhost',
  database: 'your_db_name',
  password: 'your_password',
  port: 5432,
});

module.exports = pool;
```
И сам sql запрос
```
CREATE TABLE users (
  id SERIAL PRIMARY KEY,                                -- Уникальный ID
  login VARCHAR(50) UNIQUE NOT NULL,                    -- Уникальный логин
  password_hash TEXT NOT NULL,                          -- Захэшированный пароль
  full_name VARCHAR(100) NOT NULL,                      -- ФИО
  phone VARCHAR(20) NOT NULL CHECK (
    phone ~ '^\+7\(\d{3}\)-\d{3}-\d{2}-\d{2}$'           -- Маска номера
  ),
  email VARCHAR(100) UNIQUE NOT NULL CHECK (
    email ~ '^[^@\s]+@[^@\s]+\.[^@\s]+$'                 -- Простая email-валидация
  ),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP        -- Дата регистрации
);
```
<h2>4. Создаем модель  (userModel.js в папку models )</h2>

   Подключаем файл db
```
const pool = require('../db');
```
Функция для создания нового пользователя в таблице users c SQL-запросом для добавления нового пользователя.
```
async function createUser({ login, passwordHash, fullName, phone, email }) {
  const query = `
    INSERT INTO users (login, password_hash, full_name, phone, email)
    VALUES ($1, $2, $3, $4, $5)
    RETURNING id, login, email`;
  const values = [login, passwordHash, fullName, phone, email];
  
  try {
    const result = await pool.query(query, values);
    return result.rows[0];
  } catch (err) {
    console.error('Ошибка при создании пользователя:', err);
    throw new Error('Ошибка базы данных');
  }
}
```

Так же нужно добавить функцию занят ли логин или почта 
```
 async function isLoginOrEmailTaken(login, email) {
  try {
    const result = await pool.query(
      `SELECT 1 FROM users WHERE login = $1 OR email = $2`,
      [login, email]
    );
    return result.rowCount > 0;
  } catch (err) {
    console.error('Ошибка при проверке логина/email:', err);
    return false;
  }
}
```
Экспорт функций для использования в других модулях 
```
module.exports = { createUser, isLoginOrEmailTaken };
```
 <h2>создаем роутер (auth.js в папку routes)</h2>
Импортируем подключение к базе данных PostgreSQL и тд.

```
const express = require('express');
const bcrypt = require('bcrypt');
const router = express.Router();
const { createUser, isLoginOrEmailTaken } = require('../models/userModel');

```
создаем роутер с валидацией данных.
```
router.post('/register', async (req, res) => {
  try {
    const { login, password, fullname, phone, email } = req.body;

    
    if (!login || !password || !fullname || !phone || !email) {
      return res.status(400).json({ message: 'Заполните все поля.' });
    }

    if (password.length < 4) {
      return res.status(400).json({ message: 'Пароль должен быть не короче 4 символов.' });
    }

    if (!/^[А-Яа-яЁё\s]+$/.test(fullname)) {
      return res.status(400).json({ message: 'ФИО должно содержать только кириллицу и пробелы' });
    }

    if (!/^\+7\(\d{3}\)-\d{3}-\d{2}-\d{2}$/.test(phone)) {
      return res.status(400).json({ message: 'Телефон в формате +7(XXX)-XXX-XX-XX' });
    }

    if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
      return res.status(400).json({ message: 'Некорректный email' });
    }
```
Проверка уникальности логина
```
  const exists = await isLoginOrEmailTaken(login, email);
    if (exists) {
      return res.status(409).json({ message: 'Такой логин или email уже используется.' });
    }
```
   Хеширование пароля и создание пользователя
```
   const passwordHash = await bcrypt.hash(password, 10);
    const user = await createUser({ 
      login, 
      passwordHash, 
      fullName: fullname,
      phone, 
      email 
    });
```
Отправка сообщений и Экспортирт функции,  чтобы их можно было использовать в других модулях
```
 res.status(201).json({ message: 'Пользователь зарегистрирован', user });
  } catch (err) {
    console.error('Ошибка при регистрации:', err);
    res.status(500).json({ message: 'Внутренняя ошибка сервера' });
  }
});

module.exports = router;
```
<h2>Скрипт файла регистрации</h2>
Возвращаемся к файлу RegistrationClowns.html который должен быть в папке public
Для начала подключите все скрипты и откройте тег <script>
  
```
 <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery.mask/1.14.16/jquery.mask.min.js"></script>
 <script>

```
Считывание значений полей формы
```
 const form = document.getElementById('registerForm');

  form.addEventListener('submit', async (e) => {
    e.preventDefault();
```
Очистка сообщений и получение данных  
```
['login', 'password', 'fullname', 'phone', 'email', 'submit'].forEach(id =>
      document.getElementById(id + 'Error').innerText = ''
    );
    document.getElementById('successMessage').innerText = '';

    const login = document.getElementById('login').value.trim();
    const password = document.getElementById('password').value.trim();
    const fullname = document.getElementById('fullname').value.trim();
    const phone = document.getElementById('phone').value.trim();
    const email = document.getElementById('email').value.trim();

    let hasError = false;
```
Так же нужно добавить следующие проверки
Проверка, что логин не пустой,Пароль должен быть не короче 4 символов,ФИО должно содержать только кириллицу и пробелы,Телефон строго в формате +7(XXX)-XXX-XX-XX,Проверка email — базовая валидация по шаблону.

```
 if (!login) {
      document.getElementById('loginError').innerText = 'Введите логин';
      hasError = true;
    }

    if (password.length < 4) {
      document.getElementById('passwordError').innerText = 'Пароль должен быть не менее 4 символов';
      hasError = true;
    }

    if (!/^[А-Яа-яЁё\s]+$/.test(fullname)) {
      document.getElementById('fullnameError').innerText = 'ФИО должно содержать только кириллицу и пробелы';
      hasError = true;
    }

    if (!/^\+7\(\d{3}\)-\d{3}-\d{2}-\d{2}$/.test(phone)) {
      document.getElementById('phoneError').innerText = 'Формат: +7(XXX)-XXX-XX-XX';
      hasError = true;
    }

    if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {
      document.getElementById('emailError').innerText = 'Неверный формат почты';
      hasError = true;
    }

    if (hasError) return;

    try {
      const res = await fetch('/api/register', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ login, password, fullname, phone, email })
      });

      const data = await res.json();

      if (res.ok) {
        document.getElementById('successMessage').innerText = 'Регистрация прошла успешно!';
        form.reset();
      } else {
        console.log('Ошибка с сервера:', data); // ⬅️ ВСТАВЬ ЭТУ СТРОЧКУ
        document.getElementById('submitError').innerText = data.message || 'Ошибка при регистрации';
      }
    } catch (err) {
      document.getElementById('submitError').innerText = 'Сервер недоступен';
    }
  });
```
Использование маски для телефона
```
 $(document).ready(function () {
    $('#phone').mask('+7(000)-000-00-00');
  });
```
<h2>Создание сервера server.js</h2>
нам необходимо в начале кода указать

```
const express = require('express');
const bodyParser = require('body-parser');
```
express — основной фреймворк для создания сервера.
body-parser — библиотека для разбора тела запросов в формате JSON.
<div>После этого создаём экземпляр Express-приложения — объект app, с помощью которого настраивается поведение сервера.</div>

```
const app = express();
```
Подключение маршрутов
```
const authRoutes = require('./routes/auth');
```
Middleware — настройки

```
app.use(bodyParser.json());
app.use(express.static('public'));
app.use('/api', authRoutes);
```
Запуск сервера

```
const PORT = 3000;
app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
   });

  $(document).ready(function () {
    $('#phone').mask('+7(000)-000-00-00');
  });

```
<h2>Осталось установить express и инициализировать проект</h2>
Нужно ввести в корень проекта

```
npm init -y
npm install express
npm install body-parser
npm install bcrypt
npm install pg
```
