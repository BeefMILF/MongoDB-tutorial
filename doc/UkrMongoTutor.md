# MongoDB 

MongoDB — документо-орієнтована система керування базами даних (СКБД) з відкритим вихідним кодом, яка не потребує опису схеми таблиць. MongoDB займає нішу між швидкими і масштабованими системами, що оперують даними у форматі ключ/значення, і реляційними СКБД, функціональними і зручними у формуванні запитів.

# Основні можливості MongoDB:

* Документо-орієнтоване сховище (проста та потужна JSON-подібна схема даних)
* Досить гнучка мова для формування запитів
* Динамічні запити
* Повна підтримка індексів
* Профілювання запитів
* Швидкі оновлення «на місці»
* Ефективне зберігання бінарних даних великих обсягів, наприклад, фото та відео
* Журналювання операцій, що модифікують дані в БД
* Підтримка відмовостійкості і масштабованості: асинхронна реплікація, набір реплік і шардінг
* Може працювати відповідно до парадигми MapReduce

# Перш ніж працювати з db & schemas, давайте розглянемо відмінності від інших
типів db

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/difference.png)

На відміну від баз даних SQL, Mongodb не використовує пристрій таблиці з чітко
визначеною кількістю стовпців і типів даних.

БД складається з колекцій. Кожна колекція має унікальну назву - * ідентифікатор
*, що називається `_id '. Документ являє собою набір * пар-ключ-значення * пар.
# Data types
*   **String** - utf-8
*   **Array**
*   **Binary data**
*   **Boolean**
*   **Date**
*   **Double**
*   **Integer**
*   **JavaScript**
*   **Min key/Max key**
*   **Object** - string type
*   **ObjectID** - id document
*   **Regular expression** -
*   **Symbol** - identical to string, used for spec symbols
*   **Timestamp**



# Sample Document
```
{
   _id: ObjectId(7df78ad8902c)
   title: 'MongoDB Overview',
   description: 'MongoDB is no sql database',
   by: 'tutorials point',
   url: 'http://www.tutorialspoint.com',
   tags: ['mongodb', 'database', 'NoSQL'],
   likes: 100,
   comments: [
      {
         user:'user1',
         message: 'My first comment',
         dateCreated: new Date(2011,1,20,2,15),
         like: 0
      },
      {
         user:'user2',
         message: 'My second comments',
         dateCreated: new Date(2011,1,25,7,45),
         like: 5
      }
   ]
}
```

# Встановлення Mongodb на Windows

Перейдіть у [Центр завантажень MongoDB](https://www.mongodb.com/download-center/enterprise) -> виберіть у спадному меню **Windows x64** як свою операційну систему, а потім завантажте **файл .msi**.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/donwload_center.png)

Після завантаження файлу **msi** на комп'ютер натисніть на завантажений файл.
Тепер ви можете побачити майстра встановлення Windows для встановлення MongoDB-сервера на комп'ютер.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/Installation_wizard1.png)

Клацніть **Next**. У наступному вікні прийміть ліцензійну угоду клієнта та натисніть кнопку **Next**.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/Installation_wizard2.png)

Виберіть тип налаштування як **Complete**.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/Installation_wizard3.png)

У цьому вікні збережіть усі налаштування за замовчуванням та натисніть **Next**.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/Installation_wizard4.png)

У цьому вікні зніміть прапорець у полі **Install MongoDB Compass**. Інсталятор встановить **Community version** Compass, у якій бракує певної функціональності, яку ми будемо використовувати в цьому курсі.

Натисність **Install**.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/Installation_wizard6.png)

Натисніть кнопку **Finish** після того, як інсталятор успішно встановив **MongoDB Server** у вашій системі.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/Installation_wizard7.png)

Тепер перейдіть до цього каталогу, щоб побачити виконувані файли, завантажені на ваш комп’ютер із сервером MongoDB Enterprise.

```
C:\Program Files\MongoDB\Server\4.2\bin
```
![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/bin_directory.png)

Далі ми встановимо шлях для оболонки mongo у змінних оточення, щоб ви могли запускати ці виконувані файли у своєму командному рядку, не маючи необхідності вказувати повний шлях. Не закривайте це вікно ще, оскільки ми повернемось до нього для копіювання шляху до каталогу бін.

Введіть **Змінити змінні системного середовища** або **Edit the system environment variables** або **Изменение системных переменных среды**  на панелі пошуку Windows у нижньому лівому куті екрана.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/system_environment_variables.png)

Натисніть на **Змінні середовища** або **Переменные среды** або **Environment variables**

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/system_properties.png)

З'явиться нове вікно, де можна побачити **Користувацькі змінні** та **Системні змінні**.

Двічі натисніть на **Path** під **Системними змінними**.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/environment_variables.png)

У новому вікні ви можете побачити список шляхів, доданих до змінних оточення.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/list.png)

Поверніться до каталогу bin та скопіюйте адресу.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/copy_path.png)

У вікні **Редагування змінних середовищ** натисніть кнопку **Створити** та **вставте** повний шлях до каталогу бін, який ви щойно скопіювали у буфер обміну. Далі натисніть кнопку **ОК**, щоб зберегти зміни та закрити вікно.

![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/add_path.png)

Тепер ми перевіримо, чи вдало встановлено шлях для оболонки mongo.

Відкрийте командний рядок, ввівши cmd у панель пошуку Windows.

```
mongo --nodb
```
Якщо все пройшло добре, ви могли б бачити щось подібне на екрані.
```
MongoDB shell version v4.2.3
>
```
![](https://university-courses.s3.amazonaws.com/M001/Mongo+shell+installation+guide+windows/mongo_nodb.png)

# Встановлення Mongodb на Mac

MongoDB - це база даних документів, яка належить до сімейства баз даних під
назвою NoSQL - не тільки SQL. У MongoDB записи - це документи, які дуже схожі на
об'єкти JSON в JavaScript. Значення в документах можна шукати за допомогою ключа
їх поля. Документи можуть мати деякі поля / ключі, а не інші, що робить Mongo
надзвичайно гнучким.

**Tap the MongoDB Homebrew Tap**
```
brew install mongodb
```
```
brew install mongodb-community@4.2
```

**Після завантаження mongo**, створіть */data/db* directory в root
```
mkdir -p /data/db
```
В останньому Mac OS x ви стикаєтеся з такою проблемою, як:
```
mkdir: /data/db: Read-only file system
```

Тому ви більше не можете писати в корінь. Ось ще одне рішення (ми можемо
приймати dir де завгодно і під час виклику **mongo daemon** передати *- dbpath =
OUR_PATH / data / db*):
```
cd ~
mkdir -p data/db # preferably with sudo
```


**Запустіть Mongo daemon**, у терміналі:
```
# Absolute path in my case
mongod --dbpath=/Users/macair/data/db

