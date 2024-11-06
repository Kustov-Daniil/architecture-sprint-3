1.  **Изучите функциональность монолитного приложения:**
    
    *   **Управление отоплением.** Пользователи могут удалённо включать/выключать отопление в своих домах.
        
    *   **Мониторинг температуры.** Система получает данные о температуре с датчиков, установленных в домах. Пользователи могут просматривать текущую температуру в своих домах через веб-интерфейс.
        
2.  **Проанализируйте архитектуру монолитного приложения:**
    
    *   **Язык программирования:** Java
        
    *   **База данных:** PostgreSQL
        
    *   **Архитектура:** Монолитная, все компоненты системы (обработка запросов, бизнес-логика, работа с данными) находятся в рамках одного приложения.
        
    *   **Взаимодействие:** Синхронное, запросы обрабатываются последовательно.
        
    *   **Масштабируемость:** Ограничена, так как монолит сложно масштабировать по частям.
        
    *   **Развёртывание:** Требует остановки всего приложения.
        

3.  **Определение доменов и границ контекстов**
    *  **Управление отоплением (Heating Control):** Обработка запросов на включение и выключение отопления. Управляет состоянием устройства отопления в домах.
    
    *  **Мониторинг температуры (Temperature Monitoring):** Получает и обрабатывает данные о температуре из установленных датчиков, хранит их и предоставляет доступ для пользователей.
        
    *  **Управление устройствами (Device Management):** Домен для подключения и управления устройствами. В будущем он будет ответственен за поддержку и настройку различных устройств (например, освещение, камеры, ворота).
        
    *  **Аутентификация и авторизация (Authentication & Authorization):** Обеспечивает безопасность, управляет доступом пользователей к системе, их правами и сессиями.
    
    *  **Управление уведомлениями (Notification Management):** Домен для обработки и отправки уведомлений пользователям о статусе системы, например, уведомлений о текущем статусе температурного режима или о том, что датчик вышел из строя.
    

4.  **Анализ проблем монолитного приложения**

Монолитная архитектура приложения имеет несколько недостатков, особенно в контексте целей по расширению функциональности и масштабирования

* **Сложность масштабирования:** С монолитной структурой невозможно гибко масштабировать отдельные компоненты системы.
        
* **Ограниченная гибкость и расширяемость:** Сложность добавления новой функциональности (например, управление другими устройствами) и поддержки системы.
        
* **Проблемы с развёртыванием и обновлениями:** Развёртывание новой версии требует остановки всего приложения, что может приводить к простоям.
        
* **Низкая отказоустойчивость:** В случае отказа одной функции, например, мониторинга температуры, может нарушиться работа всей системы.
        
* **Зависимость от синхронного взаимодействия:** Ограничения, связанные с использованием синхронных операций.
    

Текущая монолитная архитектура представляет собой ограничение для реализации бизнес-целей компании, поскольку затрудняет внедрение новых функций и управление масштабированием.