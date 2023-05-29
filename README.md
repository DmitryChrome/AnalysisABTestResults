# <center> **Анализ результатов A/B-тестирования** </center>
## Оглавление
1. [Описание проекта](#Описание-проекта)
2. [Описание данных](#Описание-данных)
3. [Зависимости](#Используемые-зависимости)
4. [Установка проекта](#Установка-проекта)
5. [Авторы](#Авторы)
6. [Выводы](#Выводы)

## Описание проекта
Компания планирует запустить новую акцию, чтобы продать как можно больше туров. Команда разработала два варианта посадочной страницы официального сайта компании и провела A/B-тестирование. Собранные в результате проведения эксперимента данные можно скачать [здесь](https://lms-cdn.skillfactory.ru/assets/courseware/v1/3274d20d12cca49b6ce3d18d75ba8826/asset-v1:SkillFactory+DSPR-2.0+14JULY2021+type@asset+block/ab_data_tourist.zip).

Нам предстоит решить настоящую бизнес-задачу: проанализировать эффективность обоих вариантов посадочной страницы сразу по двум критериям: **конверсии покупки** и **среднему чеку**. На основе проведенного анализа вам будет необходимо сделать выводы и принять решение: какой из вариантов дизайна более предпочтительный.

Наша фирма предлагает следующие варианты туров и их соответствующие стоимости:
* Таиланд — 100000 рублей;
* Турция — 60000 рублей;
* Мальдивы — 200000 рублей;
* Санкт-Петербург — 10000 рублей;
* Камчатка — 150000 рублей.

**Цели проекта:**
* Применение тестов на нормальность;
* Применение стабилизации метрик и их анализ;
* Отработать навык применения статистических тестов;
* Использование доверительных интервалов;
* Заключить итоговое решение по задаче.

**Основные этапы работы с данными:**
1. Анализ структуры данных и их предобработка;
2. Первичный анализ результатов A/B-тестирования;
3. Анализ данных на предмет стабилизации метрик;
4. Статистический анализ результатов A/B-тестирования;
5. Общий вывод по результатам A/B-теста.

**Данный проект** посвящен аналитической работе над результатами A/B-тестирования в виде экспериментальных данных туристического агенства. Проект показывает применение некоторых статистических тестов на одном определённом примере и не несёт в себе цели демонстрации всех возможных статистических тестов и критерий.

**О структуре проекта:**
* [AnalysisABTestResults.ipynb](./AnalysisABTestResults.ipynb) - jupyter-ноутбук, содержащий основной код проекта, в котором происходит анализ результатов A/B-тестирования.
* [data](./data/) - папка содержащая файлы с данными о результатах A/B-тестирования.

## Описание данных

Наша таблица представлена следующими полями:
* user_id — идентификатор пользователя, зашедшего на сайт;
* data — дата посещения сайта;
* group — группа теста (контрольная — А или тестовая — B);
* purchase — признак покупки: совершил ли пользователь покупку тура (1 — да, 0 — нет);
* price — цена купленного тура (если покупка не состоялась, цена равна 0).

## Используемые зависимости
* Python (3.9):
    * [Pandas (1.3.4)](https://pandas.pydata.org)
    * [Matplotlib (3.6.0)](https://matplotlib.org/)
    * [Seaborn (0.11.2)](http://seaborn.pydata.org/index.html)
    * [scipy (1.9.3)](https://scipy.org/)
    * [statsmodels (0.13.5)](https://www.statsmodels.org/stable/index.html)

## Установка проекта

```
git clone https://github.com/DmitryChrome/AnalysisABTestResults.git
```

## Авторы

* [Dmitry Chuprinko](https://t.me/Dmitry_Chuprinko)

## Выводы

В данной работе мы испльзовали статистические **t-тест** и **z-тест** на пропорции, **тест на нормальность** *Шапиро-Уилка*, также построили *доверительные интервалы* **конверсий**, *разность доверительных интервалов* **конверсий** и *доверительные интервалы* **математического ожидания** (средних чеков тестируемых групп).  
По результатам всего **А/В тестирования** и его анализа можно заключить, что вариант дизайна посадочной страницы, используемый в *группе В*, будет более <u>эффективным</u>. Сравнительные тесты показали, что **конверсия** <u>не имеет разницы</u> между тестируемыми группами, а вот **средний чек** в *группе В* <u>выше</u>, чем в *группе А*.  
В итоге вариант дизайна тестируемой *группы B* будет **рекомендован** к реализации для всех пользователей сайта.