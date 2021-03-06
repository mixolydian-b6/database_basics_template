# Bricks. Запити зацікавлених осіб

## Вступ
Цей документ описуює запити зацікавлених осіб, якими є люди, зацікавлені в отриманні інформації про перспективи вступу на факультети ВНЗ України.

### Мета 
Визначення вимог до функціональності, продуктивності і експлуатаційної придатності. Встановлення бізнес-правил і технологічних обмежень, згідно з якими розроблюватиметься проєкт.

### Контекст
Вимоги, визначені в цьому документі, є ґрунтом для розробки системи управління відкритими даними Bricks.

### Основні визначення та скорочення
Описані в документі, присвяченому [аналізу предметної області](state-of-the-art.md).

## Зміст

[Характеристика ділових процесів](#description)

[Короткий огляд продукту](#insight)

[Функціональність](#functionality)

[Практичність](#practicality)

[Надійність](#reliability)

[Продуктивність](#productivity)

[Експлуатаційна придатність](#supportability)

## <a name="description">Характеристика ділових процесів</a>

Зовнішніми факторами цієї сфери діяльності є користувачі, яким необхідно знайти дані для їх перегляду або завантаження. У системі вони зберігаються згідно з [форматом опису даних](Subject%20analysis.md#ddf). Об'єктом взаємодії користувачів із системою є набір даних. Сценарій його створення наведено нижче.

*Учасники*: менеджер, система  

*Передумови*: відсутні

*Результат*: менеджер створив набір даних

*Виключна ситуація*: ***EX.m.m.4***: колекції з уведеним ідентифікатором не існує

*Основний сценарій*:

![UC.m.m.4](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/mixolydian-b6/Bricks/master/src/uml/UC.m.m.4.puml)

## <a name="insight">Короткий огляд продукту</a>

**Bricks** – система керування відкритими даними, яка забезпечує усі етапи їх життєвого циклу. Можливо здійснювати пошук необхідних наборів даних і одразу визначати, який з них відповідає потребам користувача завдяки їх детальному опису. Будь-який набір даних можна безкоштовно завантажити. Для зручного сприймання, набір можна візуалізувати та обрати його відображувану частину.

Також, кожний користувач має можливість створити акаунт для створення власних наборів і їх редагування. Можливе додавання інших користувачів як співавторів, які теж матимуть права на редагування відповідних наборів.

## <a name="functionality">Функціональність</a>

Зацікавлених осіб можна поділити на категорії: користувач, менеджер наборів даних. Їх можливості забезпечують повний цикл життя даних.

* Можливості користувача:
  * пошук наборів даних (за допомогою пошуку або фільтрів)
  * завантаження наборів даних
  * створення акаунта менеджера
    
* Можливості менеджера:
  * можливості користувача, окрім створення акаунта
  * створення та видалення своїх наборів даних
  * змінення своїх наборів та тих, яких менеджера було зроблено співавтором
  * додання та видалення співавторів своїх наборів

## <a name="practicality">Практичність</a>

* Інтуїтивний інтерфейс. Посилання через текст кнопки та іконки складають чітке уявлення про сторінки, на які вони ведуть.
* Інтерактивінсть. Користувач користується системою через постійну взаємодію з нею.
* Система пошуку. Набори даних можуть бути знайдені за допомогою фільтрів або пошуку за ключовими словами.
* Відкритість даних. Користувач має безумовну можливість завантажити будь-який набір даних.
* Придатність для іноземців. Окрім української мови інтерфейсу, доступною є англійська.

## <a name="reliability">Надійність</a>

Системі має бути притаманне наступне:

* **Стійкість бази даних до дефектів і помилок** - властивість автоматичного підтримання заданого рівня якості даних у випадках проявів дефектів, помилок або порушення встановленого інтерфейсу із зовнішнім середовищем. Для цього, в базу повинна вводитися тимчасова й інформаційна надмірність, яка здійснює оперативне виявлення дефектів і помилок інформації, їх ідентифікацію та автоматичне відновлення нормального функціонування.

* **Резервне копіювання та відновлення даних** на незалежні сервери для можливого подальшого відновлення.

* **Доступність бази даних** - бути здатною повністю виконувати потрібну опцію в даний момент і за заданих умов її використання.
