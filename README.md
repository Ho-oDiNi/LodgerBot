## LodgerBot
В этом проекте реализован телеграм бот (aiogram 3.) с дополнительной привязкой к google sheets

# В общем виде архитектура выглядит так:

![image](https://github.com/user-attachments/assets/12467ff8-74ba-4bb5-bbd2-58eb7622b37f)

В основном потоке организована работа со всеми пользователями с разделением их по ролям.

В зависимости от фильтра пользователи делятся на:
 - Администраторов
 - Известных Юзеров
 - Неизвестных Юзеров

И в зависимости от этого фильтра определен роутер по которому пользователю будут предоставлены доступные клавиатуры и возможный функционал .

# Keyboards
Клавиатуры  — это элементы пользовательского интерфейса, которые позволяют боту предоставлять кнопки для взаимодействия с пользователями. 
Они могут быть использованы для упрощения ввода данных, направления пользователей по определенному сценарию или предложения вариантов действий.

Также делятся на:
  - ReplyKeyboards — позволяет предоставлять пользователям готовые варианты ответов или действий
  - InlineKeyboards — позволяет создавать кнопки внутри сообщений бота.

# Handlebars
Хендлеры (обработчики) — это функции или методы, которые вызываются при наступлении определенных событий в боте. 
Хендлеры обрабатывают входящие сообщения, команды, callback-запросы и другие типы событий.

# Callbacks
Callback (Коллбэк) — это функции-обработчики, которые реагируют на определенные действия пользователя, такие как нажатие кнопок в встроенных (inline) клавиатурах. 
Данные функции позволяют боту выполнять изменение данных в БД или отправлять определенные сообщения в ответ на действия пользователя.


Using libs: asyncio aiogram 3 logging apscheduler pygsheets mysqlclient dotenv aiohttp-socks