# If you were able to make /data/db in root, then just
mongod
```
Це має запустити сервер Mongo.

**Запустіть Mongo shell**, при цьому Mongo daemon працює в одному терміналі,
введіть `mongo` в інше вікно терміналу. :
```
mongo
```
Це запустить оболонку Mongo, яка є додатком для доступу до даних у MongoDB.

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/mongo.png)


# Тестування mongo
Вставлення одна за одною команд:
```
# sets database with name 'use' for current usage, if it doesnt exist, it will be created
use test
# adds in collection 'users' of db 'test' object in json format
db.users.save( { name: "Tom" } )
# prints all objects from db 'test'
db.users.find()
```
![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/test1.png)

# Графічний Клієнт Compass
Натисніть сюди, щоб [завантажити](https://www.mongodb.com/download-center/compass)

Після установки за посиланням ми встановлюємо нове З'єднання, усі поля
встановлюються за замовчуванням.

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/compass1.png)

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/compass2.png)

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/compass3.png)

# Підключення до MongoDB за допомогою Compass

Завантажте Compass з [центру завантаження MongoDB](https://www.mongodb.com/download-center/compass). Якщо ви вже встановлини Compass, тоді переконайтеся, що ви використовуєте останню (стабільну) версію Compass та при необхідності оновіть. НЕ завантажуйте та не встановлюйте версію "Community Edition Stable". Встановіть його та запустіть.

Коли відкриється Компас, ви побачите сторінку під назвою "New Connection".
![](https://university-courses.s3.amazonaws.com/M001/Compass_start_screen.png)

Компас пропонує два способи підключення до розгортання:
- Використання рядка з'єднання
- Заповнення інформації про розгортання в окремих полях

**Використання рядка з'єднання**

Вставте цей рядок у поле рядка підключення та натисніть CONNECT.

```
mongodb+srv://student:mongodb-basics@cluster0-jxeqq.mongodb.net/test
```
Нагадуємо, що _student_ це логін _mongodb-basics_ це пароль до вашого облікового запису

Додавайте цей рядок з'єднання як улюблений. Це дозволить легко підключитися до розгортання нашого класу MongoDB після закриття та перезавантаження компаса. 

![](https://university-courses.s3.amazonaws.com/M001/Compass_add_favorite.png)

**Заповнення інформації про розгортання в окремих полях**

Якщо рядок підключення не працював для вас, ви можете вручну заповнити окремі поля та спробувати підключитись таким чином.

Клацніть на _Fill in connection fields individually_:

![](https://university-courses.s3.amazonaws.com/M001/Compass_fill_in_fields.png)

Використовуйте наступну інформацію, щоб заповнити цю форму, але не натискайте "Connect", поки ви не додасте це як своє улюблене з'єднання.

_Вкладка Hostname_

**Hostname**: cluster0-shard-00-00-jxeqq.mongodb.net

**Port**: 27017

**Authentication**: Username / Password

**Username**: student

**Password**: mongodb-basics

**Authentication Database**: admin


![](https://university-courses.s3.amazonaws.com/M001/Compass_hostname_connection.png)

Вкладка _More Options_

**Replica Set Name**: Cluster0-shard-0

**Read Preference**: Primary Preferred

![](https://university-courses.s3.amazonaws.com/M001/Compass_more_options_connection.png)

# Зверніть увагу, що mongod повинен працювати, інакше Компас не під'єднається

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/connection.png)

# Базові команди для роботи з MongoDB

**db.collection.insertOne()**

Призначення: Вставляє документ у колекцію.

Синтаксис:
```js
db.collection.insertOne(
   <document>
)
```

**db.collection.insertMany()**

Призначення: Вставляє декілька документів у колекцію.

Синтаксис:
```js
db.collection.insertOne(
   [ <document 1> , <document 2>, ... ]
)
```

**db.collection.updateOne()**

Призначення: Оновлення одного документа в колекції на основі фільтра.

Синтаксис:
```js
db.collection.updateOne(
   <filter>,
   <update>
)
```


**db.collection.updateMany()**

Призначення: Оновлення декількох документів в колекції на основі фільтра.

Синтаксис:
```js
db.collection.updateMany(
   <filter>,
   <update>
)
```

**db.collection.replaceOne()**

Призначення: Замінює один документ у колекції на основі фільтра.

Синтаксис:
```js
db.collection.replaceOne(
   <filter>,
   <replacement>
)
```


**db.collection.deleteOne()**

Призначення: Вилучає один документ із колекції.

Синтаксис:
```js
db.collection.deleteOne(
   <filter>
)
```


**db.collection.deleteMany()**

Призначення: Вилучає декілька документів із колекції.

Синтаксис:
```js
db.collection.deleteOne(
   <filter>
)
```

**db.collection.find()**

Призначення: Вибирає документи у колекції чи перегляді та повертає курсор до вибраних документів.

Синтаксис: 
```js
db.collection.find(
   { field1: <value>, field2: <value> ... }
)
```

# Приклад роботи з колекціями
Код для створення двух колекцій:
```js
const mongoose = require('mongoose');
const Article = require("../models/tests/articlesTest/Article");
const Comment = require("../models/tests/articlesTest/Comment");

