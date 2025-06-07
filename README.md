# HTML--
Верстка сайта, базовые основы 
Всем привет тут я расскажу как сделать мини сайт с минимальным функционалом.
Мы будем использовать Bootstrap для верстки и базовые css

Как изменить цвет шапки и текста 
Свой собственный цвет через CSS
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

Как уменьшить кнопку Зарегистрироваться и как уменьшить её размер?

Чтобы уменьшить кнопку «Зарегистрироваться» в Bootstrap по размеру и ширине
нужно учесть, что сейчас стоит w-100, то кнопка занимает всю ширину. Чтобы уменьшить ширину нужно:
1. Убрать w-100
2.<button type="submit" class="btn btn-primary btn-sm" style="width: 150px;">Зарегистрироваться</button>
Или если вам нужно тонко настроить — можно так:
<style>
  .small-button {
    font-size: 14px;
    padding: 6px 12px;
    width: auto; /* или укажи точно */
  }
</style>

<button class="btn btn-primary small-button">Зарегистрироваться</button>
