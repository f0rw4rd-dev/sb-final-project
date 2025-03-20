# Анализ рисков созданной архитектуры, компромиссов

## Риски

1. Сложность микросервисной архитектуры.
   * Описание: при большом количестве сервисов усложняется координация, конфигурация, деплой, а также мониторинг и поиск ошибок.
   * Последствия: возможное увеличение времени на онбординг разработчиков, рост операционных расходов (DevOps/SRE-команда, инструменты логирования и мониторинга).
   * Защитные меры: автоматизация CI/CD, использование Service Mesh для единого управления сетевыми политиками, централизованные средства логирования (ELK/Loki) и мониторинга (Prometheus/Grafana).
2. Зависимость от облачных провайдеров и сервисов.
   * Описание: система активно использует облачные инструменты (Kubernetes, Managed DB, Object Storage, Kafka и т. п.). При смене провайдера или изменении тарифов возможны серьезные накладные расходы.
   * Последствия: повышенный риск vendor lock-in, сложная миграция в другой облачный стек.
   * Защитные меры: использовать максимально абстрагированные решения (Kubernetes как базис, Terraform/Helm для инфраструктуры), многокластерный/мультиоблачный подход, планирование бюджетов на случай роста тарифов.
3. Высокие требования к безопасности и конфиденциальности.
   * Описание: обработка персональных данных и фитнес-метрик может подпадать под регуляцию (GDPR, HIPAA, CCPA). Нарушение требований влечет штрафы и ухудшение репутации.
   * Последствия: необходимость внедрения процессов комплаенса, дополнительная проверка кода и инфраструктуры, выделенный бюджет на аудит и тесты.
   * Защитные меры: регулярные аудиты, пен-тест, внедрение Service Mesh с mTLS, шифрование данных в DB (TDE/column-level), RBAC, логирование доступа и соблюдение "Privacy by design".
4. Асинхронная коммуникация и Eventual Consistency.
   * Описание: при микросервисном подходе часть операций выполняется асинхронно (Kafka). Есть риск неконсистентности данных, если события задерживаются или теряются.
   * Последствия: пользователи могут замечать несоответствие (например, тренировка отобразилась, но уведомление о достижении пришло позже), повышается сложность отладки.
   * Защитные меры: настройка надежной доставки (at-least-once, ретрансляция), паттерны Saga/Compensation, мониторинг процессов в очередях, хорошая трассировка (Jaeger/Zipkin).
5. Высокая нагрузка во время массовых соревнований.
   * Описание: резкие пики нагрузки (десятки тысяч одновременных пользователей) могут перегружать API Gateway, DBs или Message Broker.
   * Последствия: возможные задержки, ошибки (HTTP 5xx). Отрицательный имиджевый эффект при публичных мероприятиях.
   * Защитные меры: горизонтальное автоскейлинг сервисов и брокеров, CDN для статических ресурсов, механизмы rate limiting, нагрузочное тестирование в условиях, близких к реальным.

## Компромиссы

1. Микросервисы vs монолит.
   * Микросервисы дают гибкую масштабируемость и независимость команд, но увеличивают сложность инфраструктуры и DevOps-поддержки.
   * Компании пришлось инвестировать в Service Mesh, CI/CD, обучать команды.
2. Собственный хостинг vs Managed Cloud.
   * Managed-сервисы (базы данных, Kafka) ускоряют разработку, но повышают риск зависимости от провайдера (vendor lock-in).
   * Возможно, со временем часть сервисов вынесут в частное облако (гибридная стратегия).
3. Асинхронные события vs синхронные вызовы.
   * Асинхронность разгружает сервисы и повышает масштабируемость, но приводит к Eventual Consistency.
   * Важно четко определить, какие операции должны быть транзакционными и где допустимы задержки.
4. Multi-cloud стратегия.
   * Позволяет снизить риски привязки к одному провайдеру, но усложняет управление (разные типы хранения, разные API).
   * Увеличивает операционную нагрузку и требует более универсальных инструментов (K8s, Terraform).

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