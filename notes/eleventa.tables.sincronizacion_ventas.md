---
id: t66t752477yo9qwv81tscqt
title: SINCRONIZACION_VENTAS
desc: null
updated: 1684521573
created: 1684521573
---


```sql
 CREATE TABLE SINCRONIZACION_VENTAS (VENTA_ID TLLAVE NOT NULL,
        SINCRONIZADO_EN TFECHAHORA,
        MENSAJE_ERROR TCADENAMEDIANA,
CONSTRAINT PK_NUBE_DELTA PRIMARY KEY (VENTA_ID));
```