# AskfmForHumans

## О проекте

Проект **"ASKfm для людей"** призван сгладить некоторые "косяки" нашей [любимой соцсети](https://ask.fm/).
Я ([@jgrdlgrd](https://ask.fm/jgrdlgrd)) занимаюсь этим чисто в качестве личного хобби, а также рад буду сотрудничать с единомышленниками.
Присылай свои идеи/вопросы/жалобы мне в личку или оставляй в комментариях под этой страницей.

Новости проекта я публикую в профиле [@ask4humans](https://ask.fm/ask4humans), находящемся под управлением бота, который и является сутью проекта.
Бот умеет автоматически приветствовать новых пользователей, а также делать некоторую полезную работу. Например:
- спасать старые вопросы от автоматического удаления
- удалять вопросы, содержащие заданный текст
- удалять или помечать прочитанными все шаутатуты

Для подключения бота к своему аккаунту поставь себе в профиль хештег `#askfmforhumans` (обязательно!)
и напиши неанонимно [@jgrdlgrd](https://ask.fm/jgrdlgrd) для получения дальнейших инструкций.

> На данный момент (и, вероятно, навсегда) **бот находится в стадии тестирования и может работать нестабильно**.

## Настройка бота

Для настройки взаимодействия бота со своим профилем добавь в конец описания профиля (раздел "О себе") строку `=AskfmForHumans=`.
Под ней в отдельных строках размещаются пары `ключ=значение`.
*Ключ* — это название настройки, а за ним после знака равенства следует одно из допустимых значений.
Для настроек типа `да/нет` можно писать только ключ без знака равенства, это будет рассматриваться как `да`.

Все настройки перечислены в таблицах ниже (**жирным** выделены значения по умолчанию).

### Базовые функции

ключ | возможные значения | комментарий
--- | --- | ---
`читать_шаутауты` | **да**/нет | Сразу же помечать уведомления о шаутаутах как прочитанные.
`спасать_старые_вопросы` | да/**нет** | Аск автоматически удаляет из инбокса вопросы старше года. Если включить, бот будет предотвращать удаление вопроса, отвечая на него и сразу удаляя ответ. При этом вопрос переместится в вершину инбокса.
`удалять_вопросы_старше_N_дней` | положительное целое число | Функция, противоположная предыдущей — позволяет автоматически избавляться от старых вопросов, не дожидаясь, когда пройдёт год. Применять с острожностью :)
`стоп_машина` | да/**нет** |  Приостановить любые действия с профилем.

### Фильтры

ключ | возможные значения | комментарий
--- | --- | ---
`фильтр_шаутауты` | **да**/нет | Удалять все шаутауты из инбокса.
`фильтр_текст` | любой текст | Удалять вопросы, в которых встречается заданный текст (без учёта регистра).
`фильтр_регвыр` | [регулярное выражение](https://ru.wikipedia.org/wiki/Регулярные_выражения) | Продвинутая версия текстового фильтра. Выражения интерпретируются функцией [`re.search`](https://docs.python.org/3/library/re.html#re.search) стандартной библиотеки Python.

### Настройки фильтров

ключ | возможные значения | комментарий
--- | --- | ---
`фильтр_только_анон` | да/**нет** | Применять фильтры только к анонимным вопросам (так можно снизить количество спама, не подвергая риску неанонимные вопросы).
`фильтр_блок_авторов` | да/**нет** | При удалении вопроса также блокировать ("кидать в ЧС") его автора, чтобы не получать повторных вопросов от этого человека. Работает даже для анонимных вопросов.
`фильтр_режим` | непрерывно/**ежедневно**/по_запросу | Непрерывный вариант фильтрует вопросы в режиме реального времени, так что ты их даже не увидишь. Другие режимы позволяют успеть прочитать полученные вопросы и ответить на понравившиеся или пометить их как "нужные". *Режим "по запросу" и сохранение "нужных" вопросов пока не реализованы.*

### Пример настроек

```
=AskfmForHumans=
фильтр_текст=привет
фильтр_текст=пока
фильтр_регвыр=(?i)добр\w+ (утр|де?н|ноч|вече)\w+
фильтр_блок_авторов
фильтр_шаутауты=нет
```

Такая конфигурация будет раз в сутки удалять все вопросы со словами "привет" или "пока", а также (благодаря регулярному выражению)
различные приветствия в духе "доброе утро" или "доброй ночки".
Обрати внимание, что можно добавить несколько фильтров типа `текст` или `регвыр` в разных строках.
Удаление всех шаутаутов без разбора здесь отключено, но если шаутаут содержит что-то, запрещённое другими фильтрами, он *будет наказан должным образом*.
Для этого в нашем примере включено блокирование авторов вопросов.

Примеры настроек можно также подсмотреть в профилях [@ask4humans](https://ask.fm/ask4humans) или [@jgrdlgrd](https://ask.fm/jgrdlgrd).

## Вопросы и ответы

**В: Администрация Аска не против этого безобразия?**  
О: Подозреваю, что мою лавочку прикроют, если у неё будет достаточно много пользователей. Поэтому можно считать, что проект предназначен только для узкого круга лиц.

**В: Где туса для людей с АйТи головного мозга?**  
О: [https://github.com/AskfmForHumans](https://github.com/AskfmForHumans)