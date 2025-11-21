---
## Front matter
lang: ru-RU
title: Лабораторная работа №12
subtitle: Настройки сети в Linux
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 2 ноября 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Основная цель

Получить навыки настройки сетевых параметров системы и управления соединениями с помощью инструментов Linux.

# Ход выполнения работы

## Проверка конфигурации сети

![Вывод команды ip -s link](Screenshot_1.png){ #fig:001 width=70% }

## Анализ таблицы маршрутов и IP-адресов

![Информация о сетевых адресах](Screenshot_2.png){ #fig:002 width=70% }

## Добавление дополнительного IP и проверка

![Добавление дополнительного адреса](Screenshot_4.png){ #fig:004 width=70% }

## Использование ifconfig и ss

![Прослушиваемые порты TCP и UDP](Screenshot_6.png){ #fig:006 width=70% }

## Просмотр и создание соединений

![Текущие соединения nmcli](Screenshot_7.png){ #fig:007 width=70% }

## Переключение режимов

![Переключение обратно на DHCP](Screenshot_9.png){ #fig:009 width=70% }

## Настройка DNS и IP

![Проверка изменений после активации static](Screenshot_10.png){ #fig:010 width=70% }

## Проверка через nmtui

![Просмотр конфигурации static через nmtui](Screenshot_11.png){ #fig:011 width=70% }

## Графический интерфейс настройки сети

![Конфигурация static в графическом интерфейсе](Screenshot_13.png){ #fig:013 width=70% }

# Заключение

В ходе работы изучены инструменты **ip**, **nmcli**, **nmtui** и **ifconfig**, а также конфигурационные файлы Linux.  
Получены практические навыки настройки IP, шлюзов, DNS и проверки состояния сети.  
Освоенные приёмы позволяют эффективно администрировать сетевую инфраструктуру в системах на базе RHEL.
