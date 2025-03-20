# ADR-05: Аутентификация и авторизация (OAuth2 / OpenID Connect)

1. Контекст:
   * Система должна иметь безопасный и удобный способ авторизации, в том числе SSO и Yandex/VK/Google/Apple.
2. Решение:
   * Использовать стандарты OAuth2 / OpenID Connect для аутентификации и JWT-токены для защищенных ресурсов.
3. Статус:
   * Принято.
4. Обоснование:
   * Широкая поддержка внешних провайдеров, легко интегрировать авторизацию через Yandex/VK/Google/Apple.
   * Поддержка протоколов безопасности, масштабируемое решение для микросервисной архитектуры.
5. Последствия:
   * Нужно внедрить сервис авторизации (Auth), обеспечить ротацию ключей, настройку защищенного хранения токенов.
   * Обеспечить дополнительные механизмы (например, MFA) для повышенной безопасности.

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