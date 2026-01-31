## Статьи

Что такое LLM Observability и с чем его едят. Почему он важен в проекте.
https://www.confident-ai.com/blog/what-is-llm-observability-the-ultimate-llm-monitoring-guide

Что такое LLM Observability и какие метрики важно собирать в случае для LLM?
https://www.ibm.com/think/topics/llm-observability

Немного про OpenTelemetry и почему он важен
https://www.ibm.com/think/topics/opentelemetry

What is LLM Observability and LLM Monitoring?
https://langfuse.com/faq/all/llm-observability

## Что можно использовать для квалификационной работы

**LangFuse** - интересный вариант, есть тонна интеграций и опенсорсный проект. Скорее всего будет выбран для ВКР, чтобы контролировать LLM в условиях продакшена.
https://github.com/langfuse/langfuse

Плюсы:
- Много интеграций с другими LLM и имеется свой AI Gateway внутри
- Сразу всё в коробке: LLM Application Observability, Prompt Management, Evaluations, Datasets, LLM Playground, своя API.
- Можно подтянуть сразу в Docker и Kubernetes
- Современный и актуальный репозиторий
- Популярный и имеет сообщество для помощи
- Есть документация
- Сбор трейсов и метрик напрямую.
- Лицензия - MIT

Минусы:
- Слишком огромная система для маленькой работы
- Очень много разбираться новичку, который впервые работает с LLM.

**OpenLLMetry** - возможно пригодится, если захотим собирать метрики не через LangFuse
https://github.com/traceloop/openllmetry

Helicone - простой вариант, имеется возможность селфхоста, имеет свой gateway, сбор метрик, дебага и промпт-менеджмент. Менее популярный, но в целом всё ещё достойный вариант, меньше документации.
https://github.com/Helicone/helicone

Phoenix - тоже простой вариант с документацией, возможность селфхоста, traces, evaluation
https://phoenix.arize.com/
https://github.com/Arize-ai/phoenix/