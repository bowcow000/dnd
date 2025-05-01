# dnd

ЗАДАНИЕ/РЕШЕНИЕ/СКРИНШОТ

## **#1 ЗАДАНИЕ:**

Выберите из таблицы orders все заказы

### **РЕШЕНИЕ:**

```
SELECT * FROM orders;
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/72e879df-c678-4c79-a638-86255e888035)


## **#2 ЗАДАНИЕ:**

Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in

### **РЕШЕНИЕ:**

```
SELECT * FROM orders
WHERE not STATUS IN ('new')
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/5e4db919-bb92-4f9b-8d1f-72dad829a440)

## **#3 ЗАДАНИЕ:**

Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new".

### **РЕШЕНИЕ:**

```
SELECT * FROM orders
WHERE STATUS IN ('new', 'cancelled')
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/461764da-cc08-4d06-acd1-d852d708564e)

## **#4 ЗАДАНИЕ:**

Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).
Вывести нужно только номер (id) и сумму (sum) заказа.

### **РЕШЕНИЕ:**

```
SELECT id,sum FROM orders
WHERE products_count > 3
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/85494cbd-ac27-424a-8fff-501665c80438)





# **22.02.25**

## **#1 ЗАДАНИЕ:**

Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

### **РЕШЕНИЕ:**

```
SELECT * FROM orders
WHERE STATUS != 'cancelled'
ORDER BY SUM
LIMIT 3
```

### **СКРИНШОТ ТАБЛИЦЫ:**

![image](https://github.com/user-attachments/assets/d567e26a-a341-4f7d-bce7-c4936188e6c8)

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/d3a74684-86fb-4c48-b403-7f647988ba6c)


## **#2 ЗАДАНИЕ:**

Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

### **РЕШЕНИЕ:**

```
SELECT * FROM orders
WHERE STATUS != 'cancelled'
ORDER BY SUM DESC
LIMIT 2
```

### **СКРИНШОТ ТАБЛИЦЫ:**

![image](https://github.com/user-attachments/assets/2ebf0f42-72ab-413b-8954-856a9d167196)

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/50d4cad0-31f1-4243-b52f-2a166ec26a02)



## **#3 ЗАДАНИЕ:**

Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).

### **РЕШЕНИЕ:**

```
INSERT INTO orders (id, products, SUM) VALUE (6, 3, 8000)
```

### **СКРИНШОТ ТАБЛИЦЫ:**

![image](https://github.com/user-attachments/assets/1230bb2d-25b3-41c9-81db-64fcbf8232b5)

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/129d7294-6045-44b9-829e-fd51d4d11e6d)

