---
## Front matter
lang: ru-RU
title: Лабораторная работа №13
subtitle: Фильтр пакетов. Управление брандмауэром firewalld
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 07 ноября 2025
toc: false
slide_level: 2
aspectratio: 169
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Основная цель

Получить навыки настройки пакетного фильтра в Linux с использованием **firewall-cmd** и **firewall-config**.

# Ход выполнения

## Управление через firewall-cmd

![Просмотр зон](Screenshot_1.png){ #fig:001 width=70% }

## Просмотр доступных сервисов

![Просмотр конфигурации зоны public](Screenshot_2.png){ #fig:002 width=70% }

## Добавление сервиса VNC

![Добавление VNC-сервера](Screenshot_3.png){ #fig:003 width=70% }

## Перезапуск службы firewalld

![VNC отсутствует после перезапуска](Screenshot_4.png){ #fig:004 width=70% }

## Добавление vnc-server постоянно

![VNC добавлен после reload](Screenshot_5.png){ #fig:005 width=70% }

## Добавление порта 2022

![Добавление порта 2022](Screenshot_6.png){ #fig:006 width=70% }

## Включение сервисов в GUI

![Включение служб в GUI](Screenshot_7.png){ #fig:007 width=70% }

## Добавление порта через GUI

![Добавление порта 2022 UDP](Screenshot_8.png){ #fig:008 width=70% }

## Применение конфигурации

![Изменения применены](Screenshot_9.png){ #fig:009 width=70% }

## Добавление дополнительных служб

![Службы добавлены](Screenshot_10.png){ #fig:010 width=70% }

# Заключение

В ходе работы были получены практические навыки:

- управления сетевой фильтрацией с использованием **firewall-cmd**;
- добавления сервисов и портов во временную и постоянную конфигурацию;
- использования графического интерфейса **firewall-config**.

Получены важные навыки администрирования сетевой безопасности в Linux.
