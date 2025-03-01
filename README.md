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











