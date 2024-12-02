<h1>Проект "Онлайн платформа торговой сети электроники".</h1> 

<h3>Использованный стек технологий:</h3>

* Python 

* Django

* Django Rest Framework (DRF)

* PostgreSQL 16

<h3>Задание:</h3>

Необходимо реализовать модель сети по продаже электроники.
Сеть должна представлять собой иерархическую структуру из трех уровней:

* завод;
* розничная сеть;
* индивидуальный предприниматель.

Каждое звено сети ссылается только на одного поставщика оборудования (не обязательно предыдущего по иерархии). 
Важно отметить, что уровень иерархии определяется не названием звена, а отношением к остальным элементам сети, 
т. е. завод всегда находится на уровне 0, а если розничная сеть относится напрямую к заводу, минуя остальные звенья, 
ее уровень — 1.

Каждое звено сети должно обладать следующими элементами:
* Название.
* Контакты:
* email,
* страна,
* город,
* улица,
* номер дома.
* Продукты:
  * название,
  * модель,
  * дата выхода продукта на рынок.
* Поставщик (предыдущий по иерархии объект сети).
* Задолженность перед поставщиком в денежном выражении с точностью до копеек.
* Время создания (заполняется автоматически при создании).

Сделать вывод в админ-панели созданных объектов.
  
На странице объекта сети добавить:
* ссылку на «Поставщика»;
* фильтр по названию города;
* admin action, очищающий задолженность перед поставщиком у выбранных объектов.

Используя DRF, создать набор представлений:
CRUD для модели поставщика (запретить обновление через API поля «Задолженность перед поставщиком»).

Добавить возможность фильтрации объектов по определенной стране.

Настроить права доступа к API так, чтобы только активные сотрудники имели доступ к API.

<h3>Установка и запуск приложения:</h3>

* Склонируйте проект на свое устройство.
* Настройте виртуальное окружение и установите зависимости из ***requirements.txt*** .
* Создайте в корне проекта файл ***.env*** и заполните его по образцу из файла .env.sample .
* Примените миграции командой ***python manage.py migrate***
* Для запуска проекта выполните команду ***python manage.py runserver***
* Для создания Администратора выполните команду ***python manage.py createsuperuser***
