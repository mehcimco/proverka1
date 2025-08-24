[ШАБЛОН 1.html](https://github.com/user-attachments/files/21957479/1.html)
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
<title>Меню выбора</title>
<style>
  :root{
    /* управляем масштабом шрифтов/кнопок */
    --max-width: 520px;
    --bg: #ffffff;
    --item-bg: #f6f6f6;
    --item-bg-hover: #eaeaea;
    --text: #111;
    --gap: 1rem;
  }

  /* Сброс */
  html,body{
    height:100%;
    margin:0;
    padding:0;
    background:var(--bg);
    font-family: Inter, Roboto, Arial, sans-serif;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    box-sizing:border-box;
  }
  *,*::before,*::after{box-sizing:inherit}

  /* Основной контейнер, центрирует контент на экране */
  .page {
    min-height:100vh; /* занимает весь экран */
    display:flex;
    align-items:center;
    justify-content:center;
    padding: calc(env(safe-area-inset-top, 0) + 20px) calc(env(safe-area-inset-right, 0) + 16px) calc(env(safe-area-inset-bottom, 0) + 20px) calc(env(safe-area-inset-left, 0) + 16px);
  }

  /* Меню — ограничивает ширину на больших экранах, растягивается на мобильных */
  .menu {
    width: min(var(--max-width), 100%);
    display:flex;
    flex-direction:column;
    gap: var(--gap);
    align-items:stretch;
    justify-content:center;
    /* небольшой фон/рамка для контраста (можно убрать) */
    background: transparent;
  }

  /* Кнопки/пункты меню — большие удобные области для касания */
  .menu a {
    display:block;
    text-decoration:none;
    color: var(--text);
    background: var(--item-bg);
    padding: clamp(12px, 3.5vh, 20px) clamp(16px, 4vw, 28px);
    font-size: clamp(18px, 3.6vw, 22px);
    text-align:center;
    border-radius: 12px;
    border: 1px solid rgba(0,0,0,0.06);
    box-shadow: 0 6px 18px rgba(0,0,0,0.04);
    transition: transform .08s ease, background-color .12s ease, box-shadow .12s ease;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
  }
  .menu a:active { transform: translateY(1px); }
  .menu a:hover { background: var(--item-bg-hover); }

  /* На очень узких экранах (смартфоны) — меню занимает почти весь видимый экран,
     кнопки становятся больше и равномерно центрируются.
     Мы НЕ скрываем адресную строку браузера (не используем overflow:hidden),
     чтобы не ломать поведение браузера. */
  @media (max-width: 600px) {
    .page {
      /* центрируем по вертикали, но даём меню высоту ровно видимой области */
      align-items: center;
      justify-content: center;
      padding: calc(env(safe-area-inset-top, 0) + 10px) calc(env(safe-area-inset-right, 0) + 8px) calc(env(safe-area-inset-bottom, 0) + 10px) calc(env(safe-area-inset-left, 0) + 8px);
    }

    .menu {
      width: 100%;
      /* чтобы кнопки визуально занимали центральную колонку и не требовали скролла:
         высота меню подстраивается под экран, пункты центрируются внутри него */
      max-height: calc(100vh - (env(safe-area-inset-top, 0) + env(safe-area-inset-bottom, 0) + 20px));
      justify-content: center;
      gap: 0.8rem;
      padding: 6px 0;
    }

    .menu a {
      border-radius: 10px;
      box-shadow: none;
      margin: 0 8px;
      font-weight: 500;
    }
  }

  /* Доступность: фокус-стиль для клавиатуры */
  .menu a:focus {
    outline: 3px solid rgba(0,120,212,0.18);
    outline-offset: 3px;
  }

  /* Маленькие экраны планшетов/вертикальные раскладки — чуть уменьшить максим-ширину */
  @media (max-width:420px) {
    :root { --max-width: 420px; }
  }

</style>
</head>
<body>

  <div class="page">
    <nav class="menu" aria-label="Главное меню">
      <!-- Замените href на ваши реальные файлы.
           Пример: href="osnastka.html" — файл в той же папке.
           Или: href="pages/osnastka.html" — внутри папки pages. -->
      <a href="osnastka.html">Оснастка</a>           <!-- ← вставьте ссылку -->
      <a href="instrument.html">Инструмент</a>       <!-- ← вставьте ссылку -->
      <a href="toollist.html">TOOL LIST</a>          <!-- ← вставьте ссылку -->
      <a href="video.html">Видео обработки</a>       <!-- ← вставьте ссылку -->
    </nav>
  </div>

</body>
</html>
