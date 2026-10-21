# Практикум

Веб приложение упрощающее организацию производственных практик.

## Технологии

|                                   Frontend                                   | Backend                                                                             |                                Database                                |
| :--------------------------------------------------------------------------: | :---------------------------------------------------------------------------------- | :--------------------------------------------------------------------: |
| <img src="https://skillicons.dev/icons?i=html,css,js&theme=dark&perline=10"> | <img src="https://skillicons.dev/icons?i=php,laravel&theme=dark&perline=10"> | <img src="https://skillicons.dev/icons?i=mysql&theme=dark&perline=10"> |

## Архитектура

```text
├── app/                  # Models, Controllers, Providers
│   ├── Http/             # Контроллеры, Middleware и Форм-реквесты
│   ├── Models/           # Модели базы данных
│   └── Providers/        # Сервис-провайдеры для регистрации служб
├── bootstrap/            # Файлы инициализации фреймворка и кэш конфигурации
├── config/               # Конфигурационные файлы приложения
├── database/             # Скрипты базы данных
│   ├── factories/        # Фабрики для генерации фейковых данных
│   ├── migrations/       # Миграции структуры таблиц
│   └── seeders/          # Сидеры для первоначального наполнения БД
├── public/               # Публичная папка (точка входа index.php, ассеты)
├── resources/            # Код страниц 
│   ├── css/              # Стили
│   ├── js/               # Скрипты
│   └── views/            # Шаблоны интерфейса Blade
├── routes/               # Файлы маршрутизации
│   ├── web.php           # Веб-маршруты
│   └── console.php       # Консольные команды Artisan
├── storage/              # Логи, кэш, сессии
├── tests/                # Автоматизированные тесты
├── .env.example          # Шаблон конфигурации окружения
└── composer.json         # Зависимости PHP проекта
```
<img width="1411" height="827" alt="image" src="https://github.com/user-attachments/assets/4e1df944-7304-4f0d-9604-b57f6026567c" />

