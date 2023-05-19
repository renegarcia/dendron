---
id: 58tvvxla3fjvy6wkqa398a2
title: CLIENTESV2
desc: null
updated: 1684521571
created: 1684521571
---


```sql
 CREATE TABLE CLIENTESV2 (ID INTEGER NOT NULL,
        FOLIO INTEGER,
        NOMBRES TCADENALARGA NOT NULL,
        APELLIDOS TCADENALARGA,
        EMAIL TCADENALARGA,
        TELEFONO VARCHAR(50),
        DOMICILIO1 TCADENALARGA,
        DOMICILIO2 TCADENALARGA,
        COLONIA TCADENALARGA,
        MUNICIPIO TCADENALARGA,
        ESTADO TCADENALARGA,
        PAIS TCADENALARGA,
        CODIGO_POSTAL VARCHAR(20),
        NOTAS VARCHAR(1000),
        TOTAL_VENTAS NUMERIC(10, 4) DEFAULT 0,
        TOTAL_GANANCIAS NUMERIC(10, 4) DEFAULT 0,
        TOTAL_TICKETS INTEGER DEFAULT 0,
        ACTIVO SMALLINT DEFAULT 1,
        DE_SISTEMA SMALLINT,
        OLD_CLIENTE_ID TLLAVE,
        OLD_FACTURACION_CLIENTES_ID TLLAVE,
CONSTRAINT CLIENTESV2_PK PRIMARY KEY (ID));
```