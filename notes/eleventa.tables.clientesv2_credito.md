---
id: 3uzq031j1ok17hzzkyo5hvi
title: CLIENTESV2_CREDITO
desc: null
updated: 1684521571
created: 1684521571
---


```sql
 CREATE TABLE CLIENTESV2_CREDITO (CLIENTESV2_ID TLLAVE NOT NULL,
        TIENE_CREDITO SMALLINT DEFAULT 0,
        LIMITE_CREDITO NUMERIC(10, 4) DEFAULT 0,
        ULTIMO_ABONO TIMESTAMP,
        SALDO_ACTUAL NUMERIC(10, 4) DEFAULT 0,
        ELIMINADO_EN TFECHAHORA,
CONSTRAINT PK_CLIENTESV2_CREDITO_ID PRIMARY KEY (CLIENTESV2_ID));
```