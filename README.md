#goit-rdb-hw-03 Relationship Databases Topic III

1. Ця команда SQL дозволяє:

1.1 вибрати всі стовпчики (За допомогою wildcard \*) з таблиці products:

![Screenshot](./assets/Screenshot%20rdb-hw-03-test-01.1.jpeg)

1.2 вибрати тільки стовпчики name, phone з таблиці shippers:

![Screenshot](./assets/Screenshot%20rdb-hw-03-test-01.2.jpeg)

2. Ця команда SQL дозволяє знайти середнє, максимальне та мінімальне значення стовпчика price таблички products:

![Screenshot](./assets/Screenshot%20rdb-hw-03-test-02.jpeg)

3. Ця команда SQL дозволяє обрати унікальні значення колонок category_id та price таблиці products,
   та порядок виведення на екран за спаданням значення price, тільки 10 рядків:

![Screenshot](./assets/Screenshot%20rdb-hw-03-test-03.jpeg)

4. Ця команда SQL дозволяє знайти кількість продуктів (рядків), які знаходиться в цінових межах від 20 до 100:

![Screenshot](./assets/Screenshot%20rdb-hw-03-test-04.jpeg)

5. Ця команда SQL дозволяє знайти кількість продуктів (рядків) та середню ціну (price) у кожного постачальника (supplier_id):

![Screenshot](./assets/Screenshot%20rdb-hw-03-test-05.jpeg)

6. # This is the contents of the sql_code

`#1.1
SELECT \* FROM mydb.products;

#1.2
SELECT name, phone
FROM mydb.shippers;

#2
SELECT
AVG(price) AS avg_price,
MAX(price) AS max_price,
MIN(price) AS min_price
FROM
products;

#3
SELECT DISTINCT category_id AS unique_cat_id, price
FROM products
ORDER BY price DESC
LIMIT 10;

#4
SELECT
COUNT(\*) AS count_products
FROM
products
WHERE
price BETWEEN 20 AND 100;

#5
SELECT
supplier_id,
COUNT(name) AS products_by_supplier,
AVG(price) AS avg_price
FROM
products
GROUP BY supplier_id;`
