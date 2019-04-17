# Web "Hello, world!" in 2019
## Python(Flask), React, Docker  

https://habr.com/ru/post/444446/

![alt-текст](https://habrastorage.org/webt/ul/ne/9v/ulne9vljujdrtxnf-qeqrrux7da.png)

Что мы покроем:

- настройка dev-окружения в docker-compose.
- создание бэкенда на Flask.
- создание фронтенда на Express.
- сборка JS с помощью Webpack.
- React, Redux и server side rendering.
очереди задач с RQ.  

### Intro

Wiki-engine. Карточки оформлены в Markdown. SPA with server-side rendering.  

- Клиент. Сделаем одностраничное приложение (т.е. с переходами между страницами посредством AJAX) на весьма распространённой в мире фронтенда связке React+Redux.
- Фронтенд. Сделаем простенький сервер на Express, который будет рендерить наше React-приложение (запрашивая все необходимые данные в бэкенде асинхронно) и выдавать пользователю.
- Бэкенд. Повелитель бизнес-логики, наш бэкенд будет небольшим Flask-приложением. Данные (наши карточки) будем хранить в популярном документном хранилище MongoDB, а для очереди задач и, возможно, в будущем — кэширования будем использовать Redis.
- Воркер. Отдельный контейнер для тяжёлых задач у нас будет запускаться библиотечкой RQ.  

### Инфраструктура: docker-compose

- MongoDB and Redis
- Backend
- Frontend
- Worker  

### Backend

flask, flask-cors, gevent, gunicorn  

$docker-compose up backend

### Frontend. Express

$docker-compose up frontend

### Frontend. Webpack and React.

- webpack
- babel: compiler  

docker-compose up --build frontend

### MongoDB

