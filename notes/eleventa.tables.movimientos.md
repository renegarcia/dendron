---
id: daingquzgpp6xwy0qv98u9p
title: MOVIMIENTOS
desc: null
updated: 1684521572
created: 1684521572
---


```sql
 CREATE TABLE MOVIMIENTOS (ID TLLAVE NOT NULL,
        OPERACION_ID TLLAVE NOT NULL,
        MONTO TMONEDA,
        CUANDO_FUE TFECHAHORA NOT NULL,
        COMENTARIOS TCADENALARGA,
        TIPO TTIPOMOVIMIENTO NOT NULL,
        CLIENTE_ID TLLAVE,
        CAJA_ID TLLAVE NOT NULL,
        CAJERO_ID TLLAVE NOT NULL,
        ABONO_ID TLLAVE,
        CLIENTESV2_CREDITO_ID INTEGER,
CONSTRAINT PK_MOVIMIENTOS PRIMARY KEY (ID));
```