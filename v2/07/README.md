**Читать на других языках: [Русский](README.md), [Українська](README.ua.md).**

# Критерии приема

- Создан репозиторий `goit-js-hw-07`
- При сдаче домашней работы есть две ссылки: на исходные файлы и рабочую
  страницу на `GitHub Pages`
- При посещении рабочей страницы задания, в консоли нету ошибок и предупреждений
- Имена переменных и функций понятные, описательные
- Код отформатирован с помощью `Prettier`

## Стартовые файлы

- В папке [src](./src) ты найдешь стартовые файлы с базовой разметкой и готовыми
  стилями. Скопируй их себе в проект. Для этого скачай весь этот репозиторий как
  архив.
- В файле `gallery-items.js` есть массив `galleryItems`, который содержит
  объекты с информацией о изображениях: маленькое (превью), оригинальное
  (большое) и описание. Мы уже подключили его к каждому из JS-файлов проекта.

## Задание 1 - галерея

Создай галерею с возможностью клика по её элементам и просмотра полноразмерного
изображения в модальном окне. Превью результата смотри
[по ссылке](https://take.ms/ZvBD0E).

Выполняй это задание в файлах `01-gallery.html` и `01-gallery.js`. Разбей его на
несколько подзадач:

1. Создание и рендер разметки по массиву данных `galleryItems` и
   предоставленному шаблону элемента галереи.
2. Реализация делегирования на `ul.js-gallery` и получение `url` большого
   изображения.
3. Подключение скрипта и стилей библиотеки модального окна
   [basiclightbox](https://basiclightbox.electerious.com/). Используй
   [CDN сервис jsdelivr](https://www.jsdelivr.com/package/npm/basiclightbox?path=dist)
   и добавь в проект ссылки на минифицированные (`.min`) файлы библиотеки.
4. Открытие модального окна по клику на элементе галереи. Для этого ознакомься с
   [документацией](https://github.com/electerious/basicLightbox#readme) и
   [примерами](https://basiclightbox.electerious.com/).
5. Замена значения атрибута `src` элемента `<img>` в модальном окне перед
   открытием. Используй готовую разметку модального окна с изображением из
   примеров библиотеки [basiclightbox](https://basiclightbox.electerious.com/).

### Разметка элемента галереи

Ссылка на оригинальное изображение должна храниться в data-атрибуте `source` на
элементе `<img>`, и указываться в `href` ссылки. Не добавляй другие HTML теги
или CSS классы кроме тех, что есть в этом шаблоне.

```html
<li class="gallery__item">
  <a
    class="gallery__link"
    href="https://cdn.pixabay.com/photo/2010/12/13/10/13/tulips-2546_1280.jpg"
  >
    <img
      class="gallery__image"
      src="https://cdn.pixabay.com/photo/2010/12/13/10/13/tulips-2546__340.jpg"
      data-source="https://cdn.pixabay.com/photo/2010/12/13/10/13/tulips-2546_1280.jpg"
      alt="Tulips"
    />
  </a>
</li>
```

Обрати внимание на то, что изображение обернуто в ссылку, а значит при клике по
умолчанию пользователь будет перенаправлен на другую страницу. Запрети это
поведение по умолчанию.

### Кнопка закрытия

> ⚠️ Следующий функционал не обязателен при сдаче задания, но будет хорошей
> дополнительной практикой.

Добавь закрытие модального окна по нажатию клавиши `Escape`. Сделай так, чтобы
прослушивание клавиатуры было только пока открыта модалка.

Добавь закрытие модалки при клике по кнопке в правом верхнем углу вьюпорта.
Библиотека не предоставляет эту кнопку, только метод закрытия окна - сделай её
самостоятельно. Реализацию такой кнопки можно посмотреть в примерах библиотеки
открыв инструменты разработчика. Подходящую иконку ты найдешь в папке `images`.

## Задание 2 - библиотека `SimpleLightbox`

Сделай такую же галерею как в первом задании, но используя библиотеку
[SimpleLightbox](https://simplelightbox.com/), которая возьмет на себя обработку
кликов по изображениям, открытие и закрытие модального окна, а также
пролистывание изображений при помощи клавиатуры.

Выполняй это задание в файлах `02-lightbox.html` и `02-lightbox.js`. Разбей его
на несколько подзадач:

1. Создание и рендер разметки по массиву данных `galleryItems` и
   предоставленному шаблону элемента галереи.
2. Подключение скрипта и стилей библиотеки используя
   [CDN сервис cdnjs](https://cdnjs.com/libraries/simplelightbox). Необходимо
   добавить ссылки на два файла: `simple-lightbox.min.js` и
   `simple-lightbox.min.css`.
3. Инициализация библиотеки после того как элементы галереи созданы и добавлены
   в `ul.js-gallery`. Для этого ознакомься с документацией
   [SimpleLightbox](https://simplelightbox.com/) - в первую очередь секции
   `Usage` и `Markup`.

### Подписи

> ⚠️ Следующий функционал не обязателен при сдаче задания, но будет хорошей
> дополнительной практикой.

Посмотри секцию `Options` и добавь отображение подписей к изображениям из
атрибута `alt`. Пусть подпись будет сверху и появляется через 250 миллисекунд
после открытия изображения.