# Тренажёр Greenplum

Интерактивный тренажёр по теории Stage 3 учебного проекта Citibike Analytics: MPP-архитектура, распределение и перекос, типы хранения, EXPLAIN и Motion, партиционирование, EXCHANGE PARTITION, PXF и способы загрузки.

На каждом уровне: теория, интерактивные схемы и анимации, задачи на SQL с автопроверкой и чекпоинт с разбором каждого варианта ответа. Прогресс хранится в браузере (localStorage), сервер не нужен.

**Сайт:** `https://<твой-логин>.github.io/greenplum-trainer/` (появится после публикации, см. ниже)

## Структура

```
greenplum-trainer/
├── README.md            — этот файл
├── CHANGELOG.md         — история версий сайта
├── PLAN.md              — рабочий план и журнал задач
├── .gitignore
└── docs/                — исходники сайта, папка для GitHub Pages
    ├── index.html       — разметка: 10 уровней (старт + 9 тем)
    ├── .nojekyll        — отключает обработку Jekyll, файлы отдаются как есть
    └── assets/
        ├── style.css    — стили, темы и палитры
        ├── app.js       — логика: модели, анимации, задачи, чекпоинты
        └── favicon.svg
```

Зависимостей и сборки нет: это обычный статический сайт. Шрифты подключаются с Google Fonts.

## Как открыть локально

Открыть `docs/index.html` в браузере двойным щелчком. Или запустить локальный сервер:

```bash
cd docs
python -m http.server 8000
# затем открыть http://localhost:8000
```

## Как опубликовать на GitHub Pages

1. Создать на GitHub пустой репозиторий `greenplum-trainer` (публичный: на бесплатном тарифе Pages работает только для публичных).
2. Репозиторий уже инициализирован (ветка `main`, первый коммит сделан). Осталось привязать GitHub и отправить код:
   ```bash
   git remote add origin https://github.com/<твой-логин>/greenplum-trainer.git
   git push -u origin main
   ```
3. На GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, ветка `main`, папка `/docs`, **Save**.
4. Через 1–2 минуты сайт откроется по адресу `https://<твой-логин>.github.io/greenplum-trainer/`.

Обновление сайта — обычный `git commit` и `git push` изменённых файлов в `docs/`. Каждое изменение записывается в `CHANGELOG.md` с номером версии.

## Источники

Теория собрана по открытым материалам (в репозиторий они не копируются, только ссылки):

- [Greenplum: что за зверь и как его приручить](https://www.youtube.com/live/TupXHhdSrhg) — Д. Павлов, DataLearn
- [Детальное видео про Greenplum с практикой](https://youtu.be/m0EkeQjjxVM)
- [Партиционирование](https://docs.arenadata.io/ru/ADB/current/concept/data-model/tables/partitioning.html) — документация Arenadata DB
- [PXF и внешние таблицы](https://habr.com/ru/companies/otus/articles/682990/) — Habr / OTUS
- [Как мы тестировали 5 способов загрузки данных в Greenplum](https://squidex.jugru.team/api/assets/srm/5061589c-532b-4a85-a80c-d8f73c8cc0fa/konferenciya-smart-data-tanya-didova-greenplum.pdf) — Т. Дидова, SmartData
- [Распределение и партиционирование в Greenplum](https://gpskew.rzvde.pro/) — интерактивная демонстрация
- [Greenplum в Wikipedia](https://en.wikipedia.org/wiki/Greenplum) — история проекта
- Карточки Anki по Greenplum (21 карточка)
