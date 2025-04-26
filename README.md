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



### **СКРИНШОТ:**



## **#5 ЗАДАНИЕ:**
Из этой таблицы сделать выборку на основе задания: Сайт выводит товары по 5 штук. Выберите из таблицы products товары, которые пользователи увидят на 3 странице каталога при сортировке в порядке возрастания цены (price).


# **05.04.25**

## **#1 ЗАДАНИЕ:**
Создайте таблицу articles для хранения данных о статьях. В таблице должны быть следующие поля:
id — идентификатор, целое положительное, NULL запрещен
name — название статьи, строка до 80 символов.text — текст статьи.
state — статус статьи. Поле из 3 вариантов: draft (черновик), correction (корректура), public (опубликована).Добавьте 3 записи так, чтобы получалась таблица ниже:

## **#2 ЗАДАНИЕ:**

Создайте таблицу rooms для хранения номеров в отеле:

id — идентификатор, целое положительное.
number — номер комнаты, целое положительное. Всего в отеле 107 комнат. NULL запрещен.
beds — количество спальных мест. Выбор из 1+1, 2+1, 2+2. Можно выбрать только один вариант. NULL запрещен.
additional — дополнительные удобства в номере. Можно выбрать несколько вариантов из списка: conditioner, bar, fridge и wifi.
Добавьте 3 записи так, чтобы получалась таблица ниже:


## **#3 ЗАДАНИЕ:**
Создайте таблицу rooms для хранения номеров в отеле:

id — идентификатор, целое положительное.
number — номер комнаты, целое положительное. Всего в отеле 107 комнат. NULL запрещен.
beds — количество спальных мест. Выбор из 1+1, 2+1, 2+2. Можно выбрать только один вариант. NULL запрещен.
additional — дополнительные удобства в номере. Можно выбрать несколько вариантов из списка: conditioner, bar, fridge и wifi.

## **#4 ЗАДАНИЕ:**
Выберите из таблицы products название, цену и страны всех товаров из России и Белоруссии (в поле country обязательно должна присутствовать или Россия, или Белоруссия).
Выбирайте только товары, у которых задана категория.
Данные отсортируйте по цене в обратном порядке.

Поле country относится к типу SET('RU', 'UA', 'BY', 'KZ') NOT NULL.




# **12.04.25**

## **#1 ЗАДАНИЕ:**

Создайте таблицу orders для хранения списка заказов:

id — идентификатор, целое положительное.
user_id — идентификатор пользователя, который оформил заказ. Целое положительное, NULL запрещен.
amount — стоимость заказа. Целое положительное число не более 1 млн. NULL запрещен, по умолчанию 0.
created — дата и время создания заказа. NULL запрещен.
state — статус заказа. Выбор из new, cancelled, in_progress, delivered, completed. Можно выбрать только один вариант. NULL запрещен. По умолчанию должен стоять new.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5462907485653429719](https://github.com/user-attachments/assets/e228656a-9282-425b-9d0b-f9985a6d5d10)



## **#2 ЗАДАНИЕ:**

Создайте таблицу users для хранения списка пользователей сайта:

id — идентификатор, целое положительное.
first_name — имя, строка до 20 символов. NULL запрещен.
last_name — фамилия, строка до 20 символов. NULL запрещен.
patronymic — отчество, строка до 20 символов. NULL запрещен, по умолчанию пустая строка.
is_active — отметка об активности пользователя. Логическое поле, по умолчанию TRUE.
is_superuser — отметка администратора. Логическое поле, по умолчанию FALSE.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5462907485653429721](https://github.com/user-attachments/assets/f7595da3-d7ed-4eca-90d9-da2c600e85ae)


## **#3 ЗАДАНИЕ:**

Создайте таблицу products для хранения товаров в интернет магазине:

id — идентификатор, целое положительное.
category_id — категория, целое положительное. Может принимать NULL. По умолчанию NULL.
name — название, строка до 100 символов. NULL запрещен.
count — количество, целое положительное до 255. NULL запрещен, по умолчанию 0.
price — цена типа DECIMAL с 10 знаками, 2 из которых выделены для копеек. NULL запрещен, по умолчанию 0.00.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5462907485653429722](https://github.com/user-attachments/assets/2a14abe8-40ac-48f6-adbf-1e70bfe36894)




# **22.04.25**

## **#1 ЗАДАНИЕ:**

оздайте таблицу users с со следующими полями:

id — идентификатор, целое положительное, первичный ключ без автоинкремента, NULL запрещен.
first_name — имя пользователя, строка до 50 символов.
last_name — фамилия пользователя, строка до 50 символов.
birthday — дата рождения. Пользователь может не указать день рождения и тогда в поле нужно хранить NULL.
Добавьте 3 записи так, чтобы получалась таблица ниже:![5206482660883558921](https://github.com/user-attachments/assets/1788aec5-7446-4668-a4ad-f1fd6c99b519)

## **#2 ЗАДАНИЕ:**

Создайте таблицу orders с автоинкрементальным первичным ключом id, полем state для хранения статуса заказа и полем amount для хранения суммы заказа. Статус заказа умещается в строку длиной 8 символов, а сумма заказа является денежным типом до 1 млн. с двумя знаками после десятичной точки.

Добавьте 3 записи так, чтобы получалась таблица ниже:![5206482660883558931](https://github.com/user-attachments/assets/e244a922-0c2a-4a78-aa73-c5a271174bf2)