const article = new Article({
  title: "COVID News",
  author: "amaterasu",
  body: "Here lies the body of the article",
})

const comment = new Comment({
  author: "amaterasu",
  body: "A very deep overview of the nowadays situation.",
  article,
})

const comment2 = new Comment({
  author: "amaterasu",
  body: "COVID is a lie.",
  article,
})

await comment.save();
await comment2.save();

article.comments = article.comments.concat(comment, comment2);
await article.save();
```

Отримаємо:

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/test-collection1.png)

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/test-collection2.png)

# Back-end userAPI:
```js
const { Router } = require("express");
const Test = require("../models/Test");
const User = require("../models/User");
const auth = require("../middleware/auth.middleware");
const router = Router();

router.post("/create", auth, async (req, resp) => {
  try {
    const newTest = new Test({
      name: req.body.testName,
      task: req.body.taskQuery,
      defaultInput: req.body.defaultInput,
      correctQuery: req.body.output,
    });

    const formed = await eval("(async () => {" + newTest.task + "})()");
    const res = await eval("(async () => {" + newTest.correctQuery + "})()");
    newTest.expectedOutput = res.toString();
    const queryResult = await newTest.save();

    resp.json({
      message: "Correct query",
      queryResult,
      created: formed,
      expected: res,
    });
  } catch (e) {
    console.log(e);
    resp.status(500).json({ message: "Something went wrong..." });
  }
});

router.get("/", auth, async (req, resp) => {
  try {
    const tests = await Test.find();
    resp.json({ tests });
  } catch (e) {
    resp.status(500).json({ message: "Something went wrong..." });
  }
});

router.post("/query", auth, async (req, resp) => {
  try {
    if (
      req.body.query.search("remove") < 0 &&
      req.body.query.search("update") < 0
    ) {
      const result = await eval("(async () => {" + req.body.query + "})()");
      const expectedOutput = req.body.activeTest.expectedOutput;
      if (result.includes(expectedOutput) || expectedOutput.includes(result)) {
        const completed = await Test.findOne({
          name: req.body.activeTest.name,
        });
        const user = await User.findById(req.user.userId);
        user.completedTests.push(completed);
        console.log(user);
        await user.save();
        resp.json({
          user,
          result,
          message: "success",
        });
      } else {
        resp.json({
          result,
          message: "failed",
        });
      }
    } else {
      resp.json({ message: "Error processing your request" });
    }
  } catch (e) {
    console.log(e);
    resp.status(500).json({ message: "Something went wrong..." });
  }
});

