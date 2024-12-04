# Документирование системы обмена книгами

## 1. Структура функциональных возможностей (Mind Map)

```mermaid
mindmap
  root((Система обмена книгами))
    Пользователи
      Регистрация
      Профиль
      Рейтинг
    Заказы:
      Каталог
      Поиск
      Категоризация
      Создание
    Сделки:
      Отклики на заказы
      Согласование выполнения
      История заказов
    Коммуникации
      Чат между пользователями
      Уведомления
      Email-рассылка
    Безопасность
      Аутентификация
      Защита данных
      Модерация контента
```
### Описание:
Эта диаграмма иллюстрирует структуру функциональных возможностей системы обмена книгами. 
### Основные узлы и их значение:

* <u>Пользователи:</u> функционал, связанный с управлением учетными записями, профилями и рейтингами.
* <u>Заказы:</u> функционал работы с созданием, каталогами, поиском и категоризацией заказов.
* <u>Сделки:</u> процесс договора об исполнении заказа включающий предложения, согласования и историю.
* <u>Коммуникации:</u> система взаимодействия между пользователями (чаты, уведомления).
* <u>Безопасность:</u> меры по защите данных, аутентификации и модерации контента.

## 2. Диаграмма путешествия пользователя (User Journey Diagram)

```mermaid
journey
  title Путь пользователя: Первый заказ
  section Регистрация
    Переход на сайт: 5: Новый пользователь
    Заполнение формы: 4: Пользователь
    Подтверждение email: 3: Система
  section Настройка профиля
    Загрузка аватара: 4: Пользователь
    Заполнение информации о себе: 3: Пользователь
  section Выполнение заказа
    Поиск заказа: 5: Пользователь
    Предложение о выполнении: 4: Пользователь
    Подтверждение сделки: 3: Заказчик
  section Завершение заказа
    Изменение статуса заказа: 3: Пользователь
    Оплата: 4: Заказчик
    Подтверждение в системе: 3: Система
    Написание отзыва: 4:Пользователь.
```
### Описание:
Диаграмма описывает ключевые этапы взаимодействия пользователя с системой:

* Регистрация: пользователь создает учетную запись и настраивает свой профиль.
* Поиск заказа: пользователь просматривает каталог, использует поиск и фильтры для выбора заказа.
* Выполнение заказа : пользователь предлагает свою книгу, согласовывает сделку с другим участником.
* Коммуникация: пользователь использует чат для уточнения деталей и оставляет отзыв о партнере.

## 3. Квадрант-граф (Prioritization Quadrant)
```mermaid
quadrantChart
    title Priorities of Functionality Development
    x-axis Easy --> Hard
    y-axis Low Priority --> High Priority

    "User Registration": [0.2, 0.8]
    "Order Catalog": [0.3, 0.7]
    "Order Search": [0.5, 0.9]
    "User Chat": [0.4, 0.6]
    "Deal Approval": [0.7, 0.8]
    "Notifications": [0.6, 0.5]
    "Deal History": [0.4, 0.4]
    "Content Moderation": [0.8, 0.9]
    "User Rating": [0.7, 0.6]
    "Email Notifications": [0.3, 0.3]
    "Authentication": [0.1, 0.9]
    "Data Protection": [0.9, 0.9]
```
### Описание:
Квадрант-граф помогает приоритизировать разработку функций системы. Каждая точка соответствует функционалу:

* Ось X: сложность реализации (от простого к сложному).
* Ось Y: приоритет для пользователей (от низкого к высокому).

## 4. Гит граф (Gitgraph)
```mermaid
gitGraph
    commit id: "v0.1.0: Project initialization"
    commit id: "v0.2.0: Basic client-server interface"
    commit id: "v0.3.0: Database integration"
    
    branch feature-auth
    checkout feature-auth
    commit id: "Add user authentication"
    commit id: "Implement user roles"

    checkout main
    merge feature-auth id: "Merge auth features into main"
    commit id: "v0.4.0: Authentication release"

    branch feature-books
    checkout feature-orders
    commit id: "Add order catalog"
    commit id: "Implement order search"
    commit id: "Add order categorization"

    checkout main
    merge feature-books id: "Merge order features"
    commit id: "v0.5.0: Order management release"

    branch feature-chat
    checkout feature-chat
    commit id: "Add user chat functionality"
    commit id: "Add notifications system"

    checkout main
    merge feature-chat id: "Merge chat features"
    commit id: "v0.6.0: Chat and notifications release"

    branch feature-security
    checkout feature-security
    commit id: "Improve data protection"
    commit id: "Content moderation tools"
    commit id: "Advanced logging for security"

    checkout main
    merge feature-security id: "Merge security improvements"
    commit id: "v0.7.0: Security update release"

    commit id: "v1.0.0: First stable release"
```
### Описание:
 Гит-граф показывает процесс разработки системы через версии:
1. Основная ветка (main): стабильные версии системы.
2. Функциональные ветки: каждая ветка посвящена отдельной функциональности (пользователи, заказы, обмен).
3. Слияния: после завершения работы над веткой, изменения интегрируются в main.
