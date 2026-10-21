# Практикум

Веб приложение упрощающее организацию производственных практик.

## Технологии

|                                   Frontend                                   | Backend                                                                             |                                Database                                |
| :--------------------------------------------------------------------------: | :---------------------------------------------------------------------------------- | :--------------------------------------------------------------------: |
| <img src="https://skillicons.dev/icons?i=html,css,js&theme=dark&perline=10"> | <img src="https://skillicons.dev/icons?i=php,laravel&theme=dark&perline=10"> | <img src="https://skillicons.dev/icons?i=mysql&theme=dark&perline=10"> |

## Запуск
1. Клонируйте репозиторий
    ```bash
    git clone https://github.com/miragiee/praktikum
    ```
2. Запустите следующие модули в Open Server Panel 6
    - Apache
    - PHP 8.5
    - MySQL 8.4
3. Откройте терминал в папке проекта и пропишите команды:
   ```bash
   composer install
   ```
   ```bash
   npm install
   ```
4. Затем заполните базу данных
   ```bash
   php artisan migrate
   ```
   ```bash
   php artisan db:seed
   ``` 
5. Запустите приложение, прописав в терминале
   ```bash
   npm run dev
   ```

## Архитектура
### Структура проекта
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
### База данных
<img width="1267" height="792" alt="image" src="https://github.com/user-attachments/assets/8bb4cad2-bd96-4312-a3bf-fc44930d6014" />


