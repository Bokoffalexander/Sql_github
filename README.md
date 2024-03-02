# SQL
## _Beautiful_

**SQL** postgres

## Создание БД с внешним ключом:

```sql
CREATE DATABASE cats_db;

CREATE TABLE cats
(
    id         BIGSERIAL PRIMARY KEY,
    cat        VARCHAR(99) NOT NULL,
    id_shop    INTEGER,
    FOREIGN KEY (id_shop) REFERENCES shops(id)
);

CREATE TABLE shops
(
    id         BIGSERIAL PRIMARY KEY,
    shop       VARCHAR(99) NOT NULL
);
```

## Пример LEFT JOIN 2-х таблиц кошки и магазины:

```sql
SELECT     cat, shop
FROM       cats
LEFT JOIN  shops
ON         shop_id=id;
```
