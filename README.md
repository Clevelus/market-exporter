# Market Exporter
Плагин для экспорта товарных предложений из WooCommerce в WordPress.

## Содержание

- [Market Exporter](#)
- [Описание](#Описание)
- [Установка](#Установка)
- [FAQ](#faq)
- [История версий](#История-версий)
- [Поддержка](#Поддержка)

## Описание

Если Вы используете WooCommerce и хотите экспортировать все Ваши товары в Яндекс Маркет, то этот плагин однозначно для Вас! Market Exporter предоставляет возможность создавать файлы YML для экспорта товаров в Яндекс Маркет.

Плагин находится в активной разработке. На данный момент поддерживается только упрощенный тип описания для экспортированного списка товарных предложений (т.е. выгружаются следующие поля: название, описание, цена, категория и изображение). Большой упор сделан на соответствие требованиям Яндекс Маркет. Поддерживаются пять валют: рубль, белорусский рубль, гривна, доллар и евро.

Я собираю отзывы и предложения о том какой функционал Вы хотите видеть в плагине.

![Фото главной страницы плагина](https://ps.w.org/market-exporter/assets/screenshot-1.png)

![Фото страницы настроек плагина](https://ps.w.org/market-exporter/assets/screenshot-2.png)

## Установка

1. Загрузите 'Market Exporter' в папку с плагинами на Вашем сайте WordPress (`/wp-content/plugins/`).
2. Активируйте 'Market Exporter' через раздел 'Плагины' в WordPress.
3. Выберите 'Market Exporter' в разделе 'WooCommerce' в WordPress.
4. Нажмите кнопку 'Генерировать YML файл'.

## FAQ

**Какие типы валют поддерживаются плагином?**

Данные о ценах принимаются в рублях (RUR, RUB), белорусских рублей (BYN), гривнах (UAH), долларах (USD) и евро (EUR). На данный момент в WooCommerce не реализована поддержка тенге (KZT), так что плагин их тоже не поддерживает. На Яндекс Маркете цены могут отображаться в рублях, гривнах, белорусских рублях и тенге в зависимости от региона пользователя.

В качестве основной валюты (для которой установлено rate="1") могут быть использованы только рубль (RUR, RUB) и гривна (UAH). Если в WooCommerce установлены доллары (USD) или евро (EUR), то используется курс Центрального Банка той страны, которая указана в настройках магазина на Яндекс Маркет. Применяется курс, установленный на текущий день. Курс обновляется ежедневно в 00.00.

**Как поменять настойки плагина?**

Настройки плагина можно осуществить на вкладке 'Настройки' в менюю 'WooCommerce' - 'Market Exporter'.

В настоящий момент поддерживаются следующие настройки:
* Изменение названия магазина;
* Измнение названия компании;
* Изменение количества изображений при экспорте товарных предложений;
* Использование произвольного поля для элемента vendor и model;
* Использование произвольного поля для элемента market_category;
* Поддержка элемента sales_notes;
* Поддержка элементов param (вкгючая габариты и вес);
* Поддержка товаров со статусом предзаказ;
* Поддержка cron.

**Какие требования к WordPress, WooCommerce и оборудованию?**

Плагин был протестирован на последних версиях WordPress, но, скорее всего, он будет работать и на более старых версиях.

WooCommerce также тестировался на последних версиях.

Версия PHP должна быть не ниже 5.4. Полная поддержка версии 7.0.

**Я хочу помочь! Что я могу сделать?**

Если у Вас есть желание помочь в развитие плагина, то Вы можете помочь в тестировании новых версий. Для этого необходимо скачать из ветки development исходный код плагина и установить его к себе на сайт.

В ветке development хранится самая последняя версия плагина, над которой идет разработка. Обращаю Ваше внимание, что данная версия может содержать в себе баги и ошибки. Но я, все же, стараюсь тестировать все релизы перед загрузкой.

Также, Вы можете помочь с переводом плагина. Для этого необходимо перейти в раздел '[Translating WordPress](https://translate.wordpress.org/projects/wp-plugins/market-exporter)' на сайте WordPress.org и предложить вариант перевода строк на желаемом языке.

## История версий
**0.1.0**
* Возможность устанавливать typePrefix для товаров
* Возможность устанавливать manufacturer_warranty для товаров
* Возможность устанавливать country_of_origin для товаров
* Поддержка параметров: shop, pickup и delivery
* Возможность изменять какое описание товара будет выгружаться в файл
* Поддержка Тенге (KZT)
* Поддержка выгрузки до 10 изображений на товарное предложение
* Возможность автоматического обновления файла при изменении или создании товарных предложений
* Обнволение интерфейса
* Исправлены переводы
* Экспорт веса и габаритов в элементы weight и dimensions
* Библиотека select2 обновлена до последней версии
* Улучшена поддержка PHP 5.2
* Фильтр категорий не отображал категории глубже 2 уровня

**0.4.4**
* Добавлена озможность устанавливать время крон.
* При отсутствии изображения у варации, плагин попытается взять изображение основного товара.
* Исправлены проблемы с крон, удалены лишние расписания.
* Разные мелки исправления и улучшения.
* Добавлены недростающие скрипты и стили select2.
* Теперь скрпиты и стили загружаются только на страницах плагина, а не везде.
* В файл будут выгружаться только актуальные категории в раздел categories.

**0.4.3**
* Добавлена поддержка для WordPress версии 4.7.3.
* Чекбоксы в настройках отображают выбранные настройки.
* Исправлена ошибка, когда Vendor и Model не выгружались у вариативных товаров.
* Исправлена ошибка, из-за которой не выгружались габариты и вес у вариативного товара.
* Исправлена ошибка с невозможностью выгрузить market_cateogry у вариативного товара.
* Улучшения в стилях CSS.

**0.4.2**
* Исправлена оишбка при активации на PHP 5.5 и младше.

**0.4.1**
* Исправлена ошибка, из-за которой не выгружались файлы из Woocommerce версии младше 3.0.0.
* По умолчанию поле sales_notes будет пустым и не будет содержать 'no' в качестве текста.
* Если задано описание вариации, то будет использовано оно вместо общего описания товара.
* У вариативных товаров выгружаются изображения вариаций, а не изображение главного товара.

**0.4.0**
* Добавлена поддержка тега model.
* Добавлена поддержка параметров (тег param).
* Добавлена поддержка белорусских рублей (BYN).
* Добавлена возможность выгружать вес и габариты (длина, ширина и высота) в качестве соответствующих параметров.
* Исправлены ошибки с полями input.
* Исправлена ошибка с невыгрузкой параметра vendor.
* Исправлена ошибка, когда прайс-лист не создавался, если одна из вариаций товара была недоступна (например, ее нет в наличии).
* Ссылки теперь генерируются согласно RFC.
* Исправлена ошибка с неработающим крон.
* Вместо короткого описания, теперь в настройках плагина доступно отдельное поле для элемента sales_notes.
* По многочисленным просьбам, добавлена поддержка PHP 5.3.
* Переработан код для поддержки последних версий WooCommerce.

**0.3.1**
* Релиз для официального репозитория WordPress. Обновляться с 0.3.0 не обязательно.

**0.3.0**
* Добавлена фильтрация выгрузки по категориям.
* Исправлены ошибки с невозможностью экспорта импортированных товаров.
* В названии товаров заменяются запрещенные символы на соответствующие коды.
* Настройки и генерация файла объеденены под одним пунктом меню. Теперь вся информация о плагине доступна в разделе WooCommerce - Market Exporter.
* Стили интерфейса придевены в соответствие общему стилю WordPress.


**0.2.6**
* Исправлены некоторые ошибки при работы с вариативными товарами. Остается ошибка с товарами, где вариации строятся по нескольким атрибутам.
* Исправлены неточности в переводе.
* Исправлена ссылка при генерации файла.
* Добавлен раздел последних новостей.
* Оптимизация кода.

**0.2.4**
* Плагин корректно работает на PHP 5.3.
* Исправлены ошибки и недочеты.

**0.2.3**
* Оптимизация кода.

**0.2.1**
В предыдущей версии был допущен ряд ошибок. Здесь я их исправил.
* Добавлена поддержка Cron. Теперь файл будет генерироваться раз в сутки.
* Добавлен CDATA в поле description.
* Решена проблема с ошибкой при экспорте, если в базе данных использовался префикс, отличный от заданного по умолчанию (не wp_)
* Исправлен экспорт изображений. Теперь должны экспортироваться нужные.

**0.2.0**
* Добавлена поддержка вариативного товара.

**0.1.0**
Предновогодний релиз. После данного релиза все исправления будут выходить под номерами 0.1.х, а релизы будут иметь вид 0.x.0.
* Добавлена возможность просмотреть/удалить историю создания файлов YML.
* Добавлена возможность добавления или удаления даты из имени файла YML.
* Добавлена возможность выгрузки товаров со статусом предзаказ.
* Исправлены ошибки с некорректными элементами в поле 'description'.

**0.0.7**
* Добавлена новая опция, которая позволяет установить произвольный атрибут для использования в качестве свойства 'vendor' в выгрузке.
* Возможность указать произвольные атрибуты для элементов 'market_category' и 'sales_notes'.
* Возможность использовать элемент 'sales_notes'.
* Важно! Данные элемента 'description' берутся из поля 'описание' товара (раньше брались из поля 'краткое описание').
* Если установлена скидка на товар, то верно заполняется элемент 'oldprice' в файле YML.
* Актуализирован русский перевод.
* Элемент 'description' не будет создаваться, если нет описания товара.

**0.0.6**
* Добавлена новая опция для указания количества изображений для экспорта.
* Оптимизация и чистка кода.
* Исправлена ошибка с экспортом изображений.

**0.0.5**
* Добавлена поддержка следующих валют: рубль, гривна, доллар, евро. Все должно работать как прописано в документации Яндекс Маркета. Т.е. можно цены задавать в любой из этих валют. Конвертация (при евро и долларе) будет по курсу ЦБ той страны, где зарегистрирован магазин, основной валютой при этом будет рубль.
* Выгружаются до 10 изображений товаров. По требованиям Яндекса длина URL изображения не должна превышать 512 символов. Изображение с длинной больше 512 символов выгружаться не будут. Сейчас реализована поддержка PNG и JPEG изображениям. GIF не реализовывал, т.к. вряд ли кто-то грузит такие изображения.
* Товары, которых нет в наличии, экспортироваться не будут.
* Вкладка с настройками плагина доступна тут: WooCommerce - Настройки - Товар.

**0.0.4**
* Корректно определяются виды доставки. Плагин проверяет доступность местной доставки, если она отключена, то берет данные из доставки по единой ставке.
* Появилось меню настроек (Настройки - Market Exporter). Сейчас там нужно указывать произвольные поля 'Короткое название магазина' и 'Полное наименование компании'. Данные поля необходимо заполнить. При первой активации плагин должен туда подставить данные из Настройки - Общие - Название сайта.
* Все текстовые поля проходят обязательную фильтрацию, при которой удаляются все HTML теги.
* Переработал код, чтобы он соответствовал рекомендациям от WordPress.
* Плагин теперь может удалять за собой "следы" из базы данных. На данный момент остается лишь папка wp-content/uploads/market-exporter/.

**0.0.3**
* Исправление багов.

**0.0.2**
* Если товара в WooCommerce спрятан, то он не будет экспортироваться в YML.
* Артикул товара выгружается в поле vendorCode в файле YML.
* Файл теперь сохраняется в папке wp-content/uploads/market-exporter/, а не в папках по умолчанию.
и небольшие оптимизации в коде.

**0.0.1**
* Первый выпуск.

## Поддержка
Поддержать плагин и разработчика можно через [Яндекс.Деньги](https://money.yandex.ru/embed/donate.xml?account=41001982223656&quickpay=donate&payment-type-choice=on&default-sum=300&targets=%D0%9F%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B0+%D0%BF%D0%BB%D0%B0%D0%B3%D0%B8%D0%BD%D0%B0+Market+Exporter+%D0%B4%D0%BB%D1%8F+WordPress&target-visibility=on&project-name=Market+Exporter&project-site=https%3A%2F%2Fgithub.com%2Fav3nger%2Fmarket-exporter&button-text=05&mail=on&successURL=)