module.exports = router;
```

# Оператори запитів(query) та проекцій(projection)

_для кожного селектору є посилання з прикладами_

## Селектори запитів

| Name   | Description                                                         |
|--------|:-------------------------------------------------------------------:|
| [$eq](https://www.bookstack.cn/read/mongodb-4.2-manual/6340320dc3dfc823.md#op._S_eq)	   | Відповідає значенням, рівним заданому значенню.                     | 
| [$gt](https://www.bookstack.cn/read/mongodb-4.2-manual/b18f99cdd71e3948.md#op._S_gt)	   | Відповідає значенням, що перевищують задане значення.               |
| [$gte](https://www.bookstack.cn/read/mongodb-4.2-manual/69028f025e729a31.md#op._S_gte)	| Відповідає значенням, що більше або дорівнює заданому значенню.     |
| [$in](https://www.bookstack.cn/read/mongodb-4.2-manual/17161a7651d20b5a.md#op._S_in)	   | Відповідає будь-якому зі значень, вказаних у масиві.                |
| [$lt](https://www.bookstack.cn/read/mongodb-4.2-manual/750260d4249e8c35.md#op._S_lt)	   | Відповідає значенням, меншим за вказане значення.                   |
| [$lte](https://www.bookstack.cn/read/mongodb-4.2-manual/eea81d13c92ecd5f.md#op._S_lte)	| Відповідає значенням, меншим або рівним заданому значенню.          |
| [$ne](https://www.bookstack.cn/read/mongodb-4.2-manual/bd164579d80de3c9.md#op._S_ne)	   | Відповідає всім значенням, не рівним заданому значенню.             |
| [$nin](https://www.bookstack.cn/read/mongodb-4.2-manual/a2c67159e3c89845.md#op._S_nin)	| Не відповідає жодному зі значень, вказаних у масиві.                |

## Логічні

| Name	| Description                                                                                                     |
|--------|:---------------------------------------------------------------------------------------------------------------:|
| [$and](https://www.bookstack.cn/read/mongodb-4.2-manual/0ac9f896539e32b6.md#op._S_and)	| Приєднується до запитів із логічним ```AND``` повертає всі документи, які відповідають умовам обох пунктів.     |
| [$not](https://www.bookstack.cn/read/mongodb-4.2-manual/3d1841137078acd3.md#op._S_not)	| Інвертує вираження запиту та повертає документи, які не відповідають виразу запиту.                             |
| [$nor](https://www.bookstack.cn/read/mongodb-4.2-manual/df28b9509c0a357d.md#op._S_nor)	| Приєднується до запитів із логічним ```NOR``` повертає всі документи, які не відповідають обом пунктам.         |
| [$or](https://www.bookstack.cn/read/mongodb-4.2-manual/0c1c9c15f2142aa5.md#op._S_or)	   | Приєднується до запитів із логічним ```OR``` повертає всі документи, які відповідають умовам будь-якого пункту. |

## Елемент

| Name	   | Description                                   | 
|-----------|:---------------------------------------------:|
| [$exists](https://www.bookstack.cn/read/mongodb-4.2-manual/4add7c495fb97712.md#op._S_exists)	| Відповідає документам, що мають вказане поле. |
| [$type](https://www.bookstack.cn/read/mongodb-4.2-manual/2c4a8fe9a41bc1ac.md#op._S_type)	   | Вибирає документи, якщо поле вказаного типу.  |

## Оцінення

| Name	      | Description                                                                                        |
|--------------|:--------------------------------------------------------------------------------------------------:|
| [$expr](https://www.bookstack.cn/read/mongodb-4.2-manual/b901afb7f2d4a064.md#op._S_expr)	      | Дозволяє використовувати вирази агрегації в мові запиту.                                           |
| [$jsonSchema](https://www.bookstack.cn/read/mongodb-4.2-manual/1bd456d35e6d6b5e.md#op._S_jsonSchema)	| Обгрунтуйте документи щодо даної схеми JSON.                                                       |
| [$mod](https://www.bookstack.cn/read/mongodb-4.2-manual/fccf3a5c1e8c9ba5.md#op._S_mod)	      | Виконує модульну операцію над значенням поля та вибирає документи із заданим результатом.          |
| [$regex](https://www.bookstack.cn/read/mongodb-4.2-manual/83747e50d5c91415.md#op._S_regex)	      | Вибирає документи, у яких значення відповідають заданому регулярному виразу.                       |
| [$text](https://www.bookstack.cn/read/mongodb-4.2-manual/6b560c502d5a7e0e.md#op._S_text)	      | Здійснює пошук тексту.                                                                             |
| [$where](https://www.bookstack.cn/read/mongodb-4.2-manual/4781820d20f6b9c9.md#op._S_where)	      | Відповідає документам, що задовольняють вираз JavaScript.                                          |

## Масив

| Name	      | Description                                                                               |
|--------------|:-----------------------------------------------------------------------------------------:|
| [$all](https://www.bookstack.cn/read/mongodb-4.2-manual/5591935e963488aa.md#op._S_all)	      | Збігає масиви, які містять усі елементи, вказані в запиті.                                |
| [$elemMatch](https://www.bookstack.cn/read/mongodb-4.2-manual/df0d30f33b468592.md#op._S_elemMatch)	| Вибирає документи, якщо елемент у полі масиву відповідає всім заданим умовам $ elemMatch. |
| [$size](https://www.bookstack.cn/read/mongodb-4.2-manual/1f2e158b67d9160d.md#op._S_size)	      | Вибирає документи, якщо поле масиву заданого розміру.                                     |

## За приклад візьмемо: 

### $gte

_**Syntax: {field: {$gte: value} }**_

Цей запит вибере всі документи в ```inventory```, де значення кількості поля більше або дорівнює ```20```.

```js
db.inventory.find( { qty: { $gte: 20 } } )
```

Ця операція update () встановлює значення ```price``` поля, яке містить вбудований носій документа ```carrier```, значення поля ```fee``` перевищує або дорівнює ```2```.

```js
db.inventory.update( { "carrier.fee": { $gte: 2 } }, { $set: { price: 9.99 } } )
```

### $elemMatch (query)

_**Syntax: { <field>: { $elemMatch: {<query1>,<query2>, ... } } }**_
 
Враховуючи такі документи в колекції: 

```js
{ _id: 1, results: [ 82, 85, 88 ] }
{ _id: 2, results: [ 75, 88, 89 ] }
```

Наступний запит відповідає лише тим документам, де масив ```results``` містить щонайменше один елемент, який є більшим або рівним ```80``` та менше ```85```.

```js
db.scores.find(
   { results: { $elemMatch: { $gte: 80, $lt: 85 } } }
)
```

Запит поверне 

```js
{ "_id" : 1, "results" : [ 82, 85, 88 ] }
```


# Інші приклади

Припустимо, ми маємо моделювати структуру, яка містить списки розсилки та дані
про людей. Приклад [тут](https://habr.com/ru/post/144798/)

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/schema.png)

Наступні вимоги:
* У людини може бути одна або кілька адрес електронної пошти;
* Людина може перебувати в будь-якій кількості списків розсилки;
* Людина може вибрати будь-яке ім’я для будь-якого списку розсилки, в якому вона
перебуває.

Давайте подивимось, як буде виглядати наша модель даних, якщо ніде дані не
вбудовуються.

**People** з ім'ям та паролем

```js
{
    _id: PERSON_ID,
    name: "Name Surname",
    pw: "Hashed password"
}
```

**Adresses** де кожен email прив'язується до конкретного абонента
```js
{
    _id: ADDRESS_ID,
    person: PERSON_ID,
    address: "vpupkin@gmail.com"
}
```

**Groups** ми можемо визначити деякі додаткові поля
```js
{
    _id: GROUP_ID
}
```

**Memberships** об’єднує людей у ​​групи

```js
{
    _id: MEMBERSHIP_ID,
    person: PERSON_ID,
    group: GROUP_ID,
    address: ADDRESS_ID,
    group_name: "Семья"
}
```

Ця модель даних чітка, проста у розробці та проста у обслуговуванні. Ми створили
модель, яку зручно використовувати в db SQL. У той же час ми не врахували
документоорієнтований підхід MongoDB.

Давайте подивимось, що ми зробимо, щоб, наприклад, отримати електронні адреси
всіх членів однієї групи, якщо ми маємо одну відому адресу електронної пошти та
назву цієї групи:

1. У колекції Adresses за відомою електронною поштою ми знаходимо PERSON_ID;
2. У колекції Memberships за отриманою PERSON_ID та відомою назвою Групи
знаходимо GROUP_ID;
3. Знову в колекції Memberships за отриманим GROUP_ID знаходимо список підписок
цієї групи;
4. І нарешті, із колекції адрес ADDRESS_ID, переглядаючи кожну підписку зі
списку отриманих, ми отримуємо список адрес електронної пошти.


## Модель з частково вбудованими даними
**People**
```js
{
    _id: PERSON_ID,
    name: "Name Surname",
    pw: "Hashed password",
    addresses: ["random@gmail.com", "random@mail.ru", ...],
    memberships: [{
        address: "random@gmail.com",
        group_name: "mongodb tutorial",
        group: GROUP_ID
    }, ...]
}
```

**Groups** ми можемо визначити деякі додаткові поля
```js
{
    _id: GROUP_ID
}
```
Запит, про який ми говорили вище, тепер виглядатиме так:

1. У колекції People ми знаходимо абонента з потрібною адресою електронної
пошти, серед підписок якої є группа з потрібним іменем;
2. Використовуючи GROUP_ID знайденої підписки, ми знайдемо інших людей цієї
групи в колекції People і отримаємо їхні електронні адреси безпосередньо з
підписки.

```js
people = [
               {
                 "_id": 1,
                 "name": "Name1 Surname1",
                 "pw": "1111",
                 "addresses": ["beefmilf@gmail.com", "beefmilf@mail.ru"],
                 "memberships": [
                                 {"address": "beefmilf@gmail.com", "group_name": "group1", "group": 1},
                                 {"address": "beefmilf@gmail.com", "group_name": "group2", "group": 2}
                                 ]
               },
               {
                 "_id": 2,
                 "name": "Name2 Surname2",
                 "pw": "2222",
                 "addresses": ["convmonk@gmail.com", "convmonk@mail.ru"],
                 "memberships": [
                                 {"address": "convmonk@gmail.com", "group_name": "mongo tutorial", "group": 1},
                                 {"address": "convmonk@mail.ru", "group_name": "mongoose", "group": 2},
                                 {"address": "convmonk@gmail.com", "group_name": "something", "group": 3}
                                 ]
               },
               {
                 "_id": 3,
                 "name": "Name3 Surname3",
                 "pw": "3333",
                 "addresses": ["random@gmail.com", "random@mail.ru"],
                 "memberships": [
                                 {"address": "random@gmail.com", "group_name": "rand name 1", "group": 1},
                                 {"address": "random@gmail.com", "group_name": "rand name 1", "group": 2},
                                 {"address": "random@mail.ru", "group_name": "rand name 1", "group": 3}
                                 ]
               },
               {
                 "_id": 4,
                 "name": "Name4 Surname4",
                 "pw": "3333",
                 "addresses": ["bot2001@gmail.com", "bot2001@mail.ru"],
                 "memberships": [
                                 {"address": "bot2001gmail.ru", "group_name": "mongo tutorial", "group": 1},
                                 {"address": "bot2001@gmail.com", "group_name": "mongoose", "group": 2},
                                 {"address": "bot2001@gmail.com", "group_name": "something", "group": 3}
                                 ]
               }

]

