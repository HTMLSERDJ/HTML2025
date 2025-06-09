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




Как изменить цвет шапки и текста 
Свой собственный цвет через CSS
```
<style>
  .custom-navbar {
    background-color: #663399; /* фиолетовая шапка */
     color: #bb4f4f;  /* фиолетовый текст */
  }
</style>

 <nav class="navbar navbar-expand-lg navbar-dark color_hat">
    <div class="container-fluid">
      <span class="navbar-brand mb-0 h1">Название сайта</span>
    </div>
  </nav>
```
Как уменьшить кнопку Зарегистрироваться и как уменьшить её размер?

Чтобы уменьшить кнопку «Зарегистрироваться» в Bootstrap по размеру и ширине
нужно учесть, что сейчас стоит w-100, то кнопка занимает всю ширину. Чтобы уменьшить ширину нужно:
1. Убрать w-100
2. ``` <button type="submit" class="btn btn-primary btn-sm" style="width: 150px;">Зарегистрироваться</button> ```
Или если вам нужно тонко настроить — можно так:
```
<style>
  .small-button {
    font-size: 14px;
    padding: 6px 12px;
    width: auto; /* или укажи точно */
  }
</style>

<button class="btn btn-primary small-button">Зарегистрироваться</button>
```
В файле Authorization form в принципе все тоже самое!

Остальные файлы похожи, поэтому думаю мы можем перейти к БД
