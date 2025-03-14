# Концептуальная архитектура

![Концептуальная архитектура](assets/concept_architecture.png)

Главные компоненты:
1. API Gateway / BFF.
   * Точка входа для мобильного приложения и веб-сайта. Реализует маршрутизацию запросов к соответствующим сервисам, агрегацию данных.
   * Может дополнительно обеспечивать аутентификацию, авторизацию, фильтрацию и кэширование.
2. Сервис социальной платформы.
   * Управление группами, публикация постов, лента активности, сообщения и уведомления.
   * Отвечает за механизмы геймификации.
3. Сервис тренировок.
   * Ведение журнала тренировок (история, планировщик, уведомления о расписании), сравнение результатов с прошлыми.
4. Сервис аналитики.
   * Расчет и хранение агрегированных метрик: общее время тренировок, прогресс пользователей, сравнение с другими спортсменами.
   * Обеспечивает доступ к дешбордам и подготовку данных для дальнейшего анализа (Data Warehouse/Big Data).
5. Сервис рекомендаций.
   * Персональные рекомендации товаров.
6. Сервис интеграции со сторонними устройствами.
   * Подключение сторонних устройств (датчики ЧСС, шагомеры, фитнес-браслеты).
   * Сбор данных о состоянии пользователя в реальном времени.
7. Сервис интеграции с каталогом товаров.
   * Взаимодействие с уже имеющейся e-commerce системой компании.
8. Сервис промоакций.
   * Управление акциями и предложениями в зависимости от локации, интересов пользователей, сезона и т. д.

## Навигация

1. [Бизнес-цели](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/business_objectives.md)
2. [Функциональные требования](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/functional_requirements.md)
3. [Стейкхолдеры](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/stakeholders.md)
4. [Концептуальная архитектура](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/concept_architecture.md)
5. [Риски реализации](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/implementation_risks.md)
6. [План поэтапной разработки и расширения системы, анализ критически важных компонентов](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/development_plan.md)
7. [Критические бизнес-сценарии](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/critical_business_scenarios.md)
8. [Атрибуты качества](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/quality_attributes.md)
9. [Нефункциональные требования](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/nonfunctional_requirements.md)
10. [Архитектурные опции](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/architectural_options.md)