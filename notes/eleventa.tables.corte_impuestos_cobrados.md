---
id: 5q4h1fa8xqlpuc5kc160xee
title: CORTE_IMPUESTOS_COBRADOS
desc: null
updated: 1684521571
created: 1684521571
---


```sql
 CREATE TABLE CORTE_IMPUESTOS_COBRADOS (ID TLLAVE NOT NULL,
        ID_IMPUESTO TLLAVE NOT NULL,
        ACUMULADO_IMPUESTOS TCURRENCY DEFAULT 0,
        ACUMULADO_VENTAS_GRAVADAS TCURRENCY DEFAULT 0,
        ID_TURNO TLLAVE NOT NULL,
        ACUMULADO_IMPUESTOS_NO_DESG TCURRENCY DEFAULT 0,
CONSTRAINT PK_CORTE_IMPUESTOS_COBRADOS PRIMARY KEY (ID));
```