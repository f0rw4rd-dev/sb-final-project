# Атрибуты качества

В качестве основных атрибутов качества для данного приложения можно выделить 3 ключевых параметра. При этом каждая подсистема может иметь дополнительные атрибуты (производительность, переносимость и др.), однако именно эти три имеют решающее значение для поддержания стабильной работы системы в целом:
1. Наблюдаемость (Observability).
   * Описание: система должна быть снабжена подробными логами, метриками и трассировками, что позволит оперативно обнаруживать и устранять проблемы.
   * Причина: в условиях глобальных запусков и при высоких нагрузках своевременная диагностика критична для поддержания качества сервиса.
2. Масштабируемость (Scalability).
   * Описание: архитектура должна обеспечивать горизонтальное масштабирование основных компонентов, чтобы справляться с пиковыми нагрузками (например, во время больших соревнований).
   * Причина: приложение ориентировано на глобальную аудиторию, а значит, должно легко адаптироваться к резкому росту количества пользователей и объемов обрабатываемых данных.
3. Безопасность (Security).
   * Описание: защита персональных данных пользователей, в том числе информации о здоровье, а также обеспечение безопасного обмена данными через API и между микросервисами.
   * Причина: обработка чувствительных данных требует соблюдения нормативных требований и минимизации рисков утечек, что является критически важным для доверия пользователей и репутации бренда.

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
12. [Описание сценариев использования приложения](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/use_cases.md)
13. [Базовая архитектура](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/basic_architecture.md)
14. [Основные представления](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/views.md)
15. [Анализ рисков созданной архитектуры, компромиссов](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/architecture_risks.md)
16. [Стоимость владения системой](https://github.com/f0rw4rd-dev/sb-final-project/blob/main/costs.md)