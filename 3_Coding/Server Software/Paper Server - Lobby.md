**Paper-Lobby** - сервер для того, чтобы объединять игроков перед началом мини-игры в команды или игроки могли спокойно убедиться в готовности перед игровым процессом.

Сам по себе лобби-сервер является местом для игроков, которые не находятся в состоянии игры, но находятся “онлайн” на сервере. Функцию лобби выполняет коммуникационную цель для игроков и серверов-арен.

Как только игрок готов к игровому процессу, игрок может начать игру, нажав на соответствующую кнопку в лобби и отправить запрос на создание арены. 

После окончания сессии игрок возвращается в лобби, где выводятся её результаты и причина окончания.

## Используемый стек технологий и плагинов

## Ядро (Java)

| Используемое ПО | Версия     | Документация                                      | Исходники                                  | Лицензия |
| --------------- | ---------- | ------------------------------------------------- | ------------------------------------------ | -------- |
| Paper           | 1.21.11-96 | [docs.papermc.io](https://docs.papermc.io/paper/) | [GitHub](https://github.com/PaperMC/Paper) | GPLv3    |

## Используемые плагины (Java)

| Плагин         | Версия         | Документация                                                            | Исходники                                           | Лицензия |
| -------------- | -------------- | ----------------------------------------------------------------------- | --------------------------------------------------- | -------- |
| UnifiedMetrics | 0.3.8          | [docs.cubxity.dev](https://docs.cubxity.dev/docs/unifiedmetrics/intro)  | [GitHub](https://github.com/Cubxity/UnifiedMetrics) | LGPLv3   |
| LuckPerms      | 5.5.24         | [luckperms.net](https://luckperms.net/wiki/Usage)                       | [GitHub](https://github.com/LuckPerms/LuckPerms)    | MIT      |
| Spark          | 1.10.165       | [spark.lucko.me](https://spark.lucko.me/docs)                           | [GitHub](https://github.com/lucko/spark)            | GPLv3    |
| WorldGuard     | 7.0.16-beta-01 | [worldguard.enginehub.org](https://worldguard.enginehub.org/en/latest/) | [GitHub](https://github.com/EngineHub/WorldGuard)   | GPLv3    |
| WorldEdit      | 7.4.0-rc-01    | [worldedit.enginehub.org](https://worldedit.enginehub.org/en/latest/)   | [GitHub](https://github.com/EngineHub/WorldEdit)    | GPLv3    |

## Самописные плагины

#### `arena-lobby-gateway`  (Paper)

**Задача:** тонкий “входной шлюз” для игроков.

- Команды/GUI: выбор режима/карты/сложности, “войти в очередь”.
- Валидации доступа: права LuckPerms (группы, лимиты, приоритеты).
- Перенаправление на Paper-арену по решению matchmaker’а.
- Минимальный state: только “куда игрок хочет” и “куда его направить”.

Реальные показатели живут на Paper. На Velocity мы их лишь агрегируем.

## Стороннее (постройки/нерелевантное к ВКР)

Постройка - https://www.planetminecraft.com/project/waiting-lobby-download-3942353/