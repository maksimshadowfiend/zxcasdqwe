# Лабораторная работа на тему: система журналирования в операционных системах Linux
## Настроим системное время:
timedatectl list-timezones

![alt text](image.png)

sudo timedatectl set-timezone zone

![alt text](image-1.png)

journalctl

![alt text](image-2.png)

## Предыдущие загрузки

sudo mkdir -p /var/log/journal

sudo nano /etc/systemd/journald.conf

![alt text](image-3.png)

## Временные окна

journalctl --since "2022-01-10 17:15:00"

![alt text](image-4.png)

journalctl --since yesterday

![alt text](image-5.png)

# Фильтр по значимости
## По единицам

journalctl -u nginx.service

journalctl -u nginx.service --since today

id -u www-user

journalctl _UID=33 --since today

![alt text](image-6.png)
## По пути компонента

journalctl /usr/bin/bash

![alt text](image-8.png)

## Отображение сообщений ядра

journalctl -k

![alt text](image-9.png)

journalctl -k -b -5

![alt text](image-10.png)

## По приоритету

journalctl -p err –b

![alt text](image-11.png)


# Выводы
Мы разобрали, как использовать утилиту journalctl в основных режимах. Она весьма полезна для системных администраторов за счет гибкой фильтрации данных при чтении журналов. Расширение функций осуществляется за счет применения различных опций, основные из которых рассмотрели в текущей работе