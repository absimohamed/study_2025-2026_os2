---
lang: ru-RU
title: Лабораторная работа №4
subtitle: Работа с программными пакетами
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 12 декабря 2025

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

Получить практические навыки работы с репозиториями и менеджерами пакетов **dnf** и **rpm** в операционной системе Rocky Linux.

# Ход выполнения работы

## Переход в режим суперпользователя и просмотр репозиториев

![Просмотр каталога /etc/yum.repos.d и файла репозитория](Screenshot_1.png){ width=75% }

## Список активных репозиториев

![Список активных репозиториев dnf](Screenshot_2.png){ width=75% }

## Поиск и информация о пакете nmap

![Поиск и информация о пакете nmap](Screenshot_3.png){ width=75% }

## Установка пакета nmap

![Установка пакета nmap](Screenshot_4.png){ width=75% }

## Удаление пакета nmap

![Удаление пакета nmap](Screenshot_5.png){ width=75% }

## Список и информация о группах пакетов

![Просмотр групп пакетов](Screenshot_6.png){ width=75% }

## Установка и удаление группы RPM Development Tools

![Установка и удаление группы пакетов](Screenshot_7.png){ width=75% }

## Дополнительные операции с группами пакетов

![Удаление группы пакетов и освобождение места](Screenshot_8.png){ width=75% }

## Просмотр истории операций dnf

![История операций dnf](Screenshot_9.png){ width=75% }

## Проверка пакета lynx и загрузка rpm

![Проверка и загрузка пакета lynx](Screenshot_10.png){ width=75% }

## Расположение исполняемого файла lynx

![Определение расположения lynx](Screenshot_11.png){ width=75% }

## Состав пакета lynx

![Список файлов пакета lynx](Screenshot_12.png){ width=75% }

## Документация пакета lynx

![Документация пакета lynx](Screenshot_13.png){ width=75% }

## Справочное руководство lynx

![Просмотр man-страницы lynx](Screenshot_14.png){ width=75% }

## Запуск текстового браузера lynx

![Работа текстового браузера lynx](Screenshot_15.png){ width=75% }

## Удаление пакета lynx

![Удаление пакета lynx](Screenshot_16.png){ width=75% }

## Установка пакета dnsmasq

![Проверка и установка dnsmasq](Screenshot_17.png){ width=75% }

## Информация о пакете dnsmasq

![Информация о пакете dnsmasq](Screenshot_18.png){ width=75% }

## Состав и документация пакета dnsmasq

![Файлы пакета dnsmasq](Screenshot_19.png){ width=75% }

## Справочное руководство dnsmasq

![Просмотр man-страницы dnsmasq](Screenshot_20.png){ width=75% }

## Скрипты установки и конфигурация dnsmasq

![Скрипты и конфигурационные файлы dnsmasq](Screenshot_21.png){ width=75% }

# Заключение

## Итог

В ходе лабораторной работы были изучены инструменты управления программными пакетами в системе Rocky Linux.  
Освоены операции работы с репозиториями, пакетами и группами пакетов, а также методы анализа содержимого rpm-пакетов и их документации.
