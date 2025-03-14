# Нефункциональные требования

1. Производительность (Performance).
   * Система должна обеспечивать быстрый отклик (низкая задержка API) даже при высокой нагрузке.
   * Время ответа на критические запросы не должно превышать установленных порогов (например, < 200 мс для основных операций).
2. Масштабируемость (Scalability).
   * Возможность горизонтального масштабирования всех сервисов.
   * Использование облачных сервисов с поддержкой авто-скейлинга.
3. Доступность (Availability) и Надёжность (Reliability).
   * Высокий процент времени безотказной работы (SLA не менее 99.9%).
   * Механизмы репликации, резервного копирования и восстановления данных.
4. Безопасность (Security).
   * Шифрование чувствительных данных при транзите (HTTPS/TLS) и хранении.
   * Аутентификация и авторизация (OAuth2, OpenID Connect, двухфакторная аутентификация).
   * Соответствие требованиям законодательства.
   * Регулярные аудиты безопасности и тестирование на проникновение.
5. Наблюдаемость (Observability).
   * Централизованное логирование, сбор метрик и трассировка запросов.
   * Использование систем мониторинга и алертинга (например, Prometheus, Grafana).
6. Расширяемость.
   * API-first подход для интеграции с внешними сервисами, сторонними устройствами (Apple HealthKit, Google Fit и пр.).
   * Возможность лёгкого подключения новых модулей и сервисов без нарушения работы существующих компонентов.
7. Удобство использования (Usability).
   * Современный и удобный UI/UX для мобильного приложения и веб-сайта, минимальное количество действий для выполнения ключевых задач.
   * Легкость в навигации, простота регистрации и использования функционала приложения.
8. Портируемость.
   * Возможность развертывания в различных облачных окружениях.
   * Использование контейнеризации (Docker, Kubernetes) для обеспечения переносимости между средами.

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