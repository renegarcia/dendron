---
id: 1cwxvczpppdwyd83doq4ze6
title: PRODUCTO_COMPONENTES
desc: null
updated: 1684521573
created: 1684521573
---


```sql
 CREATE TABLE PRODUCTO_COMPONENTES (PRODUCTO_PADRE_ID TLLAVE NOT NULL,
        PRODUCTO_HIJO_ID TLLAVE NOT NULL,
        CANTIDAD TCANTIDAD NOT NULL,
CONSTRAINT UNQ_COMPONENTES_PADRE_HIJO UNIQUE (PRODUCTO_PADRE_ID, PRODUCTO_HIJO_ID));
```