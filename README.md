# HTML--
Верстка сайта, базовые основы 
```
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Регистрация</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- Bootstrap CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body, html {
      height: 100%;
    }
    .main-content {
      min-height: calc(100vh - 56px); /* 56px — высота navbar */
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #f8f9fa;
    }
  </style>
</head>
<body>

  <!-- Шапка -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <div class="container-fluid">
      <span class="navbar-brand mb-0 h1">Название сайта</span>
    </div>
  </nav>

  <!-- Центрированная форма -->
  <div class="main-content">
    <div class="card shadow rounded-4 p-4" style="width: 100%; max-width: 400px;">
      <h4 class="text-center mb-4">Регистрация</h4>
      <form>
        <div class="mb-3">
          <label for="name" class="form-label">Имя</label>
          <input type="text" class="form-control" id="name" placeholder="Введите ваше имя">
        </div>
          <div class="mb-3">
          <label for="second_name" class="form-label">Фамилия</label>
          <input type="text" class="form-control" id="second_name" placeholder="Введите вашу фамилию">
        </div>
        <div class="mb-3">
          <label for="email" class="form-label">Электронная почта</label>
          <input type="email" class="form-control" id="email" placeholder="Введите email">
        </div>
        <div class="mb-3">
          <label for="password" class="form-label">Пароль</label>
          <input type="password" class="form-control" id="password" placeholder="Введите пароль">
        </div>
        <button type="submit" class="btn btn-primary w-100">Зарегистрироваться</button>
      </form>
    </div>
  </div>

  <!-- Bootstrap JS -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
