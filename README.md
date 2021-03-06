# Помощник для путешествий

## Описание

### Приложение

Согласно user story (см. файл `user_story/user_story.pdf`) обладает следующим функционалом:
* Предоставить актуальные новости России или Германии.
* Предоставить сводку о погоде в Москве или Берлине на завтра.
* Предоставить актуальный курс рубля к евро.
* Предоставить **предположительную** статистику по COVID-19, **согласно интернет-ресурсу "covid19api.com"**, для России или Германии. **Предоставляемая статистика не является достоверной**, а лишь допускается, что воображаемого целевого пользователя приложения данный источник информации - устраивает.

Представляет из себя графический интерфейс, макет которого приведён в файле `layout/layout.png`.

Функционирование может подвисать из-за запросов к API. Также есть вероятность, что запрос вернёт пустой ответ из-за лимита использования API (обеспечить безлимитное использование нам не позволяет бюджет...).

Собирается и запускается в Docker. Также возможна генерация документации для кода.

### Разработка

Все задачи проекта представляют из себя закрытые issue. В процессе разработки они пополнялись. Также был создан project, в который добавлялись все issue. Всё это отражено в истории issue и на вкладке "Projects" соответственно.

Файлы проекта были разделены на части и распределены по веткам, в каждой из которых отдельный участник проекта выполнял отведённую ему часть.

Описание приведено по шаблону ниже.

_Участник_ - Фамилия Имя:
* `Ветка` - часть.

\
_x73495_ - Давыдов Артём:
* `bin` - скрипт запуска.
* `build` - система сборки.
* `gui` - GUI.
* `layout` - макет.
* `user-story` - user story (прежде обсуждалась между всеми участниками).

_Moreez317_ - Борисов Александр:
* `button-news` - кнопка "Новости".
* `button-weather` - кнопка "Погода".

_senzaw_ - Никулин Ярослав:
* `button-covid` - кнопка "COVID-19".
* `button-rate` - кнопка "Курс".

Каждый раз после изменения ветки происходило слияние ветки `main` с таковой.

Участники _Moreez317_ и _senzaw_ создавали pull requests для слияний их веток. В процессе разработки было принято решение принимать pull requests лишь после review от участника _x73495_. Каждый pull request привязывался к соответствующему issue. Всё это отражено в истории pull requests.

Из-за недочётов в процессе использования git в конце разработки был произведён rebase ветки `main` для поддержания чистоты истории ветки. Из-за тех же недочётов также были произведены reset + force push и rebase на иных ветках.

## Требования

### Основное
* `docker >=18.09.1`

### Для запуска приложения
* `x11-xserver-utils`

### Для открытия документации
* `xdg-utils` или `libgnome2-bin`
* веб-браузер

### Примечания
* Названия пакетов такие, как указаны в официальном репозитории Debian.
* Для загрузки необходимых пакетов внутри Docker необходимо подключение к интернету.
* Тестировалось на Debian 10 обычным пользователем, добавленным в группу `docker`.
* Открытие документации тестировалось на Firefox.

## Запуск

Выполнить `bin/ta run` для запуска приложения.

Выполнить `bin/ta doc` для генерации и открытия документации.

