# Скрипт `bitrix_setup_vanilla.sh`

Скрипт воспроизводит руководство «Настройка окружения для Debian 11» и готовит минимальное окружение для самостоятельной установки Битрикс. Разворачиваются Nginx, Apache, MariaDB, Redis и push‑сервер.

## Запуск
```bash
bash <(curl -sL https://raw.githubusercontent.com/YogSottot/bitrix-gt/master/bitrix_setup_vanilla.sh)
```
Нужны права root и подключение к сети.

## Основные шаги
1. **Установка пакетов** (`installPkg`) – добавляются репозитории Sury PHP, ставятся веб‑серверы, PHP 8.2, MariaDB, Redis, Node.js, npm и прочие утилиты.
2. **Развёртывание конфигурации** (`deployConfig`) – копируются эталонные конфиги из документации Bitrix, настраивается firewall nftables, конфигурируются Apache и Nginx, подготавливаются Redis и push‑сервер.
3. **Настройка базы данных** (`dplMYSQL`) – создаётся база `bitrix` и пользователь, включается служба MariaDB.
4. **Подготовка инсталлятора** (`deployInstaller`) – в `/var/www/html/bx-site` скачиваются `bitrixsetup.php` и `restore.php`, создаются файлы `dbconn.php` и `.settings.php`.
5. **Финальная проверка** – скрипт убеждается, что по адресу `http://<ip>/bitrixsetup.php` доступен установочный файл.

## Результат
Получается "чистое" окружение Debian 11 с предустановленными службами и готовым к запуску установщиком Битрикс.
