# ADR-07: Использование Kafka в качестве основного брокера сообщений

1. Контекст:
   * В рамках микросервисной архитектуры необходимо обеспечить асинхронное взаимодействие сервисов и обработку событий (например, "новая тренировка", "новый пост", "появление промоакции"). Система должна поддерживать высокую пропускную способность и горизонтальное масштабирование.
   * На рынке есть несколько распространенных решений:
       * RabbitMQ.
       * Kafka.
       * ActiveMQ.
2. Решение:
    * Использовать Apache Kafka в качестве основного брокера сообщений.
3. Статус:
    * Принято.
4. Обоснование:
    * Горизонтальная масштабируемость и пропускная способность: Kafka спроектирован как распределенный журнал событий, позволяющий наращивать количество брокеров и разделов (partitions). Это упрощает поддержку больших объемов данных, когда микросервисы активно публикуют и читают события.
    * Длительное хранение событий: в Kafka можно хранить сообщения выбранное количество времени, что важно для повторной обработки событий, отладки, построения аналитики.
    * Интеграция с Big Data: Kafka хорошо интегрируется с экосистемой обработки больших данных (Apache Spark, Hadoop). Поскольку в системе есть аналитический кластер (DWH, ML), Kafka предоставляет надежный конвейер для стриминга данных.
    * Сообщество и поддержка: Kafka - де-факто стандарт для стриминга данных в крупных системах. Доступно много инструментов, что облегчает администрирование и интеграции.
    * Сравнение с RabbitMQ: RabbitMQ удобнее для классических очередей, RPC-сценариев и простых паттернов. Однако при очень больших объемах данных и необходимости долгосрочного хранения Kafka обычно показывает лучшую масштабируемость и производительность для стриминга.
5. Последствия:
    * Плюсы:
      * Высокая производительность и масштабируемость при работе с большими объемами данных.
      * Удобная интеграция с системами аналитики и стриминговой обработки.
      * Богатая экосистема инструментов.
    * Минусы:
      * Сложнее администрировать, чем классические брокеры вроде RabbitMQ.
      * Большее время обучения команды DevOps и разработчиков (особенно настройки кластера, топиков, retention).
      * Более высокие требования к инфраструктуре (Kafka хранит логи локально).

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
11. Список ADR
    1. [Выбор микросервисной архитектуры](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/adr_01.md)
    2. [Использование контейнеризации (Docker/Kubernetes)](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/adr_02.md)
    3. [Хранение пользовательских данных](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/adr_03.md)
    4. [Выделение БД для аналитики](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/adr_04.md)
    5. [Аутентификация и авторизация (OAuth2 / OpenID Connect)](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/adr_05.md)
    6. [Наблюдаемость (Observability)](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/adr_06.md)
    7. [Использование Kafka в качестве основного брокера сообщений](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/adr_07.md)
12. [Описание сценариев использования приложения](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/use_cases.md)
13. [Базовая архитектура](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/basic_architecture.md)
14. [Основные представления](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/views.md)
15. [Анализ рисков созданной архитектуры, компромиссов](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/architecture_risks.md)
16. [Стоимость владения системой](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/costs.md)