groups = [
          {"_id": 1}, 
          {"_id": 2}, 
          {"_id": 3}
]
```

Створіть колекцію people та додайте 4 документи

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/people1.png)

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/people2.png)

## Installation mongodb for node.js

```
npm install mongodb
```

```js
%%node
// create MongoClient object
var MongoClient = require('mongodb').MongoClient, format = require('util').format;
// create a db in mongodb, specify a connection URL with the correct ip address
// and the name of the database you want to create,
var url = 'mongodb://localhost:27017/';

// group_id for finding all group's emails
var group_id;

MongoClient.connect(url, function(err, db) {
    if (err) throw err;
    // connecting to db 'mail', collection 'people'
    const db_ = db.db('mail');
    var collection = db_.collection('people');

    // for example, we have person's addres and group_name, due to them we get then id in a field 'group'
    var query =  {'addresses': 'convmonk@gmail.com', 'memberships.group_name': 'something'};
    // which fields to get from query
    var field = {'memberships.group_name': 1, 'memberships.group': 1, '_id': 0};

    // this block finds to doc with query params and assigns 'group' value to var 'group_id'
    // findOne takes: query, fields to get, function
    collection.findOne(query, {'projection': field}, function (err, res) {
        if (err) throw err;
        if (res) {
            // when we use forEach, all records are loaded into memory
            res.memberships.forEach(function (res) {
                if (res.group_name == 'something') {
                    group_id = res.group;
                }
            });
        }


        var query = {'memberships.group': group_id};
        var field = {'addresses': 1};
        // this block finds all emails of people who have membership in group with group_id
        // just logs result to console
        collection.find(query, {'projection': field}, function (err, res) {
            if (err) throw err;
            res.forEach(function (res) {
                console.log(res);
            });
        });
        db.close();
    });
});
```


**Result:**
the first `id` is excluded as long as it has no membership in group with
`group_id`
```js
{ _id: 2,
  addresses: [
    'convmonk@gmail.com',
    'convmonk@mail.ru'
    ]
}
{ _id: 3,
  addresses: [
    'random@gmail.com',
    'random@mail.ru'
    ]
}
{ _id: 4,
  addresses: [
    'bot2001@gmail.com',
    'bot2001@mail.ru'
    ]
}
  ```


```js
%%node
// create MongoClient object
var MongoClient = require('mongodb').MongoClient, format = require('util').format;
// create a db in mongodb, specify a connection URL with the correct ip address
// and the name of the database you want to create,
var url = 'mongodb://localhost:27017/';


