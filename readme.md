# Тестовое задание на позицию Junior Frontend JS разработчика.

## Задача

Реализовать интерфейс для сервиса хранения файлов.
Необходимо сверстать странички:
- регистрации;
- авторизации;
- личный кабинет пользователя, где можно загружать, отображать (если добавили картинку, то отображать ее привьюшку, если документ, то иконку документа, при клике на файл скачивать его) и удалять файлы. Также в личном кабинете необходимо отобразить счетчик загруженных файлов и добавить возможность выхода из личного кабинета. Всего файлов, которые пользователь может загрузить - 20, максимальный размер загружаемых данных за 1 запрос - 1MБ).

Дизайн интерфейса на ваше усмотрение

### Технические требования

- приложение должно быть написано с использованием React;
- состояние хранить в Redux/Redux toolkit;
- запрещено использовать ui библиотеки и библиотеки для форм наподобии formik;
- комментирование кода приветствуется;
- результат задания должен быть выложен на github, к которому должна быть прикреплена инструкция по запуску проекта.

### Backend

Домен - `https://js-test.kitactive.ru`

Роуты:

- POST - `/api/register` - Регистрация пользователя, принимает `email`, `password`, `name`;
- POST - `/api/login` - Получение токена доступа, принимает `email`, `password`;
- POST - `/api/logout` - Выход. Требует токен доступа;
- GET - `/api/media` - Получение файлов. Требует токен доступа. Выгружает массив файлов (files), каждый объект содержит: `id`, `name`, `fileName`, `mimeType`, `url`, `createdAt`;
- POST - `/api/media/upload` - Загрузка файлов. Требует токен доступа. Принимает массив файлов `files`;
- GET - `/api/media/{id}` - Получение файла. Требует токен доступа.
- DELETE - `/api/media/{id}` - Удаление файла. Требует токен доступа.

Токен передавать в заголовке `Authorization`, со значением `Bearer {token}`
