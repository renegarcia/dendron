---
id: 5slyq6tlqawhmbo6b82c91o
title: ARTICULO_COMPONENTES
desc: null
updated: 1684521571
created: 1684521571
---


```sql
 CREATE TABLE ARTICULO_COMPONENTES (ARTICULO_ID TLLAVE NOT NULL,
        PRODUCTO_PADRE_ID TLLAVE NOT NULL,
        PRODUCTO_HIJO_ID TLLAVE NOT NULL,
        CANTIDAD TCANTIDAD NOT NULL,
CONSTRAINT UNQ_ART_COMP_PADRE_HIJO UNIQUE (ARTICULO_ID, PRODUCTO_PADRE_ID, PRODUCTO_HIJO_ID));
```