MongoClient.connect(url, function(err, db) {
    if (err) throw err;

    // connecting to db 'mail', collection 'people'
    const db_ = db.db('mail');
    var collection = db_.collection('people');

    // addresses to delete, it is also used in 'memberships.address'
    var query = {'addresses': 'convmonk@gmail.com'};
    var field = {'addresses': 1, 'memberships.address': 1};
    
    // firsty lets find res 
    collection.findOne(query, {'projection': field}, function (err, res) {
        if (err) throw err;
        
        // get rid of 'addresses' in query 
        var addrs = res.addresses.filter(function (e) {return e != query.addresses});
        
        // if addrs empty, we just delete document 
        if (!addrs.length){
            collection.deleteOne({'_id': res._id});
        }
        // if addrs exists, we delete 'addresses' in query and change all 'memberships.address' == query.addresses 
        // to the first accessible address in addresses 
        else {
            // get first accessible address for change 
            var addr = addrs[0];
            
            collection.updateOne(
                query, // filter 
                {
                    // first param means set to each element's field 'address' and in arrayFilter we define condition
                    // which elem exactly to change for addr
                    // second param just filtered array of addresses
                    $set: {'memberships.$[elem].address': addr, 'addresses': addrs}
                },
                {
                    multi: true, // default false, applied just to the first match
                    arrayFilters: [{'elem.address': query.addresses}] // means if elem.address == query.addresses
                },
                function (err, res) {
                    if (err) throw err;
                    
                    // res of operation 
                    console.log(res);
                }
                );
        }
        db.close();
    });

});
```

Джерела, які були використані в останньому коді:
*[$[\<identifier\>]](https://docs.mongodb.com/master/reference/operator/update/positional-
filtered/)*

[db.collection.updateOne](https://docs.mongodb.com/manual/reference/method/db.collection.updateOne/)

**Результат:** ми видалили `"convmonk@gmail.com"` і змінили `"address"` поля

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/remove1.png)

# Mongoose ODM

Mongoose - це ODM (* Object Document Mapper - об'єктно-документний відображувач). Це означає, що Mongoose дозволяє вам визначати об'єкти зі строго-типізованою схемою, яка відповідає документу MongoDB.

Mongoose надає величезний набір функціональних можливостей для створення і роботи зі схемами. На даний момент Mongoose містить вісім SchemaTypes (* типи даних схеми), які можуть мати властивість, яка зберігається в MongoDB. Ці типи наступні:

* String
* Number
* Date
* Buffer
* Boolean
* Mixed
* ObjectId (* унікальний ідентифікатор об'єкта, первинний ключ, _id)
* Array

## Installation

```
npm install mongoose
```


Types:


```js
var schema = new Schema(
{
  name: String,
  binary: Buffer,
  living: Boolean,
  updated: { type: Date, default: Date.now },
  age: { type: Number, min: 18, max: 65, required: true },
  mixed: Schema.Types.Mixed,
  _someId: Schema.Types.ObjectId,
  array: [],
  ofString: [String], // You can also have an array of each of the other types
too.
  nested: { stuff: { type: String, lowercase: true, trim: true } }
})
```

```js
%%node

// import mongoose lib
var mongoose = require('mongoose');

// connection
var url = 'mongodb://localhost:27017/mail';
// first two keys for ignoring some warnings of deprecation
mongoose.connect(url, {useUnifiedTopology: true, useNewUrlParser: true,  autoIndex: false});

// define schema
var Schema = mongoose.Schema;
var peopleSchema = new Schema({
    _id: {
        type: Number,
        unique: true,
        required: true,
        auto: true
    },
    pw: {
        type: String,
        minlength: 4,
        maxlength: 32,
        required: true,
    },
    name: {
        type: String,
        minlength: 4,
        maxlength: 32,
        required: true
    },
    addresses: {
        type: Array,
        required: true,
        validate: function (array) {
            if (array.length === 0) return false;
            return array.every((v) => typeof v === 'string');
        }
    },
    memberships: {
        type: Array
    }
});
// compiling model from schema 
var Person = mongoose.model('Person', peopleSchema);
```

Якщо ми не вкажемо * {autoIndex: false} *, ми можемо спостерігати:
```
mongoose: Cannot specify a custom index on `_id` for model name "Person",
MongoDB does not allow overwriting the default `_id` index.   See
http://bit.ly/mongodb-id-index
```
> Here is [explanation](https://mongoosejs.com/docs/guide.html), in the section
**Index**


# Валідація
Mongoose забезпечує вбудовані валідатори, валідатори користувачів, синхронні та
асинхронні валідатори. У всіх випадках ви можете вказати дійсні діапазони або
значення, а також повідомлення про помилки, якщо порушено умови перевірки.

Вбудовані валідатори включають:
* Усі схеми SchemaType мають вбудований необхідний валідатор, який визначає, чи
слід встановлювати поле перед збереженням документа.
* Числа мають валідатори min та max.
* У рядках:
* * enum (перерахування): вказати набір допустимих значень для поля.
* * match (match)): задає регулярний вираз, що рядок повинен відповідати.
* * maxlength, minlength - максимальна і мінімальна довжина струни.

> here is more [info](https://mongoosejs.com/docs/validation.html)

Простий приклад перевірки:

```js
%%node
// create new doc for testing validation
var item = new Person({
    _id: 2,
    pw: "0000",
    name: "bhsdsb",
    addresses: ['email@gmail.com']
});

