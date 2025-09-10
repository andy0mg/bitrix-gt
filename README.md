# bitrix-gt

Набор скриптов для развёртывания окружения 1C‑Битрикс на чистой системе Linux. Поддерживаются Debian 11/12, CentOS 7 и Astra Linux.

## Скрипты
- [`bitrix_gt.sh`](docs/bitrix_gt.md) — установка «Битрикс: Управление сайтом» (Nginx, Apache, PHP‑FPM, MariaDB).
- [`bitrix24_gt.sh`](docs/bitrix24_gt.md) — развёртывание «Битрикс24» с Redis и push‑сервером.
- [`bitrix_setup_vanilla.sh`](docs/bitrix_setup_vanilla.md) — воспроизводит официальное руководство для Debian 11, готовит минимальное окружение и скачивает установщик.

Каждый скрипт запускается командой вида:
```bash
bash <(curl -sL https://raw.githubusercontent.com/YogSottot/bitrix-gt/master/<имя_скрипта>)
```
Скрипты выполняются от имени `root`, скачивают необходимые пакеты и создают конфигурацию веб‑стека.

## Дополнительные ресурсы
- Проект [ispconfig](https://github.com/Wladimir-N/ispconfig)
- Проект [bitrix-docker/server](https://gitlab.com/bitrix-docker/server)
