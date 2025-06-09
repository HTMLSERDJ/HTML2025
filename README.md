# HTML--
Верстка сайта, базовые основы 
Всем привет тут я расскажу как сделать сайт с клоунами.
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
<div> Класс------+---Что делает </div>
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

Примеры

```
<div class="mb-3">
      <label for="login" class="form-label">Логин</label>
      <input type="text" class="form-control" id="login" required>
      <div class="text-danger" id="loginError"></div>
    </div>


<div class="mb-3">
      <label for="password" class="form-label">Пароль</label>
      <input type="password" class="form-control" id="password" required minlength="4">
      <div class="text-danger" id="passwordError"></div>
    </div>


    <div class="mb-3">
      <label for="fullName" class="form-label">ФИО</label>
      <input type="text" class="form-control" id="fullName" required>
      <div class="text-danger" id="fullNameError"></div>
    </div>

    <div class="mb-3">
      <label for="phone" class="form-label">Телефон</label>
      <input type="text" class="form-control" id="phone" placeholder="+7(XXX)-XXX-XX-XX" required>
      <div class="text-danger" id="phoneError"></div>
    </div>

    <div class="mb-3">
      <label for="email" class="form-label">Email</label>
      <input type="email" class="form-control" id="email" required>
      <div class="text-danger" id="emailError"></div>
    </div>

    <button type="submit" style="margin-left: 37%;" class="btn btn-primary">Зарегистрироваться</button>
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
4. Создаем модель  (userModel.js в папку models )
   Подключаем файл db
```
const pool = require('../db');
```
Функция для создания нового пользователя в таблице users c SQL-запросом для добавления нового пользователя.
```
async function createUser({ login, passwordHash, fullName, phone, email }) {
  const query = 
    INSERT INTO users (login, password_hash, full_name, phone, email)
    VALUES ($1, $2, $3, $4, $5)
    RETURNING id, login, email
  ;
```
Ниже нужно добавить массив значений для 1-5
```  const values = [login, passwordHash, fullName, phone, email]; ```
После выполнение запроса 
```
  const result = await pool.query(query, values);
  return result.rows[0];
```
Так же нужно добавить функцию занят ли логин или почта 
```
 const result = await pool.query(
    `SELECT 1 FROM users WHERE login = $1 OR email = $2`,
    [login, email]
  );
  return result.rowCount > 0;
}
```
Экспорт функций для использования в других модулях 
```
module.exports = { createUser, isLoginOrEmailTaken };
```
5. создаем роутер (auth.js в папку routes)

