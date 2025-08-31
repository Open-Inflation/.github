# An open source project to collect consumer inflation data worldwide

| Project        | Store type          | Tests last run | Tests | Downloads |
|----------------|---------------------|----------------|-------|-----------|
| [perekrestok_api](https://github.com/Open-Inflation/perekrestok_api) | food (mid/expensive) | ![Tests last run (ISO)](https://img.shields.io/badge/dynamic/json?label=Tests%20last%20run&query=%24.workflow_runs%5B0%5D.updated_at&url=https%3A%2F%2Fapi.github.com%2Frepos%2FOpen-Inflation%2Fperekrestok_api%2Factions%2Fworkflows%2Ftests.yml%2Fruns%3Fper_page%3D1%26status%3Dcompleted&logo=githubactions&cacheSeconds=300) | [![Tests](https://github.com/Open-Inflation/perekrestok_api/actions/workflows/tests.yml/badge.svg)](https://github.com/Open-Inflation/perekrestok_api/actions/workflows/tests.yml) | [![PyPI - Downloads](https://img.shields.io/pypi/dm/perekrestok_api?label=PyPi%20downloads)](https://pypi.org/project/perekrestok-api/) |
| [chizhik_api](https://github.com/Open-Inflation/chizhik_api) | food (cheap) | ![Tests last run (ISO)](https://img.shields.io/badge/dynamic/json?label=Tests%20last%20run&query=%24.workflow_runs%5B0%5D.updated_at&url=https%3A%2F%2Fapi.github.com%2Frepos%2FOpen-Inflation%2Fchizhik_api%2Factions%2Fworkflows%2Ftests.yml%2Fruns%3Fper_page%3D1%26status%3Dcompleted&logo=githubactions&cacheSeconds=300) | [![Tests](https://github.com/Open-Inflation/chizhik_api/actions/workflows/tests.yml/badge.svg)](https://github.com/Open-Inflation/chizhik_api/actions/workflows/tests.yml) | [![PyPI - Downloads](https://img.shields.io/pypi/dm/chizhik_api?label=PyPi%20downloads)](https://pypi.org/project/chizhik-api/) |
| [fixprice_api](https://github.com/Open-Inflation/fixprice_api) | food+household (cheap) | ![Tests last run (ISO)](https://img.shields.io/badge/dynamic/json?label=Tests%20last%20run&query=%24.workflow_runs%5B0%5D.updated_at&url=https%3A%2F%2Fapi.github.com%2Frepos%2FOpen-Inflation%2Ffixprice_api%2Factions%2Fworkflows%2Ftests.yml%2Fruns%3Fper_page%3D1%26status%3Dcompleted&logo=githubactions&cacheSeconds=300) | [![Tests](https://github.com/Open-Inflation/fixprice_api/actions/workflows/tests.yml/badge.svg)](https://github.com/Open-Inflation/fixprice_api/actions/workflows/tests.yml) | [![PyPI - Downloads](https://img.shields.io/pypi/dm/fixprice_api?label=PyPi%20downloads)](https://pypi.org/project/fixprice-api/) |
| [pyaterochka_api](https://github.com/Open-Inflation/pyaterochka_api) | food (mid) | not implemented | not implemented | [![PyPI - Downloads](https://img.shields.io/pypi/dm/pyaterochka_api?label=PyPi%20downloads)](https://pypi.org/project/pyaterochka-api/) |
| dns_api | electronics (mid) | not implemented | not implemented | not implemented |
| eldorado_api | electronics (mid) | not implemented | not implemented | not implemented |
| citilink_api | electronics (mid/cheap) | not implemented | not implemented | not implemented |
| mvideo_api | electronics (mid/expensive) | not implemented | not implemented | not implemented |


### 2. Создание "сборочных конвееров"

> Скрипты отдельные для каждой страны *(по причине оптимизации разработки, и банов селлерами опредленных IP-диапазонов)*. Они будут формировать списки каталогов собирая их в единый формат *(структуру)*, а так же иконки товаров.
> Собранные таким образом изображения и информация каталога будет запакована в архив и в таком виде отправлена на сервер хранения.

***Этап не проработан.***

### 3. Создание центра хранения

Это единый сервер куда будут присылаться данные на регистрацию. Регистрация будет проходить из:
1. Дополнения базы данных новыми записями *(создание новой карточки товара, если позиция новая)*/*(обновление текущей карточки товара новой информацией (обновленной цене, рейтингу и т.п.))*
2. Обновление изображений: сохранение новых изображений для новых товаров, замена изображений для текущих товаров.

#### Сервер отвечает 2-мя способами:
1. Пользователь может запросить актуальный дамп (датасет)
2. Пользователь может общаться с сервером как с обычным каталогом

### 4. Создание сайта-интерфейса

> Информация будет запрашиваться из центра хранений для визуализации инфляции, информации об изменении карточек товаров и т.п.
