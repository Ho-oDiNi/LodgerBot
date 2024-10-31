## LodgerBot
В этом проекте реализован телеграм бот (aiogram 3) с дополнительной привязкой к google sheets

# В общем виде архитектура выглядит так:

![image](https://github.com/user-attachments/assets/12467ff8-74ba-4bb5-bbd2-58eb7622b37f)

В основном потоке организована работа со всеми пользователями с разделением их по ролям.

В зависимости от фильтра пользователи делятся на:
 - Администраторов
 - Известных Юзеров
 - Неизвестных Юзеров

И в зависимости от этого фильтра определен роутер по которому пользователю будут предоставлены доступные клавиатуры и возможный функционал .

# ОБЩИЙ ФУНКЦИОНАЛ
Для всех авторизованных пользователей доступны функции, основанные на хранении информации в базе данных:
 - Получение информации о квартире
 - Журнал счетчиков

# ПОЛЬЗОВАТЕЛЬСКИЕ ФУНКЦИИ
У пользователя есть только одна дополнительная функция:
 - Связь с администратором

# ФУНКЦИОНАЛ АДМИНИСТРАТОРА
У администратора есть несколько дополнительных функций:
 - Список оборудования
 - Подсчет коммунальных услуг 
 - Выселение жильцов
 - Заселение жильцов

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

# Config
В Config хранятся ключи и другие секретные данные, необходимые для работы бота

# DB_Utils
Для хранения, изменения, получения данных о квартирах, арендаторах, оборудовании, показаниях счетчиков и прочей информации используется база данных.

Связь таблиц БД:

![image](https://github.com/user-attachments/assets/5d6b2680-8adb-4b4d-a9c0-f4b7acf5f710)

# Scheduler
Scheduler позволяет отправлять уведомления пользователям раз в определенный период:
  - Ежемесячная оплата
  - Оплата коммунальных услуг
  - Смена тарифов коммунальных услуг

# Other
Функции форматирования сообщений и Машина Состояний(FSM)
FSM позволяет боту "запоминать" текущий контекст разговора и действовать в зависимости от состояния, в котором находится пользователь.

Using libs: asyncio aiogram 3 logging apscheduler pygsheets mysqlclient dotenv aiohttp-socks