item.validate(function(err) {
    if (err)
        console.log(err.message);
    else
        console.log('pass validate');
    }
);
```

Знову, знайдіть усі електронні листи людей, які мають членство в групі з
"group_name" особи з "addresses"

```js
var query_fields = {'addresses': 'convmonk@gmail.com', 'memberships.group_name': 'something'};
var select = {'memberships.group_name': 1, 'memberships.group': 1, '_id': 0};

var group_id;

// select is used as 'projection' param in mongodb 
var query = Person.findOne(query_fields).select(select);

// same code as in mongodb example
query.exec(function (err, res) {
    if (err) return err;
    console.log(res.memberships);
    if (res) {
        res.memberships.forEach(function (res) {
            if (res.group_name === 'something') {
                group_id = res.group;
            }
        });
    }

    var query_fields = {'memberships.group': group_id};
    var select = {'addresses': 1};
    Person.find(query_fields).select(select).exec(function (err, res) {
        if (err) throw err;
        res.forEach(function (res) {
            console.log(res);
        });
    });
});
```

# Promise
Уявіть, що ви відомий співак, якого шанувальники постійно домагають питаннями
щодо майбутнього синглу.

Щоб отримати перерву, ви обіцяєте надіслати їм сингл, коли він вийде. Ви надаєте
шанувальникам список, на який вони можуть підписатися. Вони можуть залишити свою
електронну пошту там, щоб отримати пісню, як тільки вона вийде. І навіть більше:
якщо щось піде не так, наприклад, в студії буде пожежа, і пісня не може бути
випущена, вони також отримають повідомлення про це.

1. Існує код "створення", який робить щось, на що потрібно час. Наприклад, він
завантажує дані по мережі. За нашою аналогією, це "співак".
2. Існує "споживчий" код, який хоче отримати результат коду "створення", коли
він буде готовий. Для цього може знадобитися для декількох функцій. Це "фани".
3. `Promise` ([`згода`](https://learn.javascript.ru/promise-basics), ми будемо
називати такий об’єкт «Promis») - це спеціальний об’єкт у JavaScript, який
посилається на "створення" та "споживання" кодів разом. З точки зору нашої
аналогії, це "список підписки". Код "створення" може бути виконаний стільки,
скільки потрібно для отримання результату, а обіцянка робить результат доступним
для коду, який підписаний до нього, коли результат буде готовий.

Синтаксис створення Promise:

```js
let promise = new Promise(function(resolve, reject) {
  // function (executor)
  // "singer"
});
```

Функція, передана в конструкції `new Promise`, називається виконавцем. Коли
створено Обіцяння, воно запускається автоматично. Він повинен містити
"створюючий" код, який колись дасть результат. З точки зору нашої аналогії:
виконавець - «співак».

Його аргументи `resolve` та` reject` - це зворотні виклики(callbacks), які надає
сам JavaScript. Наш код лише всередині виконавця.

Коли він отримує результат, зараз чи пізніше - це не має значення, він повинен
викликати в один з таких зворотних дзвінків:

* `resolve` (value) - якщо операція завершена успішно, з результатом value.
* `reject` (error) - якщо сталася помилка, error - object of the error.

Отже, виконавець запускається автоматично, він повинен виконати роботу, а потім
викликати `resolve` or `reject`.

Об'єкт `promise`, повернений конструктором` new Promise`, має внутрішні
властивості:
* `state` - спочатку очікує на розгляд(pending), потім змінюється на
виконання(fulfilled), коли викликається рішення(resolve), або відхиляється, коли
викликається відхилення(reject).
* `result` - спочатку не визначено(undefined), потім змінюється на значення при
виклику рішення (value) або на помилку при відхиленні виклику (error)


![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/promise.png)

```js
function logger(doc) {
    console.log(doc);
}

// promise findOne
// null is projection argument(but then we use select)
// {emptyError: true} just not to check if res is null   
var prom = Person.findOne(query_fields, null, {lean: true, emptyError: true}) 
    .select(select)
    .then(doc => {
        doc.memberships.forEach(function (doc) {
            if (doc.group_name === 'something') {
                group_id = doc.group;
            }
        });
    })
    .then(() => {
        var query_fields = {'memberships.group': group_id};
        var select = {'addresses': 1};
        Person.find(query_fields).select(select).exec(function (err, res) {
            if (err) throw err;
            res.forEach(function (res) {
                logger(res);
            });
        });
    })
    .catch(err => {
        console.log(err);
    });
```

Update/delete promise

```js
var query_fields = {'addresses': 'convmonk@gmail.com'};
var select = {'addresses': 1, 'memberships.address': 1};


function update(doc, addrs) {
    if (!addrs.length){
        Person.deleteOne({'_id': doc._id});
    }
    else {
        var addr = addrs[0];
        Person.updateOne(
            query_fields,
            { $set: {'memberships.$[elem].address': addr, 'addresses': addrs} },
            {
                multi: true, // default false, applied just to the first match
                arrayFilters: [{'elem.address': query_fields.addresses}] // means if elem.address == query.addresses
            },
            {new: true},
            function (err, res) {
                if (err) throw err;

                // res of operation
                console.log(res);
            }
        );
    }
}

