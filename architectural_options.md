# Архитектурные опции

## Рассмотренные архитектурные опции

|                            | Плюсы                                                                          | Минусы                                                                                                                                                    |
|----------------------------|--------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Монолитная архитектура     | Более быстрая разработка MVP                                                   | Ограниченная масштабируемость при росте нагрузки                                                                                                          |
|                            | Относительно легкое тестирование и развертывание на ранних этапах              | Сложности с поддержкой и развитием, особенно при необходимости интеграции множества сервисов (социальная платформа, тренировки, аналитика, магазин и пр.) |
| Микросервисная архитектура | Высокая масштабируемость за счет независимого развертывания отдельных сервисов | Сложнее организовать коммуникацию между сервисами                                                                                                         |
|                            | Удобство параллельной разработки различными командами                          | Более высокие накладные расходы на DevOps, мониторинг и управление                                                                                        |

## Обоснование выбора

Выбран микросервисный подход с API Gateway / BFF, контейнеризацией (Docker, Kubernetes) и multi-cloud стратегией по следующим причинам:
1. Масштабируемость.
   * Микросервисы позволяют масштабировать ключевые компоненты независимо (например, социальная платформа, сервис тренировок), что особенно важно при глобальном охвате и пиковых нагрузках.
2. Гибкость интеграции.
   * Использование API-first подхода и сервис-меша позволяет легко подключать новые устройства, сторонние сервисы и обеспечивать взаимодействие между различными компонентами.
3. Наблюдаемость и отказоустойчивость.
   * При микросервисной архитектуре легче реализовать централизованное логирование, мониторинг и трассировку, что соответствует одному из основных атрибутов качества.
   * Автоматизированные CI/CD-процессы и оркестрация контейнеров (Kubernetes) обеспечивают высокую отказоустойчивость.
4. Командная разработка.
   * Разделение на независимые сервисы упрощает параллельную работу различных команд, что соответствует требованиям по итеративной разработке и расширению системы.
5. Минимизация vendor lock-in.
   * Многооблачный подход и использование стандартизированных API позволяет избежать привязки к конкретному облачному провайдеру, что снижает риски и обеспечивает гибкость в будущем.

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