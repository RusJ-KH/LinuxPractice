# Введение
Данная практика посвещена базовым принципам администрирования Linux. Для выполнения практики необходимо развернуть 3 виртуальные машины Linux.

Как пример, можно использовать Virtual Box + Ubuntu Server 20.04.

# Задание
Для выполнения данного задания необходимо:
1.	Развернуть три виртуальные машины Linux, согласно схеме ниже


![info](./assets/images/Schema.png)


2.	Linux A
    1. Сконфигурировать Hostname следующим образом: <your_surname>_server
    2. Создать пользователя <your_surname>_1
    3. Сконфигурировать виртуальный интерфейс со следующим ip адресом: 192.168.<день рождения>.10/24 с помощью утилиты netplan
    4. Развернуть Http сервер на виртуальной машине на порту 5000. Необходимо реализовать минимум три эндпоинта (запрос /get, /post, /put) 
3.	Linux B
    1. Сконфигурировать Hostname следующим образом: <your_surname>_gateway
    2. Создать пользователя <your_surname>_2
    3. Сконфигурировать 2 виртуальных интерфейс со следующими ip адресом: 192.168.<день рождения>.1/24,  192.168.<месяц рождения>.10/24 с помощью утилиты /etc/network/interfaces
    4. С помощью утилит ip route и iptables настроить маршрут пакетов от Linux A до C. Должны быть запрещены все пакеты, кроме http пакетов через порт 5000
    5. Запустить программу tcpdump с фильтрацией по портам 5000
4.	Linux C
    1. Сконфигурировать Hostname следующим образом: <your_surname>_client
    2. Создать пользователя <your_surname>_3
    3. Сконфигурировать виртуальный интерфейс со следующим ip адресом: 192.168.<месяц рождения>.100/24 любой утилитой
    4. С помощью команды curl на машине C послать 3 запроса на машину А в http сервер (/get, /post, /put)

5. Сделать скриншоты всех этапов задания
6. Оформить отчет в виде Markdown файла. Приложить конфигурационные файлы в репозиторий


Репозиторий оформить следующим образом:
- application - исходный код http сервера
- configs - конфигурационные файлы сетевых настроек виртуальных машин
- report.md - Отчет markdown


P.S.
Если не получилось использовать разные утилиты для настройки сети, используйте netplan