// promise update/delete
var prom = Person.findOne(query_fields, null, {emptyError: true})
    .select(select)
    .then(doc => {
        var addrs = doc.addresses.filter(function (e) {return e !== query_fields.addresses});
        update(doc, addrs);
    })
    .catch(err => {
    console.log(err.message);
});
```

# Підключення Atlas

**Що таке Atlas?**

- База даних як послуга
- Зберігає дані у хмарі
- Обробляє реплікацію: підтримання зайвих копій даних для збільшення доступності даних

**Як працює Atlas?**

Користувачі Atlas можуть розгорнути кластери, що представляють собою групи серверів, які зберігають ваші дані.
Ці сервери налаштовані в тому, що ми називаємо набір реплік, який є кластером, де кожен сервер зберігає однакові дані.

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/cluster.jpg)

Це означає, що щоразу, коли ви вставляєте або оновлюєте документ, надлишки копій зберігаються у наборі.
Використання набору реплік гарантує, що якщо ви втратите доступ до одного сервера у своєму кластері, ви не збираєтеся втрачати свої дані.
Усі сервери вашого кластеру існують у хмарі на обраного вами постачальника хмарних послуг.

![](https://github.com/BeefMILF/MongoDB-tutorial/raw/master/doc/photos/cluster-lose.jpg)

**Чому ми повинні використовувати Atlas?**

Однією з головних причин є простота налаштування.
Atlas керує деталями створення кластерів для вас, що спрощує оперативні витрати на виконання розгортання.
Інтерфейс Atlas полегшує управління та розгортання MongoDB через хмарні постачальники та регіони.
Atlas - це також чудовий спосіб експериментувати з новими інструментами та можливостями MongoDB.

**Створення свого кластера-пісочниці**

Якщо у вас немає облікового запису Atlas, [створіть](https://www.mongodb.com/university-signup)
Після створення нового облікового запису вам буде запропоновано створити ваш перший кластер:

![](https://university-courses.s3.amazonaws.com/M001/cluster_create.png)

Тепер ви повинні обрати хмарного постачальника (провайдера) для свого кластера. 
Виберіть AWS як постачальника хмарних ситуацій, а для регіону _Region_ виберіть місце, найближче до вас, яке має мітку _Free Tier Available_. Зауважте, що місцем розташування за замовчуванням є _N.Virginia (us-east-1). Free Tier Available_

![](https://s3.amazonaws.com/university-courses/m220/cluster_provider.png)

Виберіть кластер рівня M0 Sandbox:

![](https://university-courses.s3.amazonaws.com/M001/cluster_tier.png)

Клацніть на Cluster Name, введіть "Sandbox" у відповідне текстове поле та натисніть "Create Cluster":

![](https://university-courses.s3.amazonaws.com/M001/m001_cluster_name.png)

Після створення кластера вас буде переспрямовано на інформаційну панель облікового запису:

![](https://university-courses.s3.amazonaws.com/M001/account_dashboard.png)

Перейдіть до Settings та змініть назву проекту на "M001":

![](https://university-courses.s3.amazonaws.com/M001/m001_project_rename.png)

Потім налаштуйте параметри безпеки цього кластеру, включивши Білий список IP Whitelist:

Оновіть свій білий список IP-адрес, щоб ваша програма могла спілкуватися з кластером. Перейдіть на вкладку "Network Access", а потім натисніть "Add IP Address".

![](https://university-courses.s3.amazonaws.com/M001/m001_ip_whitelisting0.png)

На екрані з’явиться нове запит із запитом "Add Whitelist Entry". Клацніть на "Allow Access from Anywhere", а потім натисніть "Confirm".

![](https://university-courses.s3.amazonaws.com/M001/m001_ip_whitelisting.png)

_Зауважте, що ми зазвичай не рекомендуємо відкривати кластер Atlas, щоб дозволити доступ з будь-якого місця. Ми робимо це для цього класу, щоб мінімізувати проблеми з мережею, з якими ви можете зіткнутися._

Потім створіть додаток MongoDB користувача, необхідного для цього курсу.

Перейдіть на вкладку "Database Access", а потім натисніть "ADD NEW USER".

![](https://university-courses.s3.amazonaws.com/M001/m001_user0.png)

Запам'ятайте свої логін та пароль та нікому не кажіть. Однак для спроби, можете створити користувача з такими обліковими даними:

- ім'я користувача: student
- пароль: mongodb-basics

Дайте цьому користувачеві привілей Read and write to any database:

![](https://s3.amazonaws.com/university-courses/M001/m001_user.png)

Вітаємо вас зі створенням першого Atlas застосунку! Тепер у вас є база даних MongoDB, до якої ви можете отримати доступ з будь-якої точки світу.

# Тестування jest-mongodb

[Jest MongoDB](https://github.com/shelfio/jest-mongodb) забезпечує всю необхідну конфігурацію для запуску тестів за допомогою MongoDB.

1. Спочатку встановіть @shelf/jest-mongodb
```js
yarn add @shelf/jest-mongodb --dev
```

2. Вкажіть попередньо встановлене налаштування в Jest-конфігурації:
```js
{
  "preset": "@shelf/jest-mongodb"
}

```

3. Напишіть свій тест:
```js
const {MongoClient} = require('mongodb');

describe('insert', () => {
  let connection;
  let db;

  beforeAll(async () => {
    connection = await MongoClient.connect(global.__MONGO_URI__, {
      useNewUrlParser: true,
    });
    db = await connection.db(global.__MONGO_DB_NAME__);
  });

  afterAll(async () => {
    await connection.close();
    await db.close();
  });

  it('should insert a doc into collection', async () => {
    const users = db.collection('users');

    const mockUser = {_id: 'some-user-id', name: 'John'};
    await users.insertOne(mockUser);

    const insertedUser = await users.findOne({_id: 'some-user-id'});
    expect(insertedUser).toEqual(mockUser);
  });
});
```

Немає необхідності завантажувати залежності.
