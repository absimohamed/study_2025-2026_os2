---
## Front matter
lang: ru-RU
title: Лабораторная работа №9
subtitle: Управление SELinux
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 17 октября 2025

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

Получить навыки работы с контекстом безопасности и политиками SELinux, включая изменение режимов работы, настройку контекстов и управление переключателями.

# Ход выполнения работы

## Просмотр состояния SELinux

![Проверка состояния SELinux](Screenshot_1.png){ #fig:001 width=70% }

## Проверка и изменение режима SELinux

![Изменение режима работы SELinux](Screenshot_2.png){ #fig:002 width=70% }

## Отключение SELinux

![SELinux отключён](Screenshot_4.png){ #fig:004 width=70% }

## Включение и переразметка меток

![Переразметка меток безопасности](Screenshot_6.png){ #fig:006 width=70% }

## Восстановление контекста безопасности

![Восстановление контекста файла /etc/hosts](Screenshot_8.png){ #fig:008 width=70% }

## Настройка контекста веб-сервера

![Назначение контекста каталогу /web](Screenshot_12.png){ #fig:012 width=70% }

## Работа с переключателями SELinux

![Переключатель ftpd_anon_write](Screenshot_14.png){ #fig:014 width=70% }

# Заключение

В ходе лабораторной работы были изучены принципы работы SELinux, изменение его режимов, настройка контекстов безопасности и управление политиками доступа.