![image](https://github.com/user-attachments/assets/5d34739f-99e3-40ce-94d9-612db7713250)



## **#4 ЗАДАНИЕ:**

Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.

### **РЕШЕНИЕ:**

```
INSERT INTO products
(id, NAME, count, price)
VALUE (7, 'VR-очки', 2, 70000)
```

### **СКРИНШОТ ТАБЛИЦЫ:**

![image](https://github.com/user-attachments/assets/da865a8e-0c0c-45f5-9610-5d1f0b70996d)

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/2881fe53-e05e-4ecf-a631-53a7a3df2bfb)

![image](https://github.com/user-attachments/assets/b41f8f4b-1617-432b-ac45-6eee12a5eedd)


## **#5 ЗАДАНИЕ:**

В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.

### **РЕШЕНИЕ:**

```
UPDATE products SET NAME='PS5' where NAME = 'IMAC'
```

### **СКРИНШОТ ТАБЛИЦЫ:**

![image](https://github.com/user-attachments/assets/3715da01-4aa9-4b9a-a96a-0c4101019dd6)

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/4eebef6a-5acb-4cea-97f6-32cf3c45edab)

![image](https://github.com/user-attachments/assets/f43221df-48d1-4297-b4ce-79a36d28c75e)





# **01.03.25**

## **#1 ЗАДАНИЕ:**

Создайте таблицу users с полем id типа INT и двумя текстовыми полями, которые будут хранить имя (first_name) и фамилию (last_name). Длина имени и фамилии не превышает 50 символов.

Добавьте в таблицу трех пользователей: Дмитрия Иванова, Анатолия Белого и Дениса Давыдова.

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS users;

CREATE TABLE users (
  id INT NOT NULL,
  first_name VARCHAR(50) NOT NULL,
  last_name VARCHAR(50) NOT NULL
);

INSERT INTO users (id, first_name, last_name) VALUES
(1, "Дмитрия", "Иванова"),
(2, "Анатолий", "Белов"),
(3, "Денис", "Давыдов"),
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/074cb495-7bcf-4391-ba43-671e5c807466)

![image](https://github.com/user-attachments/assets/9b58bfd6-503d-4324-95c0-ec985de42445)





# **15.03.25**

## **#1 ЗАДАНИЕ:**

Создайте таблицу users для хранения информации о пользователях сайта.
В таблице должны быть следующие поля:

id – идентификатор, целое положительное;
email – адрес электронной почты, строка не более 100 символов;
date_joined – дата регистрации (достаточно хранить дату, без времени)
last_activity – дата и время последней активности (с точностью до секунд).

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS users;

CREATE TABLE users (
    id INT,
    email VARCHAR(100) NOT NULL,
	 date_joined DATE NOT NULL,
	 last_activity DATETIME NOT NULL
);

INSERT INTO users (id, email, date_joined, last_activity) VALUES
(1, "user1@domain.com", "2014-12-12", "2016-04-08 12:34:54"),
(2, "user2@domain.com", "2014-12-12", "2017-02-13 11:46:53"),
(3, "user3@domain.com", "2014-12-13", "2017-04-04 05:12:07");
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/2f07fb55-5dd2-4a06-8643-e0ea762a051f)

![image](https://github.com/user-attachments/assets/6c1a1f5c-8d2f-4968-b64a-960ea8548ba8)

## **#2 ЗАДАНИЕ:**

Создайте таблицу calendar для хранения календаря посетителей.
В таблице должны быть следующие поля:

id – идентификатор записи в календаре, целое положительное;
user_id – идентификатор пользователя, целое положительное;
doctor_id – идентификатор доктора, целое положительное;
visit_date – дата и время визита (точность до секунд).

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS calendar;

Create table calendar (
id INT UNSIGNED,
user_id INT UNSIGNED NOT NULL,
doctor_id INT UNSIGNED NOT NULL,
visit_date DATETIME NOT NULL);

INSERT INTO calendar (id, user_id, doctor_id, visit_date) VALUES
(1, 1914 , 1, '2017-04-08 12:00:00'),
(2, 12, 1, '2017-04-08 12:30:00'),
(3, 4641, 2, '2017-04-09 09:00:00'),
(4, 784, 1,'2017-04-09 09:00:00'),
(5, 15, 2,'2017-04-09 10:00:00');
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/47bf6611-9218-4d12-b683-a10ab7ecf29e)

![image](https://github.com/user-attachments/assets/4f16ec96-c4cd-4909-832d-22725c1794b9)


## **#3 ЗАДАНИЕ:**

Создайте таблицу users , в которой будут следующие поля:

id — идентификатор, целые положительные числа.
first_name— имя, строки до 50 символов.
last_name — фамилия, строки до 60 символов.
bio — биография, текст до 65000 символов.

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS users;

create table users (
	id INT(10) UNSIGNED,
	first_name VARCHAR(50) NOT NULL,
	last_name VARCHAR(60) NOT NULL,
	bio TEXT
);

INSERT INTO users (id, first_name, last_name, bio) VALUES
(1,'Антон','Кулик','С отличием окончил 39 лицей.'),
(2,'Сергей','Давыдов',''),
(3,'Дмитрий','Соколов','Профессиональный программист.');
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/3c3cfd4e-b6fe-4d19-9652-22c04f788ea7)

![image](https://github.com/user-attachments/assets/d3ea0c32-4f69-4eb6-b776-4c1fd4ad6263)





# **29.03.25**

## **#1 ЗАДАНИЕ:**

Выберите из таблицы orders 4 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

### **РЕШЕНИЕ:**

```
SELECT * FROM orders
ORDER BY sum DESC
LIMIT 4
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/ed7b5016-629a-4418-a147-8da6d09b1c71)


## **#2 ЗАДАНИЕ:**

Выберите из таблицы products название и цены четырех самых дешевых товаров, которые есть на складе.

### **РЕШЕНИЕ:**

```
SELECT * FROM products
ORDER BY price
LIMIT 4
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/95b6862f-b0f1-4470-8f27-24f5f8e7d60d)


## **#3 ЗАДАНИЕ:**

Выберите из таблицы orders три последних заказа (по дате date) стоимостью от 3200 рублей и выше.
Данные отсортируйте по дате в обратном порядке.

### **РЕШЕНИЕ:**

```
SELECT * FROM orders
WHERE sum >= 3200
ORDER BY date DESC
LIMIT 3
```

### **СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/f0fcc7c0-040c-4966-95b4-f54d51c4d0cc)


## **#4 ЗАДАНИЕ:**

Создайте данную таблицу:![5420105400654622307](https://github.com/user-attachments/assets/2150186f-fb97-43ff-b531-4cbbf663d122)

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS products;
CREATE TABLE products (
    id INT UNSIGNED NOT NULL,
    name VARCHAR(255) NULL,
    count INTEGER NULL,
    price INTEGER NULL
);
INSERT INTO products (id, name, count, price)
VALUES
    (1, 'Стиральная машина', 5, 10000),
    (2, 'Холодильник', 0, 10000),
    (3, 'Микроволновка', 3, 4000),
    (4, 'Пылесос', 2, 4500),
    (5, 'Вентилятор', 0, 700),
    (6, 'Телевизор', 7, 31740),
    (7, 'Тостер', 2, 2500),
    (8, 'Принтер', 4, 3000),
    (9, 'Активные колонки', 1, 2900),
    (10, 'Ноутбук', 4, 36990),
    (11, 'Посудомоечная машина', 0, 17800),
    (12, 'Видеорегистратор', 23, 4000),
    (13, 'Смартфон', 8, 12300),
    (14, 'Флешка', 4, 1400),
    (15, 'Блендер', 0, 5500),
    (16, 'Газовая плита', 5, 11900),
    (17, 'Клавиатура', 3, 1800);
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/fa2d0950-cd1e-44a2-891f-43420acc1e42)

![изображение](https://github.com/user-attachments/assets/71ec4ecd-72ba-4456-bdd1-065f549b8a17)


## **#5 ЗАДАНИЕ:**

Из этой таблицы сделать выборку на основе задания: Сайт выводит товары по 5 штук. Выберите из таблицы products товары, которые пользователи увидят на 3 странице каталога при сортировке в порядке возрастания цены (price).

### **РЕШЕНИЕ:**

```
SELECT * FROM products
ORDER BY price
LIMIT 10,5
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/cc10cf79-37e6-41fd-9a69-6f72e59205ae)


# **05.04.25**

## **#1 ЗАДАНИЕ:**
Создайте таблицу articles для хранения данных о статьях. В таблице должны быть следующие поля:
id — идентификатор, целое положительное, NULL запрещен
name — название статьи, строка до 80 символов.text — текст статьи.
state — статус статьи. Поле из 3 вариантов: draft (черновик), correction (корректура), public (опубликована).Добавьте 3 записи так, чтобы получалась таблица ниже:![photo_5443150777825750114_x](https://github.com/user-attachments/assets/c3bde0cd-6dd6-4e90-b76d-f3d5fb27d8de)

### **РЕШЕНИЕ:**

```
﻿DROP TABLE IF EXISTS articles;

CREATE TABLE articles (
id INT UNSIGNED NOT NULL,
name VARCHAR (80),
text TEXT,
state ENUM('draft', 'correction', 'public')
);
INSERT INTO articles (id, name, text, state)
VALUES
(1, 'Новое в Python 3.6', '', 'draft'),
(2, 'Оптимизация SQL запросов', 'При больших объемах данных ...', 'correction'),
(3, 'Транзакции в MySQL', 'По долгу службы мне приходится ...', 'public')
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/563e74c1-dc7b-4dd6-a786-04277ca98efd)

![изображение](https://github.com/user-attachments/assets/a661af4b-8155-4eb0-b1a5-de7f9a310e37)


## **#2 ЗАДАНИЕ:**

Создайте таблицу rooms для хранения номеров в отеле:
id — идентификатор, целое положительное.
number — номер комнаты, целое положительное. Всего в отеле 107 комнат. NULL запрещен.
beds — количество спальных мест. Выбор из 1+1, 2+1, 2+2. Можно выбрать только один вариант. NULL запрещен.
additional — дополнительные удобства в номере. Можно выбрать несколько вариантов из списка: conditioner, bar, fridge и wifi.
Добавьте 3 записи так, чтобы получалась таблица ниже:![photo_5443150777825750117_x](https://github.com/user-attachments/assets/52d07086-300a-4e38-82ce-479c1618e999)

### **РЕШЕНИЕ:**

```
CREATE TABLE rooms (
id INT UNSIGNED NOT NULL,
number TINYINT UNSIGNED NOT NULL,
beds ENUM('1+1','2+1','2+2') NOT NULL,
additional SET('conditioner','bar','fridge','wifi')
);
INSERT INTO rooms (id,number,beds,additional)
VALUES
(1,10,'1+1','conditioner,bar,wifi'),
(2,12,'2+1',''),
(3,24,'2+2','fridge,bar,wifi')
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/586f55ee-7578-4721-b890-c8dc2108bbe9)

![изображение](https://github.com/user-attachments/assets/153fab98-f072-4a22-be2b-cc0c9265c999)


## **#3 ЗАДАНИЕ:**

Выберите из таблицы products название, цену и страны всех товаров из России и Белоруссии (в поле country обязательно должна присутствовать или Россия, или Белоруссия).
Выбирайте только товары, у которых задана категория.
Данные отсортируйте по цене в обратном порядке.
Поле country относится к типу SET('RU', 'UA', 'BY', 'KZ') NOT NULL.

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS products;

CREATE TABLE products (
    id INT UNSIGNED NOT NULL,
    category_id INT UNSIGNED NULL,
    name VARCHAR(255) NULL,
    count INTEGER NULL,
    price INTEGER NULL,
    country SET('RU', 'UA', 'BY', 'KZ') NOT NULL
);
INSERT INTO products (id, category_id, name, count, price, country)
VALUES
    (1, 7, 'Стиральная машина', 5, 10000, 'RU,UA'),
    (2, 12, 'Холодильник', 0, 11000, 'BY'),
    (3, 12, 'Микроволновка', 3, 4000, 'UA,KZ'),
    (4, 8, 'Пылесос', 2, 4500, 'KZ,BY'),
    (5, NULL, 'Вентилятор', 0, 700, 'BY,RU'),
    (6, 9, 'Телевизор', 7, 31740, 'RU'),
    (7, 12, 'Тостер', 0, 2500, 'RU'),
    (8, NULL, 'Принтер', 4, 3000, 'UA,BY'),
    (9, NULL, 'Активные колонки', 1, 2900, 'UA');
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/48235781-69c7-4058-8025-2510e7b8cf72)

![изображение](https://github.com/user-attachments/assets/d3c300a2-9f05-4b4b-962d-b40c25fa236c)


# **12.04.25**

## **#1 ЗАДАНИЕ:**

Создайте таблицу orders для хранения списка заказов:
id — идентификатор, целое положительное.
user_id — идентификатор пользователя, который оформил заказ. Целое положительное, NULL запрещен.
amount — стоимость заказа. Целое положительное число не более 1 млн. NULL запрещен, по умолчанию 0.
created — дата и время создания заказа. NULL запрещен.
state — статус заказа. Выбор из new, cancelled, in_progress, delivered, completed. Можно выбрать только один вариант. NULL запрещен. По умолчанию должен стоять new.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5462907485653429719](https://github.com/user-attachments/assets/e228656a-9282-425b-9d0b-f9985a6d5d10)

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS orders;

CREATE TABLE orders (
    id INT UNSIGNED NOT NULL,
    user_id INTEGER NOT NULL CHECK (user_id > 0),
    amount INTEGER NOT NULL DEFAULT 0 CHECK (amount >= 0 AND amount <= 1000000),
    created TIMESTAMP NOT NULL,
    state VARCHAR(20) NOT NULL DEFAULT 'new' CHECK (state IN ('new', 'cancelled', 'in_progress', 'delivered', 'completed'))
);
INSERT INTO orders (id, user_id, amount, created, state)
VALUES
(1, 56, '5400', '2018-02-01 17:46:59', 'new'),
(2, 90, '249', '2018-02-01 19:13:04', 'new'),
(3, 78, '2200', '2018-02-01 22:43:09', 'new');
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/2e6b211f-3391-4e0c-8d60-e88ba66c4896)

![изображение](https://github.com/user-attachments/assets/071f15cd-963e-4bb5-9ffd-c70d41e67eed)


## **#2 ЗАДАНИЕ:**

Создайте таблицу users для хранения списка пользователей сайта:
id — идентификатор, целое положительное.
first_name — имя, строка до 20 символов. NULL запрещен.
last_name — фамилия, строка до 20 символов. NULL запрещен.
patronymic — отчество, строка до 20 символов. NULL запрещен, по умолчанию пустая строка.
is_active — отметка об активности пользователя. Логическое поле, по умолчанию TRUE.
is_superuser — отметка администратора. Логическое поле, по умолчанию FALSE.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5462907485653429721](https://github.com/user-attachments/assets/f7595da3-d7ed-4eca-90d9-da2c600e85ae)

### **РЕШЕНИЕ:**

```
﻿DROP TABLE IF EXISTS users;

CREATE TABLE users (
    id INT UNSIGNED CHECK (id > 0),
    first_name VARCHAR(20) NOT NULL,
    last_name VARCHAR(20) NOT NULL,
    patronymic VARCHAR(20) NOT NULL DEFAULT '',
    is_active BOOLEAN NOT NULL DEFAULT TRUE,
    is_superuser BOOLEAN NOT NULL DEFAULT FALSE
);
INSERT INTO users (id, first_name, last_name, patronymic, is_active, is_superuser)
VALUES
(1, 'Дмитрий', 'Иванов', '', TRUE, FALSE),
(2, 'Анатолий', 'Белый', 'Сергеевич', TRUE, TRUE),
(3, 'Андрей', 'Крючков', '', FALSE, FALSE);
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/0f6c94c1-bba0-4586-87e4-f316cd55fd4c)

![изображение](https://github.com/user-attachments/assets/2aa4e620-17e9-4a15-a22f-9a12822f8d76)


## **#3 ЗАДАНИЕ:**

Создайте таблицу products для хранения товаров в интернет магазине:
id — идентификатор, целое положительное.
category_id — категория, целое положительное. Может принимать NULL. По умолчанию NULL.
name — название, строка до 100 символов. NULL запрещен.
count — количество, целое положительное до 255. NULL запрещен, по умолчанию 0.
price — цена типа DECIMAL с 10 знаками, 2 из которых выделены для копеек. NULL запрещен, по умолчанию 0.00.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5462907485653429722](https://github.com/user-attachments/assets/2a14abe8-40ac-48f6-adbf-1e70bfe36894)

### **РЕШЕНИЕ:**

```
﻿DROP TABLE IF EXISTS products;

CREATE TABLE products (
    id INT UNSIGNED CHECK (id > 0),
    category_id INTEGER DEFAULT NULL CHECK (category_id IS NULL OR category_id > 0),
    name VARCHAR(100) NOT NULL,
    count INTEGER NOT NULL DEFAULT 0 CHECK (count >= 0 AND count <= 255),
    price DECIMAL(10, 2) NOT NULL DEFAULT 0.00
);
INSERT INTO products (id, category_id, name, count, price)
VALUES
(1, 1, 'Кружка', 5, 45.9),
(2, 17, 'Фломастеры', 0, 78.00),
(3, NULL, 'Сникерс', 12, 59.80);
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/1e194593-ac98-45f9-b4ae-3b2fb6a43095)

![изображение](https://github.com/user-attachments/assets/13232fc0-2cad-4750-a763-ae0b0825f24d)


# **22.04.25**

## **#1 ЗАДАНИЕ:**

Создайте таблицу users с со следующими полями:
id — идентификатор, целое положительное, первичный ключ без автоинкремента, NULL запрещен.
first_name — имя пользователя, строка до 50 символов.
last_name — фамилия пользователя, строка до 50 символов.
birthday — дата рождения. Пользователь может не указать день рождения и тогда в поле нужно хранить NULL.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5206482660883558921](https://github.com/user-attachments/assets/1788aec5-7446-4668-a4ad-f1fd6c99b519)

### **РЕШЕНИЕ:**

```
﻿DROP TABLE IF EXISTS users;

CREATE TABLE users (
    id INT UNSIGNED CHECK (id > 0),
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    birthday DATE DEFAULT NULL
);
INSERT INTO users (id, first_name, last_name, birthday)
VALUES
(1, 'Дмитрий', 'Иванов', NULL),
(2, 'Анатолий', 'Белый', NULL),
(3, 'Денис', 'Давыдов', '1999-09-08');
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/cb3d2764-4730-420e-87e1-c372b22a4930)

![изображение](https://github.com/user-attachments/assets/3bbe1071-339c-4d4a-b4cd-ba564dc90340)


## **#2 ЗАДАНИЕ:**

Создайте таблицу orders с автоинкрементальным первичным ключом id, полем state для хранения статуса заказа и полем amount для хранения суммы заказа. Статус заказа умещается в строку длиной 8 символов, а сумма заказа является денежным типом до 1 млн. с двумя знаками после десятичной точки.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5206482660883558931](https://github.com/user-attachments/assets/e244a922-0c2a-4a78-aa73-c5a271174bf2)

### **РЕШЕНИЕ:**

```
DROP TABLE IF EXISTS orders;

CREATE TABLE orders (
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY NOT NULL,
    state VARCHAR(8) NOT NULL,
    amount DECIMAL(8, 2) NOT NULL CHECK (amount >= 0 AND amount <= 1000000)
);
INSERT INTO orders (state, amount)
VALUES
('new', 1000.50),
('new', 3400.10),
('delivery', 7300.50);
```

### **СКРИНШОТ:**

![изображение](https://github.com/user-attachments/assets/9b813deb-b57d-4708-b80d-aafae43b1915)

![изображение](https://github.com/user-attachments/assets/f38ec62e-2aa2-42fc-bd68-c2388b06f338)

