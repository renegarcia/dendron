---
id: 14jdu6joty8qqo2enxzcw42
title: CREDITOS_ABONOS_IMPUESTOS
desc: null
updated: 1684521571
created: 1684521571
---


```sql
 CREATE TABLE CREDITOS_ABONOS_IMPUESTOS (ID TLLAVE NOT NULL,
        ABONO_ID TLLAVE NOT NULL,
        VENTA_ID TLLAVE NOT NULL,
        IMPUESTO_ID TLLAVE NOT NULL,
        IMPUESTO_PORCENTAJE TMONEDA NOT NULL,
        IMPUESTO_BASE TMONEDA DEFAULT 0,
        IMPUESTO_MONTO TMONEDA DEFAULT 0,
CONSTRAINT PK_CA_IMPUESTOS_ID PRIMARY KEY (ID));
```