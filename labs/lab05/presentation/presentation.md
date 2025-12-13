---
## Front matter
lang: ru-RU
title: Лабораторная работа №5
subtitle: Управление системными службами
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 12 декабря 2025

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

Получить практические навыки управления системными службами и целями загрузки
в операционной системе Linux с использованием менеджера **systemd**. :contentReference[oaicite:0]{index=0}

# Ход выполнения работы

## Управление сервисами

![Проверка статуса vsftpd](Screenshot_1.png){ #fig:001 width=70% }

## Установка сервиса vsftpd

![Установка vsftpd](Screenshot_1.png){ #fig:002 width=70% }

## Запуск сервиса vsftpd

![Запуск и статус vsftpd](Screenshot_2.png){ #fig:003 width=70% }

## Управление автозапуском

![Enable и disable vsftpd](Screenshot_3.png){ #fig:004 width=70% }

## Символические ссылки systemd

![Список сервисов автозапуска](Screenshot_4.png){ #fig:005 width=70% }

## Зависимости сервиса

![Зависимости vsftpd](Screenshot_5.png){ #fig:006 width=70% }

## Firewalld и iptables

![Статус firewalld и iptables](Screenshot_6.png){ #fig:007 width=70% }

## Конфигурация firewalld

![Файл firewalld.service](Screenshot_7.png){ #fig:008 width=70% }

## Конфигурация iptables

![Файл iptables.service](Screenshot_8.png){ #fig:009 width=70% }

## Маскирование iptables

![Маскирование iptables](Screenshot_9.png){ #fig:010 width=70% }

## Просмотр изолируемых целей

![Список изолируемых целей](Screenshot_10.png){ #fig:011 width=70% }

## Режим восстановления

![Rescue mode](Screenshot_11.png){ #fig:012 width=70% }

## Текстовый режим

![multi-user.target](Screenshot_12.png){ #fig:013 width=70% }

## Графический режим

![graphical.target](Screenshot_13.png){ #fig:014 width=70% }

# Заключение

В ходе лабораторной работы были изучены механизмы управления сервисами и целями
в системе **systemd**. Освоены навыки установки, запуска, добавления в автозапуск,
анализа зависимостей и разрешения конфликтов юнитов. Полученные знания позволяют
эффективно администрировать службы и управлять процессом загрузки Linux-систем. 
