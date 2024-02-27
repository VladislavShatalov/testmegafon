# Про этот плейбук

## Краткое описание
Плейбук позволяет развернуть базовую конфигурацию Nginx с работой на два хоста.

## Файлы
defaults/main.yml: Определяет переменные по умолчанию.
handlers/main.yml: Обработчики для перезапуска NGINX.
tasks/main.yml: Задачи для установки NGINX и конфигурации.
tasks/test.yml: Задачи для проверки HTTP-запросов.
vars/main.yml: Переменные, которые можно изменить.

## Опции 
nginx_install: Указывает, нужно ли развертывать NGINX (по умолчанию: true).
nginx_config_only: Указывает, нужно ли только обновить конфигурацию NGINX (по умолчанию: false).
nginx_http_port: Порт HTTP-сервера (по умолчанию: 80).
nginx_https_port: Порт HTTPS-сервера (по умолчанию: 443).
nginx_server_names: Список серверных имен (FQDN) для виртуальных хостов.
nginx_config_path: Путь к файлу конфигурации NGINX.

## Суть роли для тестирования 
Ansible роль проверит HTTP-запросы на всех сервер-блоках и выведет сообщение об ошибке, если код ответа не 200.

## Структура
├── defaults
│   └── main.yml
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   ├── main.yml
│   └── test.yml
├── README.md
└── vars
    └── main.yml